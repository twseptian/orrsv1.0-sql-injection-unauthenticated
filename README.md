# Online Railway Reservation System 1.0 - 'id' SQL Injection (Unauthenticated)
origininal link: https://www.exploit-db.com/exploits/50646
```bash
# Exploit Title: Online Railway Reservation System 1.0 - 'id' SQL Injection (Unauthenticated)
# Date: 07/01/2022
# Exploit Author: twseptian
# Vendor Homepage: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html
# Software Link: https://www.sourcecodester.com/sites/default/files/download/oretnom23/orrs.zip
# Version: v1.0
# Tested on: Kali Linux 2021.4,PHP 7.4.26
```
## SQL Injection
SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to it's database. Online Railway Reservation System v1.0 is vulnerable to SQL injection via the 'id' parameter on the Reservation Form.

## Attack Vector
An attacker can compromise the database of the application using some automated(or manual) tools like SQLmap.

## Steps of reproduce:
- Step-1: Navigate to 'Schedule' > go to 'Book' or 'Revervation Form' page using the following URL: http://localhost/orrs/?page=reserve&sid=1
- Step-2: Put the SQL Injection payloads in 'id' field. In this we used time-based blind payload: `/orrs/?page=reserve&sid=1') AND (SELECT 6842 FROM (SELECT(SLEEP(5)))UsWr) AND ('WBCm'='WBCm`
- Step-3: Now, the Server target accepted our payload and the response got delayed by 5 seconds.
