## Sourcecoster simple online bidding system has Unauthorized access

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/admin/users.php

## describe
A simple online bidding system has an unrestricted unauthorized access vulnerability that allows an attacker to obtain sensitive server information.

POC
```
/simple-online-bidding-system/bidding/admin/users.php  access
```
If you access this URL without logging in, you can directly access the user management page without authorization, and you can modify and delete the account without authorization.
<img width="1238" alt="image" src="https://github.com/user-attachments/assets/f5044708-f3f5-48c1-a8ea-b7371b97086f">







