Vagrant.configure("2") do |config|
    config.vm.box = "debian/buster64"

    config.vm.define "admin" do |admin|
        admin.vm.hostname = "admin"
        admin.vm.network "private_network", ip: "10.0.9.10"    
    end

    config.vm.define "mariadb" do |mariadb|
        mariadb.vm.hostname = "mariadb"
        mariadb.vm.network "private_network", ip: "10.0.9.11"    
    end

    config.vm.define "webserver" do |webserver|
        webserver.vm.hostname = "webserver"
        webserver.vm.network "private_network", ip: "10.0.9.12"
        webserver.vm.provision :shell, path: "webserver/apache2.sh"    
    end

    config.vm.provision :shell, path: "init.sh"
end