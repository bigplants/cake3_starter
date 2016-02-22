# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.20"
    config.vm.hostname = "scotchbox"

    if ( RUBY_PLATFORM.downcase =~ /darwin/ )
        config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }
    else
        config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]
    end

    config.vm.provision "shell", inline: <<-EOT
            sed -i -e "s%/var/www/public%/var/www/webroot%" /etc/apache2/sites-available/000-default.conf
            /etc/init.d/apache2 restart
            echo "CREATE DATABASE IF NOT EXISTS my_app" | mysql -uroot -proot
            sudo /usr/local/bin/composer self-update
            cd /var/www;composer update
    EOT
end
