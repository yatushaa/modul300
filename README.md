

FTP
-----------------------------

Einfacher FTP mit Ubuntu 16.x.

### Erstellen und konfigurieren einer Gast Maschine

    cd ftp
    vagrant up
 
Die Dateien werden lokal im aktuellen Verzeichnis abgelegt: 

	config.vm.synced_folder ".", "devops\vagrant\ftp\.vagrant\machines\ftp"

Description: Vagrant Ubuntu Trusty64 VM mit ftp server installiert. Das User Interface ist via ftp://localhost:2121/ erreichbar

    sudo nano /etc/vsftpd.conf
Wechseln von anonymous_enable=YES --> anonymous=NO

    sudo service vsftpd restart

    username= anonymous
    passwort=

Dannach sollte Login successful

