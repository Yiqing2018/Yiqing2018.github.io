---
layout:     post
title:      Configuring for PHP development environment
subtitle:   Apache, Mysql, phpMyAdmin on MacOS10.13.3
date:       2018-02-08
author:     Yiqing
header-img: img/post-bg-skill.jpg
catalog: true
tags:
    - php
    - PracticalSkill

---
# Introduction

>This article shows how to set up for PhP development environment on Mac, which includes **Apache web server**, **Mysql database** and **PhpMyadmin**  
MAMP(Mac+Apache+Mysql+PHP) works as an ideal PHP development environment for Mac. As for phpMyAdmin, it helps us manage our database conveniently


# Preparations

#### some test documents(e.g.)
test1.html  

    <html>
    <head>  
      <title>hello world</title>  
    </head>
    <body>  
    I love you!  
    </body>  
    </html>

---
test2.html  

    <html>
    <head>  
      <title>hello</title>  
    </head>
    <body>  
    I love you so much!  
    </body>  
    </html>

---
test3.php  

    <?php
    echo "Hellole world!";
    ?>

---


# How To Set up
### 1.Apache Web Service
Apache has been installed on Mac, so you just need to open the terminal and type: $ `sudo apachectl start` and then type into your computer password.  
(stop apache service: sudo apachectl stop)  
Open your browser and go to 127.0.0.1 when it shows _It works!_ that means you have started Apache.
### 2.Web resources default path  
The default path of web resources on Mac is `/Library/WebServer/Documents/`  
If you put the test1.html under that path, then go to _127.0.0.1/_ test1.html” it would show“I love you!”
### 3. Reset the Default Path
Sometimes it is inconvenient to use the default path, so we could reset the path:
go to `“/private/etc” `and find the folder `“apache2”` , and the file named `“httpd.conf”`(these documents are related to the  configuration of Mac, so you’d better back up etc folder in case)

open `“http.conf”`, find keyword- `DocumentRoot` and write down your prefer path.

And in order to test if you are doing right, plz put the test2.html under the path you has reset.

And then restart Apache(“sudo apchectl restart”) open the browser, type into `“127.0.0.1/test2.html”` when it shows `“I love you so much!”` it means you’ve done well.

### 4.PHP
Mac has installed PHP already, you could start the service in one step.
open the “https.conf” file and find the keyword `“php” ` delete the `“#”` in front of the sentence.
restart apache service and put test3.php under the new path, then go to `“127.0.0.1/test3.php”` when is shows `“hello world”`, it means it works.

### 5. install Mysql

I’ve tries install the newest 5.7 version but it doesn’t work. So I installed 5.6 version instead.

go to the website to download, you could get a dmg/pkg file…. it is very easy, just as you have installed other softwares on Mac. (5.7 version  you should pay attention to the password generated  randomly, as for 5.6 version, it is `empty-password`)

Open the terminal, and type as follows:  
```
>>/usr/local/mysql/bin
>>ls
(to confirm whether there is a file named mysql under the directory)
>>vim ~/.bash_profile
>>PATH=$PATH:/usr/local/mysql/bin
next is reset your password(5.6 version empty password)
>>mysql -uroot -p
(just click on the enter button, since the password is empty)
>>use mysql;
>>UPDATE user SET Password = PASSWORD(‘root’) WHERE user = ‘root’;
(my new pass is ‘root’ you can choose your pass)
>>FLUSH PRIVILEGES;
(if you want to uninstall Mysql, check on this)
```  
if you want to uninstall Mysql, check on [this](https://blog.csdn.net/u012721519/article/details/55002626).
### 6. install phpMyadmin

download the phpMyadmin folder from the official website and put it under the new path you have just set. (rename the folder as `phpmyadmin`)

open the browser and go to `“127.0.0.1/phpmyadmin”` use the password you just set, it is easy to login into and use your database!  

#### References  
[Set up Mysql on Mac](https://blog.csdn.net/pansanday/article/details/54915916)  
[Mysql empty password](https://blog.csdn.net/cubeli90/article/details/52336939)  
[build MAMP](http://blog.sina.com.cn/s/blog_7c0a6c550102wv07.html)  







