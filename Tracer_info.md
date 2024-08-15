## Online Graduate Tracer System has information leakage vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/15904/online-graduate-tracer-system-college-ict-alumni.html

## Vulnerability file
/tracking/admin/export_it.php

## Vulnerability analysis
<img width="1215" alt="image" src="https://github.com/user-attachments/assets/8b7040e3-ec38-4e7e-add6-0a3cd4487f85">



## describe
The Onlinegraduate Tracer system has unlimited information leakage attacks. An attacker can use this vulnerability to obtain user information in the system, including name, phone number, address, etc.

POC
```
Visit admin/export_it.php
```
Access this route directly without logging in to download personal information.

<img width="1363" alt="image" src="https://github.com/user-attachments/assets/b0f8820a-eaa4-44bb-917d-4f7cbf11cb96">


<img width="1696" alt="image" src="https://github.com/user-attachments/assets/7ae29cbd-3e8d-4c65-ae8c-5627251f88aa">







