# ZAP Scanning Report

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 0 |
| Low | 3 |
| Informational | 3 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Insufficient Site Isolation Against Spectre Vulnerability | Low | 4 |
| Unexpected Content-Type was returned | Low | 8 |
| ZAP is Out of Date | Low | 1 |
| A Client Error response code was returned by the server | Informational | 648 |
| Non-Storable Content | Informational | 12 |
| User Agent Fuzzer | Informational | 180 |




## Alert Detail



### [ Insufficient Site Isolation Against Spectre Vulnerability ](https://www.zaproxy.org/docs/alerts/90004/)



##### Low (Medium)

### Description

Cross-Origin-Resource-Policy header is an opt-in header designed to counter side-channels attacks like Spectre. Resource should be specifically set as shareable amongst different origins.

* URL: http://api-gateway:8080/api/v1/contacts

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/blocked

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/incoming

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/outgoing

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 4

### Solution

Ensure that the application/web server sets the Cross-Origin-Resource-Policy header appropriately, and that it sets the Cross-Origin-Resource-Policy header to 'same-origin' for all web pages.
'same-site' is considered as less secured and should be avoided.
If resources must be shared, set the header to 'cross-origin'.
If possible, ensure that the end user uses a standards-compliant and modern web browser that supports the Cross-Origin-Resource-Policy header (https://caniuse.com/mdn-http_headers_cross-origin-resource-policy).

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Embedder-Policy ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Embedder-Policy)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 14

#### Source ID: 3

### [ Unexpected Content-Type was returned ](https://www.zaproxy.org/docs/alerts/100001/)



##### Low (High)

### Description

A Content-Type of text/html was returned by the server.
This is not one of the types expected to be returned by an API.
Raised by the 'Alert on Unexpected Content Types' script

* URL: http://api-gateway:8080/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``


Instances: 8

### Solution



### Reference




#### Source ID: 4

### [ ZAP is Out of Date ](https://www.zaproxy.org/docs/alerts/10116/)



##### Low (High)

### Description

The version of ZAP you are using to test your app is out of date and is no longer being updated.
The risk level is set based on how out of date your ZAP version is.

* URL: http://api-gateway:8080/api/v1/contacts//accept

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `The latest version of ZAP is 2.17.0`


Instances: 1

### Solution

Download the latest version of ZAP from https://www.zaproxy.org/download/ and install it.

### Reference


