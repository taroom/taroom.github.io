cara setting domain lokal dengan direktori di home
- buat dulu sebuah folder misalkan demidesa__gitlab

- setting owner folder
sudo chown -R $USER:$USER ~/Project/artech/demidesa__gitlab/

- setting modifier
sudo chmod -R 755 ~/Project/artech/demidesa__gitlab/

- list file (optional)
ls -l ~/Project/artech/

- membuat sebuah vhost baru di..
sudo vim /etc/hosts

- membuat conf di sites_enable
contoh : /etc/apache2/sites-available/demidesa.lan.conf

- mengaktifkan site
sudo a2ensite demidesa.lan.conf

-reload apache 
sudo systemctl reload apache2

https://www.youtube.com/watch?v=lkLAJd-Wb80
https://www.codepolitan.com/membuat-virtual-host-apache-di-ubuntu-1604-59e6e64e472e1
https://www.ostechnix.com/configure-apache-virtual-hosts-ubuntu-part-1/