## Online Graduate Tracer System has XSS vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/15904/online-graduate-tracer-system-college-ict-alumni.html

## Vulnerability file
/tracking/admin/add_acc.php

## Vulnerability analysis
<img width="1303" alt="image" src="https://github.com/user-attachments/assets/e44351e5-1e0b-48d0-8749-fcdca29381a9">


## describe
There are unlimited XSS attacks on the Onlinegraduate Tracer system. Attackers can use this vulnerability to obtain sensitive system information, including cookies, keylogging, etc.
POC
```
Visit admin/exportcs.php
```

<img width="1456" alt="image" src="https://github.com/user-attachments/assets/ad3a11f1-45ef-4681-aefd-561e056a6ed8">

<img width="1299" alt="image" src="https://github.com/user-attachments/assets/668aab78-56a9-4464-8e60-3aa86d52e90e">