* [ https://www.zaproxy.org/download/ ](https://www.zaproxy.org/download/)


#### CWE Id: [ 1104 ](https://cwe.mitre.org/data/definitions/1104.html)


#### WASC Id: 45

#### Source ID: 3

### [ A Client Error response code was returned by the server ](https://www.zaproxy.org/docs/alerts/100000/)



##### Informational (High)

### Description

A response code of 400 was returned by the server.
This may indicate that the application is failing to handle unexpected input correctly.
Raised by the 'Alert on HTTP Response Code Error' script

* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote

  * Method: `DELETE`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote/

  * Method: `DELETE`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/._darcs

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.bzr

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.DS_Store

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.git/config

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.hg

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.idea/WebServers.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.php_cs.cache

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.ssh/id_dsa

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.ssh/id_rsa

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.svn/entries

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.svn/wc.db

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/.zap5349958077613650188

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/757630518054395713

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/_framework/blazor.boot.json

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/_wpeprivate/config.json

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/adminer.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/2218623565641173768

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/1895313863237103172

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/796947862374826639

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//actuator/health

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags/871049201282037427

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%252Bresponse.write%252841%252C115*483%252C786%2529%252B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%252F%253E%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2522java.lang.Thread.sleep%2522%252815000%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2523%257B%2525x%2528sleep+15%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2523%257Bglobal.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2523set%2528%2524engine%253D%2522%2522%2529%250A%2523set%2528%2524proc%253D%2524engine.getClass%2528%2529.forName%2528%2522java.lang.Runtime%2522%2529.getRuntime%2528%2529.exec%2528%2522sleep+15%2522%2529%2529%250A%2523set%2528%2524null%253D%2524proc.waitFor%2528%2529%2529%250A%2524%257Bnull%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2524%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2527%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2527%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2527case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2528DBMS_SESSION.SLEEP%252815%2529%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%2529%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%252Bresponse.write%2528%257B0%257D*%257B1%257D%2529%252B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%252Fflags

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%252FWEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2523assign+ex%253D%2522freemarker.template.utility.Execute%2522%253Fnew%2528%2529%253E+%2524%257B+ex%2528%2522sleep+15%2522%2529+%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2525%253D%2525x%2528sleep+15%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253C%2525%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cimg%2520src=%2522random.gif%2522%2520onerror=alert(5397&29%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253CscrIpt%253Ealert%25281%2529%253B%253C%252FscRipt%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cscript%253Ealert(5397&29%253C/script%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cxsl%253Avalue-of+select%253D%2522document%2528%2527http%253A%252F%252Fapi-gateway%253A22%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cxsl%253Avalue-of+select%253D%2522php%253Afunction%2528%2527exec%2527%252C%2527erroneous_command+2%253E%2526amp%253B1%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%253Cxsl%253Avariable+name%253D%2522rtobject%2522+select%253D%2522runtime%253AgetRuntime%2528%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522process%2522+select%253D%2522runtime%253Aexec%2528%2524rtobject%252C%2527erroneous_command%2527%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522waiting%2522+select%253D%2522process%253AwaitFor%2528%2524process%2529%2522%252F%253E%250A%253Cxsl%253Avalue-of+select%253D%2522%2524process%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%255Cflags

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%255CWEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%255D%255D%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%257B%257B%2522%2522.__class__.__mro__%255B1%255D.__subclasses__%2528%2529%255B157%255D.__repr__.__globals__.get%2528%2522__builtins__%2522%2529.get%2528%2522__import__%2522%2529%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%257B%257B%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529+%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%257B%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%257B%257Brange.constructor%2528%2522return+eval%2528%255C%2522global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%255C%2522%2529%2522%2529%2528%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=%257Bsystem%2528%2522sleep+15%2522%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=0W45pz4p

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=4qbjuu3lpalvhj5ddkcwzvbuf3zse9j1n8rauc0x3hyy1t9bzdodtodt

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=5%253BURL%253D%2527https%253A%252F%252F2523400780898781728.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=5%253BURL%253D%2527https%253A%252F%252F2523400780898781728.owasp.org%252F%253FOPEN%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%250D%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%250D%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%253F%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%253F%250D%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=any%253F%250D%250ASet-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=c%253A%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=c%253A%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=c%253A%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=c%253A%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+randomblob%2528100000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+randomblob%25281000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+randomblob%252810000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+randomblob%2528100000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+randomblob%25281000000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=cat+%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=eho4ik957nfo8woveths7668ydqcbfxu5cb6uht3b2w3e3mm1l2rknx9dih8

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=flags

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=get-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252F%255C2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252Fwww.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252Fwww.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252Fwww.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252Fwww.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=http%253A%252F%252Fwww.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=https%253A%252F%252F%255C2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=https%253A%252F%252F2523400780898781728%25252eowasp%25252eorg

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=https%253A%252F%252F2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=https%253A%252F%252F2523400780898781728.owasp.org%252F%253FOPEN

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=javascript:alert(5397&29

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%2526cat+%252Fetc%252Fpasswd%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%2526sleep+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%2526timeout+%252FT+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%253Bcat+%252Fetc%252Fpasswd%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%253Bsleep+15.0%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+%252F+sleep%252815%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+AND+%25221%2522%253D%25221

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+AND+%25221%2522%253D%25221%2522+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2522+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2526cat+%252Fetc%252Fpasswd%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2526sleep+15.0%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2526timeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2526type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2526cat+%252Fetc%252Fpasswd%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2526sleep+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2526timeout+%252FT+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%253Bcat+%252Fetc%252Fpasswd%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%253Bsleep+15.0%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+%252F+sleep%252815%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+AND+%25271%2527%253D%25271

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+AND+%25271%2527%253D%25271%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2527+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bcat+%252Fetc%252Fpasswd%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bget-help+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bsleep+15.0%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%253Bstart-sleep+-s+15.0+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN&class.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+%252F+case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+%252F+sleep%252815%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+AND+1%253D1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+AND+1%253D1+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+and+exists+%2528DBMS_SESSION.SLEEP%252815%2529%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+or+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=qagy6f26jsid37vag36tu523fd6jmnyh6w885euqzcrqqta48kdv9d1ps

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=response.write%252841%252C115*483%252C786%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=Set-cookie%253A+Tamper%253D464831c7-e029-4697-b116-3ae1c2289aa1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=system-property%2528%2527xsl%253Avendor%2527%2529%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=thishouldnotexistandhopefullyitwillnot

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=ucYGFloHJLYqgyBEHBTHIgLXJYPmrBaLZYpJMEIIONoIWHCAnrDnfQUZWvdZYLQdRGLBcFgiZqtrCUHxAONcCKMCOYplHchOplAXKCUiepqAQWXxTVChsnPdSfBmewaYnVUqaColhjOFBvApRjdYaPCbCDBmJUpUvKkKkEmbZSgsqnAOTeuwiGFJBYpQEiXIrlCdSZkFuJAsyirGHmaUVjFReeZfpJXNqYxmETrwVdUbtvEjbFLPDFsaNATuFVWKCjpehkdKWMYiYgyLyLXNOnAyVJIfMjdWKtbAqBDmjGodyVePqgMeahBCPaLgmxlxvfNCiDdAAKOZONRDLvweVvBitEWosyqhCOERUjyGJWRxoeRZbqvGtIaJZvmuNEeEmaIUGbLvSLTDZGhotPxkdZygEJnSVsjpXjIOvVVCYxYGjNAQHIGWEBqLWMjUNcNEtqZCKxmYOkXfynZDCkdVXyIiAjrKSfWOItcTambOcXcCWLfaEVbvlwZKlwcJpuEuTowdInMNtWFCaNlUhNUdDWxuiPquJQodUkIpFkLAjnFEpYTgEvFJriRbMXnPTpeAhNEqhnDYuKjtTmtEZDJqpKACOdYOZZEapenSprYLvYVQMCySpDgmYBoDmNRnEVZrBwUcDVIyyJhRZBBCRSQsmqYKxdbOBALIhmRNnTAqvtcjKhpFKwPxDjheyGqySwJsrwcSUkncGHUxDbjLKMOVqmhVpBxJAZjOdYlwfoucPjYwAacVxnUSVrOWDCrlfyPOYgGIaIdpTgTumYLiatnPohRRTAqvOqirGWVmMldZyedtYIoOUDofQibJcqngfhoKHUAoumGQBCVBWrjVDlMceLXClIJjXccAQMZmEEhIbFaRcwQGsIdTAiCIFprOGmJTWLOFqMvruBVaqkVKEAUHLiIfreYSkMPfAdhHmtOUrojrAeHSrZPJhqSLfWCHbeRZYEFToKGqqsvlIaKnDcUqFJMExybSVRnrLunZkbPrrqpdEUsdnURIuUtwymRGTNNFTgKALeHDqNDssGELcSdwClpxMmoVpkxqgucvfmhEfWGUVoHILuxqpIbQfOZNuiKdmPiARQYvkjHYNMQucscElUGoiNRIQtjdWBSGOWcTXewRSSPWmXwXpppyNsQbFUnvhXXxEjckJQssKMlvoHxXhoOlXPQqgoZOWDKKZtHGKbJSwtrkEkjmUHjcxOepxgWdDlCrXNGLvmyehXHSgqAlTmLghVpSanwOuvbVUJnFUFFBPiRIwAsjWkdRfsxnhTuYAqMNVWleilFWYMvleEGyjrHaPuToMUncNbDLlHlAGuNhPpQbRbqXmnrBUrwIJDGUmtylgAXiBSgJYBPhyVENdQLoOQttOyIJUlaIMKDjKUTTGnMtjkhhmGHZWXDpEMbGHBUucAJgBHayCBkXvYBhxZCeqaDFUcsuSIHorFMtGLZDRXmJNXjrYOrmGJvVYKtrUqUqrNfSncRqYGhqadMCJFNXstWslkrjwHfZJRObjRsftmIoaKgCZAPFbrHJywoOcZJocMHZKdTbhysuUpaEeNPEWJjpYkQxxXmAYyxhSoEKLGfEcplYkdnxHphthKuBIsWBPXPnqpsBatToMSYTYiLsQPjdXrZqnxHutiQsaaRIrZmuuDOOsbBVCQViAkfSFkOXgYSnZOQpeTwclKVgtRGfSdSOvYXtCnVxbZliXokYQBxYoGNJNqktmBlloGthcdGHycMQFmFbtNZjScRspMQSHvYoTAelgXYCZgYUcdCCqUKVFDKddVqZkBWWIpYfahfDumtDgIHLsEUjAaICopNskTPsyURpcxjyRxRLmKjgBuSwdQwjsPgWEjaJtXUUKhcTvcAjlgaBaaDmPHDMtXtFoGlFDQpogqJhQRyEjEHWPoBqNXMOeJjGxDmrXZmNBjsvJqwCxqwkUVdZaQXLiCgkHtvtlKCmQIMDugfXhwlbjtjMMPsUbRBpJbVhbPVHPJpNuJuiIxqsKlouxgnPIuDOPYNXyGZJmAZdUklOUrIBBMNbrqUMLxfrQNkYBWGxxhRtCHYILfKMPnwUcqGIThMmkMbjflNkYXnvBalkhDfytMywmumu

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=URL%253D%2527http%253A%252F%252F2523400780898781728.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=WEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=WEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=www.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=www.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=www.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=www.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=www.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=ZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=ZAP%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=ZAP+%25251%2521s%25252%2521s%25253%2521s%25254%2521s%25255%2521s%25256%2521s%25257%2521s%25258%2521s%25259%2521s%252510%2521s%252511%2521s%252512%2521s%252513%2521s%252514%2521s%252515%2521s%252516%2521s%252517%2521s%252518%2521s%252519%2521s%252520%2521s%252521%2521n%252522%2521n%252523%2521n%252524%2521n%252525%2521n%252526%2521n%252527%2521n%252528%2521n%252529%2521n%252530%2521n%252531%2521n%252532%2521n%252533%2521n%252534%2521n%252535%2521n%252536%2521n%252537%2521n%252538%2521n%252539%2521n%252540%2521n%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zApPX9sS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%2523%257B8194*1948%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%2523set%2528%2524x%253D6232*9823%2529%2524%257Bx%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%2524%257B7568*6699%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%253C%2525%253D2988*2475%2525%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%253Cp+th%253Atext%253D%2522%2524%257B6340*7096%257D%2522%253E%253C%252Fp%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%25233527*3176%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%25403460*7517%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%2540math+key%253D%25222218%2522+method%253D%2522multiply%2522+operand%253D%25225166%2522%252F%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%257B%253D3616*4944%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%257B1551*3452%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%257B81100%257Cadd%253A15560%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B%257Bprint+%25229057%2522+%25229795%2522%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj%257B9459*9054%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=zj+9251*9811+zj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%252Bresponse.write%2528417%252C684*574%252C205%2529%252B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%252F%253E%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2522java.lang.Thread.sleep%2522%252815000%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2523%257B%2525x%2528sleep+15%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2523%257Bglobal.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2523set%2528%2524engine%253D%2522%2522%2529%250A%2523set%2528%2524proc%253D%2524engine.getClass%2528%2529.forName%2528%2522java.lang.Runtime%2522%2529.getRuntime%2528%2529.exec%2528%2522sleep+15%2522%2529%2529%250A%2523set%2528%2524null%253D%2524proc.waitFor%2528%2529%2529%250A%2524%257Bnull%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2524%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2527%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2527%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2527case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2528DBMS_SESSION.SLEEP%252815%2529%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%2529%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%252Bresponse.write%2528%257B0%257D*%257B1%257D%2529%252B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%252Fmoderation-log

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%252FWEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2523assign+ex%253D%2522freemarker.template.utility.Execute%2522%253Fnew%2528%2529%253E+%2524%257B+ex%2528%2522sleep+15%2522%2529+%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2525%253D%2525x%2528sleep+15%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253C%2525%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cimg%2520src=%2522random.gif%2522%2520onerror=alert(5397&29%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253CscrIpt%253Ealert%25281%2529%253B%253C%252FscRipt%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cscript%253Ealert(5397&29%253C/script%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cxsl%253Avalue-of+select%253D%2522document%2528%2527http%253A%252F%252Fapi-gateway%253A22%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cxsl%253Avalue-of+select%253D%2522php%253Afunction%2528%2527exec%2527%252C%2527erroneous_command+2%253E%2526amp%253B1%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%253Cxsl%253Avariable+name%253D%2522rtobject%2522+select%253D%2522runtime%253AgetRuntime%2528%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522process%2522+select%253D%2522runtime%253Aexec%2528%2524rtobject%252C%2527erroneous_command%2527%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522waiting%2522+select%253D%2522process%253AwaitFor%2528%2524process%2529%2522%252F%253E%250A%253Cxsl%253Avalue-of+select%253D%2522%2524process%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%255Cmoderation-log

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%255CWEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%255D%255D%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%257B%257B%2522%2522.__class__.__mro__%255B1%255D.__subclasses__%2528%2529%255B157%255D.__repr__.__globals__.get%2528%2522__builtins__%2522%2529.get%2528%2522__import__%2522%2529%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%257B%257B%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529+%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%257B%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%257B%257Brange.constructor%2528%2522return+eval%2528%255C%2522global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%255C%2522%2529%2522%2529%2528%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=%257Bsystem%2528%2522sleep+15%2522%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=0W45pz4p

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=100%252F2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=5%253BURL%253D%2527https%253A%252F%252F2523400780898781728.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=5%253BURL%253D%2527https%253A%252F%252F2523400780898781728.owasp.org%252F%253F50%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%2526cat+%252Fetc%252Fpasswd%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%2526sleep+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%2526timeout+%252FT+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%253Bcat+%252Fetc%252Fpasswd%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%253Bsleep+15.0%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+%252F+sleep%252815%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+AND+%25221%2522%253D%25221

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+AND+%25221%2522%253D%25221%2522+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2522+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2526cat+%252Fetc%252Fpasswd%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2526sleep+15.0%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2526timeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2526type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2526cat+%252Fetc%252Fpasswd%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2526sleep+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2526timeout+%252FT+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%253Bcat+%252Fetc%252Fpasswd%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%253Bsleep+15.0%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+%252F+sleep%252815%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+AND+%25271%2527%253D%25271

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+AND+%25271%2527%253D%25271%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2527+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bcat+%252Fetc%252Fpasswd%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bget-help+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bsleep+15.0%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%253Bstart-sleep+-s+15.0+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50&class.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+%252F+case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+%252F+sleep%252815%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+AND+1%253D1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+AND+1%253D1+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+and+exists+%2528DBMS_SESSION.SLEEP%252815%2529%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+or+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=52-2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%250D%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%250D%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%253F%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%253F%250D%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=any%253F%250D%250ASet-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=c%253A%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=c%253A%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=c%253A%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=c%253A%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+randomblob%2528100000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+randomblob%25281000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+randomblob%252810000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+randomblob%2528100000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+randomblob%25281000000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=cat+%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=get-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252F%255C2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252Fwww.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252Fwww.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252Fwww.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252Fwww.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=http%253A%252F%252Fwww.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=https%253A%252F%252F%255C2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=https%253A%252F%252F2523400780898781728%25252eowasp%25252eorg

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=https%253A%252F%252F2523400780898781728.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=https%253A%252F%252F2523400780898781728.owasp.org%252F%253F50

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=javascript:alert(5397&29

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=moderation-log

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=nhldoJstuipwvnqZOPyTvMGmHJFmwlQHJENiLqBZYPvxGnwFawMuFCyoqJJMYrRLtaVOVwrFUeYWSFSfBLOwRMWAaUKWTqivjkxjyFWLsvHmNwoKxLBuhnKATowEqmZlQHUXkTyqtDaFGOSLgUTujdUIqbTlyrdOMETXkqEYhhjNyOxjAgjRBvZemAoltEhTqwLbhASolNlNLWjsmBVAWUhtNtdSVDdFMxMQutKnaTfpbLHIPoGwqesLSNNChGSQkFaDDgNqroMAdWVqAdxddWGJiLECyNAshRGuFgdVpiNEABNerFVakyFGFHoQsVRZoSFtCHJYRyJjGKqtqYDVEfuZRNbNInyYLucZkFddTTKIMbTahQasnOSUtCesqFhiWrnvMKZIcHyWDQYTbjGKHyMWTVSySNwZKjBvSLWVEjcJWXoetNKFqEQmZcdeClHxTIyXHtopnaiIFKoreRGMXRAsjwfUkoPQTOgmcsuSrSduhWmEKjDySVZDcAKiaIFgdtHHGBrExkXcIMkTwFyJwRYOriOArvMEyTxoGOArhhDwKCwELchmvXLFhLUmSEhaCoQPhGfigTlMxdiILxtLTHZcItpAUUUCiuXjtCjqgiKgyqZkCTFjsclkvrcMKWtfBmabGoJUZiEasGBDjsLBKkJJskGRgpWiQDgyyIxbsBCBcZPLeXHTMIlGytIkRcIXttBkBBcMTOSdXyrOnLGndhprPYZkilxooYSNoJPoBUksJwuJRpdFVhyqpdNGYRwbCLDlkUdfBwbGIRZgyYHfqlaBGQoiFirfCdaVvWowXCQdpvjktHMOHCMgixAiBOCpBUIUMDCZQQSKTHsZfnDUktWrRQyXMekHBYhbqETerOcWEpvNiCDkAVZRYblEQUHklwAQntwrViyhYCabmVruVeGFnFAxdKQWMRRNKyYEtyJhICRmUOZHxvIOKfpuVHWtrjakwekBuHuXbjLNZxQJXmxjgoMIaswjWDDxhENgAEkNRvKkCMgYvBqQqdYVNsspWPOZaILcbcvtJnfjfMWOiRswWHBygPaOtPhcgTimdJvCoaXfmXyBapjhVAwRZBwAHvyPyrZMZEiqhyZupNGpVhMxguoUOhMZEjQIUTHkqWjDgfeqPtthMHUNPicDxSmquGdkUxiFnFqJhhKxOYsOaRoChKBMltSKnocItPDAGTfLAodlPMkjYPkrHVLEYSujlxAaphtbJhUiGsdTvoZbyDdILXjxUmcUjFicPJTinWCTstAqIKZAbcrVBwgHuaIkkmgpYwUNyIvNXPgTFWhfjyjWgIXuqWbWMbZSGuKmXUNCMChGFFHfNtrwcVQKKSFWdGJtCtWFgWPlwBvgRYYxuImAxvIRjxGYPXMWFFTbofifarBSYFeZxBSCVfUginyCCmjoiZBYEQibKLIEWNhGDCpSOnVAQrCNTNRHKVOrDqBZPkPPQOtHjTmlUrpLmiPErMPYCUYloUKvttrvnZrXvjKEUuEQWWWdXBcpDMxAAaPFGWkwJuyrNLDiMxXNJecTpYorasyaSQQlOLdBMsEhjrvglGhnWRmFAbJaTxlyXIrRwNrOcHrReQCOUZOUuHPmyLbVZkQDdgPwFivhISoiWyAhEBfXfuMihpmmxYOGeruPvKMbUELySCnelinKaGUkwtRDOCoXCtxEkTneHPIgpwBbLnkhxZElWanshJcCmlBDeTvrdtknooBGenTBOkWSLYJBMUfwVuQZpGnPnvuXHNnxVtcvKggfKXRffTRBZdNKshIWafZNnpmeQfCdChhexrYEMacZyCEHWnTPjBwvNfUqoWQavTuLNlWqJHoGOfFNhHcinbVxwrNRTbadELCWZSabtxfGXOIFuixUAyjtvUiMWOtmoOXNBeweqhOKFWUntCxjGiJeLSyRFFqATyIAitFCwcBKyknegPPPQHWWaIRQBVlhwgZxhjDastsysmnFwgkjsfbLoawstDMhalluIsgxJmvYpSrHenwHlGfSbNUCCUbmJgXdpSxJAhHJTCmRNehVObFETBPlXIAiBBxkiVrOpjegErqZJBncVwprGTPvQbpoGFGeTcWBEeFLyUsjowoakxIF

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=response.write%2528417%252C684*574%252C205%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=s3uzgbbh21w4km2ou441owrel2wv8z8kpatmdytmz9kaiz5mtdslflz4c

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=Set-cookie%253A+Tamper%253D25b1134b-fc88-4cdd-aa18-e5d821490009

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=system-property%2528%2527xsl%253Avendor%2527%2529%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=thishouldnotexistandhopefullyitwillnot

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=URL%253D%2527http%253A%252F%252F2523400780898781728.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=WEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=WEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=www.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=www.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=www.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=www.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=www.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=ZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=ZAP%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=ZAP+%25251%2521s%25252%2521s%25253%2521s%25254%2521s%25255%2521s%25256%2521s%25257%2521s%25258%2521s%25259%2521s%252510%2521s%252511%2521s%252512%2521s%252513%2521s%252514%2521s%252515%2521s%252516%2521s%252517%2521s%252518%2521s%252519%2521s%252520%2521s%252521%2521n%252522%2521n%252523%2521n%252524%2521n%252525%2521n%252526%2521n%252527%2521n%252528%2521n%252529%2521n%252530%2521n%252531%2521n%252532%2521n%252533%2521n%252534%2521n%252535%2521n%252536%2521n%252537%2521n%252538%2521n%252539%2521n%252540%2521n%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zApPX10sS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%2523%257B4713*2805%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%2523set%2528%2524x%253D1673*7815%2529%2524%257Bx%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%2524%257B4396*9843%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%253C%2525%253D5656*5511%2525%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%253Cp+th%253Atext%253D%2522%2524%257B2548*7607%257D%2522%253E%253C%252Fp%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%25235068*6137%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%25402384*4492%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%2540math+key%253D%25227399%2522+method%253D%2522multiply%2522+operand%253D%25223376%2522%252F%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%257B%253D9496*8266%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%257B51800%257Cadd%253A39570%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%257B9626*9577%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B%257Bprint+%25225145%2522+%25226688%2522%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj%257B8522*4311%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=zj+8171*5403+zj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/3645528967766278567

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/3856354028242015787

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/6171573618036485823

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/blocked/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/6207673946656107152

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/incoming/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/outgoing/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//votes

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//votes/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//votes%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents/2689233502625653437

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/app/etc/local.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/BitKeeper

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/CHANGELOG.txt

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/composer.json

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/composer.lock

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/config/database.yml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/config/databases.yml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/core

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/CVS/root

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/DEADJOE

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/elmah.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/favicon.ico

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/filezilla.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/i.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/id_dsa

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/id_rsa

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/info.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/key.pem

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/lfm.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/myserver.key

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/phpinfo.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/privatekey.key

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/server-info

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/server-status

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/server.key

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/sftp-config.json

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/sitemanager.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/sites/default/files/.ht.sqlite

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/sites/default/private/files/backup_migrate/scheduled/test.txt

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/test.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/vb_test.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/vim_settings.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/applicationContext.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/classes/09/729.class

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/classes/09/739.class

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/classes/applicationContext/xml.class

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/classes/web/xml.class

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/web.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/winscp.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WS_FTP.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/zap5254731813105553862

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/blocked

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/blocked%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/incoming

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/incoming%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/outgoing

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/outgoing%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//votes%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/computeMetadata/v1/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/latest/meta-data/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/metadata/instance

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/opc/v1/instance/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``


Instances: 648

### Solution



### Reference



#### CWE Id: [ 388 ](https://cwe.mitre.org/data/definitions/388.html)


#### WASC Id: 20

#### Source ID: 4

### [ Non-Storable Content ](https://www.zaproxy.org/docs/alerts/10049/)



##### Informational (Medium)

### Description

The response contents are not storable by caching components such as proxy servers. If the response does not contain sensitive, personal or user-specific information, it may benefit from being stored and cached, to improve performance.

* URL: http://api-gateway:8080/api/v1/incidents//vote

  * Method: `DELETE`
  * Parameter: ``
  * Attack: ``
  * Evidence: `DELETE `
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests/outgoing

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `authorization:`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//votes

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `authorization:`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//comments

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `authorization:`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//flag

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `authorization:`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags//resolve

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `PUT `
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//accept

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `PUT `
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts//block

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `PUT `
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/incidents//vote

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `PUT `
  * Other Info: ``


Instances: 12

### Solution

The content may be marked as storable by ensuring that the following conditions are satisfied:
The request method must be understood by the cache and defined as being cacheable ("GET", "HEAD", and "POST" are currently defined as cacheable)
The response status code must be understood by the cache (one of the 1XX, 2XX, 3XX, 4XX, or 5XX response classes are generally understood)
The "no-store" cache directive must not appear in the request or response header fields
For caching by "shared" caches such as "proxy" caches, the "private" response directive must not appear in the response
For caching by "shared" caches such as "proxy" caches, the "Authorization" header field must not appear in the request, unless the response explicitly allows it (using one of the "must-revalidate", "public", or "s-maxage" Cache-Control response directives)
In addition to the conditions above, at least one of the following conditions must also be satisfied by the response:
It must contain an "Expires" header field
It must contain a "max-age" response directive
For "shared" caches such as "proxy" caches, it must contain a "s-maxage" response directive
It must contain a "Cache Control Extension" that allows it to be cached
It must have a status code that is defined as cacheable by default (200, 203, 204, 206, 300, 301, 404, 405, 410, 414, 501).

### Reference


* [ https://datatracker.ietf.org/doc/html/rfc7234 ](https://datatracker.ietf.org/doc/html/rfc7234)
* [ https://datatracker.ietf.org/doc/html/rfc7231 ](https://datatracker.ietf.org/doc/html/rfc7231)
* [ https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html)


#### CWE Id: [ 524 ](https://cwe.mitre.org/data/definitions/524.html)


#### WASC Id: 13

#### Source ID: 3

### [ User Agent Fuzzer ](https://www.zaproxy.org/docs/alerts/10104/)



##### Informational (Medium)

### Description

Check for differences in response based on fuzzed User Agent (eg. mobile sites, access as a Search Engine Crawler). Compares the response statuscode and the hashcode of the response body with the original response.

* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/

  * Method: `DELETE`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/flags%3Fstatus=OPEN

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/metrics

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/moderation-log%3Flimit=50

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/comments/commentId/flag

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/contacts/requests

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``


Instances: 180

### Solution



### Reference


* [ https://owasp.org/wstg ](https://owasp.org/wstg)



#### Source ID: 1


