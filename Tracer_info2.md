## Online Graduate Tracer System has information leakage vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/15904/online-graduate-tracer-system-college-ict-alumni.html

## Vulnerability file
/tracking/admin/exportcs.php

## Vulnerability analysis
<img width="1148" alt="image" src="https://github.com/user-attachments/assets/9b1f6645-c4ad-4f7d-83b3-0397997a6d12">

## describe
The Onlinegraduate Tracer system has unlimited information leakage attacks. An attacker can use this vulnerability to obtain user information in the system, including name, phone number, address, etc.

POC
```
Visit admin/exportcs.php
```
Access this route directly without logging in to download personal information.

<img width="1111" alt="image" src="https://github.com/user-attachments/assets/a0d22c61-6b83-44c5-a64d-b7fd1a5040b9">

<img width="1706" alt="image" src="https://github.com/user-attachments/assets/7e87cf0d-c3a6-4e2d-924b-803f2fc25d1a">







