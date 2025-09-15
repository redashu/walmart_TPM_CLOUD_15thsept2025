# walmart_TPM_CLOUD_15thsept2025

## In cloud system  scalling understanding 

<img src="scale1.png">

## HA in cloud with cloud region and AvZone 

<img src="scale2.png">

### cloud deployment Model 

<img src="model1.png">

### How cloud is offering service to USers

<img src="model2.png">

### Deploying webapp consideration 

<img src="model3.png">

## setup webapp in centos 9 stream server vm 

### Inastalling git cli 

```
[ashutoshhsingh93@ashuvm1 ~]$ sudo dnf install git -y 
Last metadata expiration check: 0:17:09 ago on Mon 15 Sep 2025 06:10:32 PM UTC.
Dependencies resolved.
===============================================================================================================================================
 Package                                   Architecture              Version                                Repository                    Size
===============================================================================================================================================
Installing:
 git                                       x86_64                    2.47.3-1.el9                           appstream                     51 k
Installing dependencies:
 emacs-filesystem                          noarch                    1:27.2-18.el9                          appstream                    9.2 k
 git-core                    

 ```

 ### clone the code 

 ```
 [ashutoshhsingh93@ashuvm1 ~]$ git clone https://github.com/schoolofdevops/html-sample-app.git
Cloning into 'html-sample-app'...
remote: Enumerating objects: 74, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 74 (delta 0), reused 0 (delta 0), pack-reused 71 (from 1)
Receiving objects: 100% (74/74), 1.38 MiB | 8.08 MiB/s, done.
Resolving deltas: 100% (5/5), done.
[ashutoshhsingh93@ashuvm1 ~]$ ls
html-sample-app
[ashutoshhsingh93@ashuvm1 ~]$ ls html-sample-app/
assets  elements.html  generic.html  html5up-phantom.zip  images  index.html  LICENSE.txt  README.txt
[ashutoshhsingh93@ashuvm1 ~]$ 

```

### Installing httpd 

```
sudo dnf install httpd -y 

```

### copy content to app server


```
 sudo cp -rf html-sample-app/*   /var/www/html/
```

### follow the rest 

```
ashutoshhsingh93@ashuvm1 ~]$ ls
html-sample-app
[ashutoshhsingh93@ashuvm1 ~]$ ls /var/www/html/
[ashutoshhsingh93@ashuvm1 ~]$ ls
html-sample-app
[ashutoshhsingh93@ashuvm1 ~]$ sudo cp -rf html-sample-app/   /var/www/html/
[ashutoshhsingh93@ashuvm1 ~]$ 
[ashutoshhsingh93@ashuvm1 ~]$ ls /var/www/html/
html-sample-app
[ashutoshhsingh93@ashuvm1 ~]$ sudo cp -rf html-sample-app/*   /var/www/html/
[ashutoshhsingh93@ashuvm1 ~]$ 
[ashutoshhsingh93@ashuvm1 ~]$ ls /var/www/html/
assets  elements.html  generic.html  html5up-phantom.zip  html-sample-app  images  index.html  LICENSE.txt  README.txt
[ashutoshhsingh93@ashuvm1 ~]$ 
[ashutoshhsingh93@ashuvm1 ~]$ sudo systemctl start httpd
[ashutoshhsingh93@ashuvm1 ~]$ sudo systemctl status httpd
● httpd.service - The Apache HTTP Server
     Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; preset: disabled)
     Active: active (running) since Mon 2025-09-15 18:41:20 UTC; 5s ago
       Docs: man:httpd.service(8)
   Main PID: 85890 (httpd)
     Status: "Started, listening on: port 80"
      Tasks: 177 (limit: 10622)
     Memory: 14.3M (peak: 14.7M)
        CPU: 92ms
     CGroup: /system.slice/httpd.service
             ├─85890 /usr/sbin/httpd -DFOREGROUND
             ├─85891 /usr/sbin/httpd -DFOREGROUND
             ├─85892 /usr/sbin/httpd -DFOREGROUND
             ├─85893 /usr/sbin/httpd -DFOREGROUND
             └─85894 /usr/sbin/httpd -DFOREGROUND
```