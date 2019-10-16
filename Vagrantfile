Vagrant.configure("2") do |config|

    config.vm.define "gitlab-ci-stack"
    config.vm.box = "ubuntu/bionic64"

    # Register domain and tld for later access prettiness (working with vagrant-dns Plugin https://github.com/BerlinVagrant/vagrant-dns)
    config.vm.hostname = "rockbits"
    config.dns.tld = "it"

    # Configure private network and static ip (https://www.vagrantup.com/docs/networking/private_network.html)
    config.vm.network "private_network", ip: "192.168.50.60"

    config.vm.provider :virtualbox do |virtualbox|
        virtualbox.name = "gitlab-ci-stack"
        #virtualbox.gui = true
        virtualbox.memory = 4096
        virtualbox.cpus = 4

        # Forward DNS resolver from host (vagrant dns) to box
        virtualbox.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end

end