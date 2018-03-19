
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
config.vm.define "ftp" do |ftp|
    ftp.vm.box = "ubuntu/trusty64"
    ftp.vm.hostname = "ftp01"
	ftp.vm.network "forwarded_port", guest:21, host:2121, auto_correct: true
	ftp.vm.provider "virtualbox" do |vb|
	  vb.memory = "512"  
	end  
   
ftp.vm.provision "shell", inline: <<-SHELL
	sudo apt-get update
	sudo apt-get install vsftpd
	sudo sed -i -e 's/anonymous_enable=NO/anonymous_enable=YES/' /etc/vsftpd.conf
	vagrant ssh
	sudo ufw allow 20/tcp
	sudo ufw allow 21/tcp
	sudo ufw allow 22/tcp
	sudo ufw enable
	exit
SHELL
end
end