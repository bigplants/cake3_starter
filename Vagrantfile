# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.20"
    config.vm.hostname = "scotchbox"
    # config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    # Optional NFS. Make sure to remove other synced_folder line too
    config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }
    config.vm.provision "shell", inline: <<-EOT
            sed -i -e "s%/var/www/public%/var/www/webroot%" /etc/apache2/sites-available/000-default.conf
            /etc/init.d/apache2 restart
    EOT
end
