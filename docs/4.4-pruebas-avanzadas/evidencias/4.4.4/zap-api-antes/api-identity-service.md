# ZAP Scanning Report

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 1 |
| Medium | 0 |
| Low | 4 |
| Informational | 5 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Path Traversal | High | 1 |
| A Server Error response code was returned by the server | Low | 2 |
| Insufficient Site Isolation Against Spectre Vulnerability | Low | 6 |
| Unexpected Content-Type was returned | Low | 10 |
| ZAP is Out of Date | Low | 1 |
| A Client Error response code was returned by the server | Informational | 462 |
| Authentication Request Identified | Informational | 1 |
| Information Disclosure - Sensitive Information in URL | Informational | 1 |
| Non-Storable Content | Informational | 12 |
| User Agent Fuzzer | Informational | 264 |




## Alert Detail



### [ Path Traversal ](https://www.zaproxy.org/docs/alerts/6/)



##### High (Low)

### Description

The Path Traversal attack technique allows an attacker access to files, directories, and commands that potentially reside outside the web document root directory. An attacker may manipulate a URL in such a way that the web site will execute or reveal the contents of arbitrary files anywhere on the web server. Any device that exposes an HTTP-based interface is potentially vulnerable to Path Traversal.

Most web sites restrict user access to a specific portion of the file-system, typically called the "web document root" or "CGI root" directory. These directories contain the files intended for user access and the executable necessary to drive web application functionality. To access files or execute commands anywhere on the file-system, Path Traversal attacks will utilize the ability of special-characters sequences.

The most basic Path Traversal attack uses the "../" special-character sequence to alter the resource location requested in the URL. Although most popular web servers will prevent this technique from escaping the web document root, alternate encodings of the "../" sequence may help bypass the security filters. These method variations include valid and invalid Unicode-encoding ("..%u2216" or "..%c0%af") of the forward slash character, backslash characters ("..\") on Windows-based servers, URL encoded characters "%2e%2e%2f"), and double URL encoding ("..%255c") of the backslash character.

Even if the web server properly restricts Path Traversal attempts in the URL path, a web application itself may still be vulnerable due to improper handling of user-supplied input. This is a common problem of web applications that use template mechanisms or load static text from files. In variations of the attack, the original URL parameter value is substituted with the file name of one of the web application's dynamic scripts. Consequently, the results can reveal source code because the file is interpreted as text instead of an executable script. These techniques often employ additional special characters such as the dot (".") to reveal the listing of the current working directory, or "%00" NULL characters in order to bypass rudimentary file extension checks.

* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `PUT`
  * Parameter: `phoneNumber`
  * Attack: `me`
  * Evidence: ``
  * Other Info: ``


Instances: 1

### Solution

Assume all input is malicious. Use an "accept known good" input validation strategy, i.e., use an allow list of acceptable inputs that strictly conform to specifications. Reject any input that does not strictly conform to specifications, or transform it into something that does. Do not rely exclusively on looking for malicious or malformed inputs (i.e., do not rely on a deny list). However, deny lists can be useful for detecting potential attacks or determining which inputs are so malformed that they should be rejected outright.

When performing input validation, consider all potentially relevant properties, including length, type of input, the full range of acceptable values, missing or extra inputs, syntax, consistency across related fields, and conformance to business rules. As an example of business rule logic, "boat" may be syntactically valid because it only contains alphanumeric characters, but it is not valid if you are expecting colors such as "red" or "blue."

For filenames, use stringent allow lists that limit the character set to be used. If feasible, only allow a single "." character in the filename to avoid weaknesses, and exclude directory separators such as "/". Use an allow list of allowable file extensions.

Warning: if you attempt to cleanse your data, then do so that the end result is not in the form that can be dangerous. A sanitizing mechanism can remove characters such as '.' and ';' which may be required for some exploits. An attacker can try to fool the sanitizing mechanism into "cleaning" data into a dangerous form. Suppose the attacker injects a '.' inside a filename (e.g. "sensi.tiveFile") and the sanitizing mechanism removes the character resulting in the valid filename, "sensitiveFile". If the input data are now assumed to be safe, then the file may be compromised. 

Inputs should be decoded and canonicalized to the application's current internal representation before being validated. Make sure that your application does not decode the same input twice. Such errors could be used to bypass allow list schemes by introducing dangerous inputs after they have been checked.

Use a built-in path canonicalization function (such as realpath() in C) that produces the canonical version of the pathname, which effectively removes ".." sequences and symbolic links.

Run your code using the lowest privileges that are required to accomplish the necessary tasks. If possible, create isolated accounts with limited privileges that are only used for a single task. That way, a successful attack will not immediately give the attacker access to the rest of the software or its environment. For example, database applications rarely need to run as the database administrator, especially in day-to-day operations.

When the set of acceptable objects, such as filenames or URLs, is limited or known, create a mapping from a set of fixed input values (such as numeric IDs) to the actual filenames or URLs, and reject all other inputs.

Run your code in a "jail" or similar sandbox environment that enforces strict boundaries between the process and the operating system. This may effectively restrict which files can be accessed in a particular directory or which commands can be executed by your software.

OS-level examples include the Unix chroot jail, AppArmor, and SELinux. In general, managed code may provide some protection. For example, java.io.FilePermission in the Java SecurityManager allows you to specify restrictions on file operations.

This may not be a feasible solution, and it only limits the impact to the operating system; the rest of your application may still be subject to compromise.


### Reference


* [ https://owasp.org/www-community/attacks/Path_Traversal ](https://owasp.org/www-community/attacks/Path_Traversal)
* [ https://cwe.mitre.org/data/definitions/22.html ](https://cwe.mitre.org/data/definitions/22.html)


#### CWE Id: [ 22 ](https://cwe.mitre.org/data/definitions/22.html)


#### WASC Id: 33

#### Source ID: 1

### [ A Server Error response code was returned by the server ](https://www.zaproxy.org/docs/alerts/100000/)



##### Low (High)

### Description

A response code of 500 was returned by the server.
This may indicate that the application is failing to handle unexpected input correctly.
Raised by the 'Alert on HTTP Response Code Error' script

* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%2522%2500%253CscrIpt%253Ealert%25281%2529%253B%253C%252FscRipt%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `500`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `500`
  * Other Info: ``


Instances: 2

### Solution



### Reference



#### CWE Id: [ 388 ](https://cwe.mitre.org/data/definitions/388.html)


#### WASC Id: 20

#### Source ID: 4

### [ Insufficient Site Isolation Against Spectre Vulnerability ](https://www.zaproxy.org/docs/alerts/90004/)



##### Low (Medium)

### Description

Cross-Origin-Resource-Policy header is an opt-in header designed to counter side-channels attacks like Spectre. Resource should be specifically set as shareable amongst different origins.

* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy@example.com

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa

  * Method: `GET`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password

  * Method: `POST`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `PUT`
  * Parameter: `Cross-Origin-Resource-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 6

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
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `text/html`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users%3Fname=abc

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


Instances: 10

### Solution



### Reference




#### Source ID: 4

### [ ZAP is Out of Date ](https://www.zaproxy.org/docs/alerts/10116/)



##### Low (High)

### Description

The version of ZAP you are using to test your app is out of date and is no longer being updated.
The risk level is set based on how out of date your ZAP version is.

* URL: http://api-gateway:8080/api/v1/admin/users//role

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
* URL: http://api-gateway:8080/.zap1440629997433156558

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/1584466717212306017

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
* URL: http://api-gateway:8080/api/2770156956595508546

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
* URL: http://api-gateway:8080/api/v1/5635328691698805257

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
* URL: http://api-gateway:8080/api/v1/admin/9019362407877962939

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//actuator/health

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users/4215137184182417956

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
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
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/4883267155649037911

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/5582065776151533183

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/7712129891659597951

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3F-s

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%252Bresponse.write%2528828%252C534*415%252C656%2529%252B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%252F%253E%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522%253E%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2522java.lang.Thread.sleep%2522%252815000%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2523%257B%2525x%2528sleep+15%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2523%257Bglobal.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2523set%2528%2524engine%253D%2522%2522%2529%250A%2523set%2528%2524proc%253D%2524engine.getClass%2528%2529.forName%2528%2522java.lang.Runtime%2522%2529.getRuntime%2528%2529.exec%2528%2522sleep+15%2522%2529%2529%250A%2523set%2528%2524null%253D%2524proc.waitFor%2528%2529%2529%250A%2524%257Bnull%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2524%257B%2540print%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%257D%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2524%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%2522%253Cimg+src%253Dx+onerror%253Dprompt%2528%2529%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%2522%253CscrIpt%253Ealert%25281%2529%253B%253C%252FscRipt%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B%2524var%253D%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2527case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2528DBMS_SESSION.SLEEP%252815%2529%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%2529%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%252Bresponse.write%2528%257B0%257D*%257B1%257D%2529%252B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%252Flookup

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%252FWEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253B+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Bprint%2528chr%2528122%2529.chr%252897%2529.chr%2528112%2529.chr%252895%2529.chr%2528116%2529.chr%2528111%2529.chr%2528107%2529.chr%2528101%2529.chr%2528110%2529%2529%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2521--%2523EXEC+cmd%253D%2522dir+%255C%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2521--%2523EXEC+cmd%253D%2522ls+%252F%2522--%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2523assign+ex%253D%2522freemarker.template.utility.Execute%2522%253Fnew%2528%2529%253E+%2524%257B+ex%2528%2522sleep+15%2522%2529+%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2525%253D%2525x%2528sleep+15%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253C%2525%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%2525%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cimg%2520src=%2522random.gif%2522%2520onerror=alert(5397&29%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cscript%253Ealert(5397&29%253C/script%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cxsl%253Avalue-of+select%253D%2522document%2528%2527http%253A%252F%252Fapi-gateway%253A22%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cxsl%253Avalue-of+select%253D%2522php%253Afunction%2528%2527exec%2527%252C%2527erroneous_command+2%253E%2526amp%253B1%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cxsl%253Avalue-of+select%253D%2522system-property%2528%2527xsl%253Avendor%2527%2529%2522%252F%253E%253C%2521--

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%253Cxsl%253Avariable+name%253D%2522rtobject%2522+select%253D%2522runtime%253AgetRuntime%2528%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522process%2522+select%253D%2522runtime%253Aexec%2528%2524rtobject%252C%2527erroneous_command%2527%2529%2522%252F%253E%250A%253Cxsl%253Avariable+name%253D%2522waiting%2522+select%253D%2522process%253AwaitFor%2528%2524process%2529%2522%252F%253E%250A%253Cxsl%253Avalue-of+select%253D%2522%2524process%2522%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%255Clookup

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%255CWEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%255D%255D%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%257B%257B%2522%2522.__class__.__mro__%255B1%255D.__subclasses__%2528%2529%255B157%255D.__repr__.__globals__.get%2528%2522__builtins__%2522%2529.get%2528%2522__import__%2522%2529%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%257B%257B%253D+global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529+%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%257B%257B__import__%2528%2522subprocess%2522%2529.check_output%2528%2522sleep+15%2522%252C+shell%253DTrue%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%257B%257Brange.constructor%2528%2522return+eval%2528%255C%2522global.process.mainModule.require%2528%2527child_process%2527%2529.execSync%2528%2527sleep+15%2527%2529.toString%2528%2529%255C%2522%2529%2522%2529%2528%2529%257D%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=%257Bsystem%2528%2522sleep+15%2522%2529%257D

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252F..%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255C..%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=0W45pz4p

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=5%253BURL%253D%2527https%253A%252F%252F5461601868004964959.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=5%253BURL%253D%2527https%253A%252F%252F5461601868004964959.owasp.org%252F%253Fzaproxy%2540example.com%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=5461601868004964959.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%250D%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%250D%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%253F%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%253F%250D%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=any%253F%250D%250ASet-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f%250D%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=bwugqgntyp3sn6ddhxskfk9nwgpunsoaip4p7xc7v7hr5nzyc7q6mno16gd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=c%253A%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=c%253A%252FWindows%252Fsystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=c%253A%255C

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=c%253A%255CWindows%255Csystem.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+randomblob%2528100000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+randomblob%25281000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+randomblob%252810000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+randomblob%2528100000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+randomblob%25281000000000%2529+when+not+null+then+1+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=cat+%252Fetc%252Fpasswd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=get-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=hkbpmnrrq5x39w1nlzsou51nnkfffvsj9qm6h2qmgqe1bzjn7ka9cr0weh

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252F%255C5461601868004964959.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252Fwww.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252Fwww.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252Fwww.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252Fwww.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=http%253A%252F%252Fwww.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=https%253A%252F%252F%255C5461601868004964959.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=https%253A%252F%252F5461601868004964959%25252eowasp%25252eorg

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=https%253A%252F%252F5461601868004964959.owasp.org

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=https%253A%252F%252F5461601868004964959.owasp.org%252F%253Fzaproxy%2540example.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=javascript:alert(5397&29

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=lookup

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=response.write%2528828%252C534*415%252C656%2529

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=Set-cookie%253A+Tamper%253De730aaec-6c02-4be7-854f-2816691bb23f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=system-property%2528%2527xsl%253Avendor%2527%2529%252F%253E

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=thishouldnotexistandhopefullyitwillnot

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=TNvcLTVQCGveFGXLCGvNjeLjmWwdvoGuJvLOVORCiqaRPOTempBkcyxQPvUEIVWGHEKKoACPJjjJGoeQSdsvFBFXHiVshMwgoytibIPZVmCZUlbQTKckFFHUrvdsFoYcKMsQtUqWojNttBffCdZubYapeiWkTBQJRyEtxNrElNuBHLXkMKSrGDroKlOnKXhnEQmDuZnmOStZvkbGIhGLiJUAuZUjbiTYlgwfrsvVQUMcqflGNCyZhsvwvpVpdljvBEKepNZNWqUTCfNxjiaSXIJyuFnDulOVyomoYkflEMkwEnZkhpSPIDcSoKYIKhIXTocWfxinMfulKNISVhJHLlASPZLXHgrTGVPFPrEYvUwKvgLaEhYhAfiVSMFGATSHZYjkVFFrjIpGjtNoiHsyUkaMJrpVyQWYIegKRLRLhkeHgyONOPqDUcAJpmYSsZUJJVUDGrLWxaYIRkkTdoBRqGyPRZEmhvItDHCxFRmvHHKCsMFNjbvEvJTLAbEbInnDThnikFbYhKkFEabJGkjccnLieSaaBjyjNktQQUeArIccxlGSNHyvrFddihigWdiCvvfnTjmVsxvuLPgaWITMQtiFbXhupTbBGjsCvhiWaRLuMyxCuTmtevfWkgDBDdlqRGEVXUiyktcKPtWAifbHUtCyeAPlTryFtiXwVJkYjVitTIhyBaqBCBCpnBxntPdIUlmjsgGacZlNOPylbmKjFjMAmOoNHWOrchyhOusUJrdojWKDDsHgffOOqyAvFYXtgDohrMqyHIuuNlRAgbIxYgxOUtKjdrNcuWmPjyGUmDUbdRBwgSHMxCgAPyyYGfTBFgUvimTCmppKWajIiiXdThprnyuxBmVpSacylgfbCTEKwvIxIuRhITWEnEHHQkjCUCVswyCDhYCjPhCZliGBThBIDdRTMeiJHRQeGjWgvdpOhUrYwqOqHZDIpykuBlaVJpxZRKYwcnHJSHUekeEwFigMiRoSpcMGiYTnepsivrdCIKppIRjEgjrygpSwJuUXnLQNAFvIauCbPxZLXbOXkNBgyBeCErmHbwUoLKDgLeKHXtcGATFllhBuMjQyDEqtqDxlWKBacacXJrKuOFeHmyhqnwsVgClMJCBmEAPSlKTULodyAlNaGuXoOaQefKkQDWCaVHYiawZTcaPeJCcgSsKbSefFBVDBFkbDsRVleKmlKAmgniFhRMTnbvqkuphxMMbalQYNIyypTUwjIEjOmxifWfsUcqidnjnnuYWkYuvZHESXmBncFAJDuEeWCsawusjuRybgSnTQwqIUtMfptWVBoWAZPnrvxIfPsLWLsEoeQHnLfDYaRgKIZwUxuvWGGsqXJqNMcrcvZFqIwLXfFkSnQTBMnFmIXrCrgAetDxwKCKnwFAaZXtSOXDjqJyrxqiOwamWVoOnXjBtpHmMeHbjkxwoTVoaiGCMwTWxdGRTuMIYmGLcufsCOKdHhBgROQbhFuCyHXAHEiDDkeOplNlisUoJWWPhdpItdAwEWYyfwjwVpNgeVtxMTxkswnlktKtPkJoFhcnosdKanRWNZxafIiwiycUUcmdWmboCISBTablwNBnloarThAWKfREabFNHISHNKFRcjXrJBrGXJwgVIGaqqhLowYpZrRSAdLTGeFpFpPJmnoUbOcKEOUGbDoSQHxLPTrNgulJEZLfCtohKGZyeIhCrkwMvQufPmEOvZMjbmRihGqfKmUdZUbCmToDRYYtkJwLmTsxgVIsRuFKNaKoJDyiItQrDUwUmeyVLoaPDnhEVqPbbGhVFSvjxpRUUZAYPDxIqPxsVaUmqhsKAYBskBfgqeOGoXCQtMiJoarxfZAXOkQFpseQCeqQOCJiKOlogRsQKuloQCvvUQjNISPGWOOiiwipMJorWSLMrfpQpDnpVKKWICiXBRYOOcwgCfmkPUiZchXkeWumenTvkjMbrMQnnrsbjQMafpbpQwDETWZbjlEteIZwTwDBgqqvaJmKmrhgrCmLElOTjyLEdZLespjpMLgDmBuJLbTDFDkVqGcRxkPsNvdGuQQySwFiePQGJPMpfbDIvqXrWLDHnUcGAajEYmvIcyhPVICDPqQWaTNkiW

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=URL%253D%2527http%253A%252F%252F5461601868004964959.owasp.org%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=WEB-INF%252Fweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=WEB-INF%255Cweb.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=www.google.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=www.google.com%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=www.google.com%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=www.google.com%253A80%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=www.google.com%253A80%252Fsearch%253Fq%253DZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=ZAP

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=ZAP%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%2525n%2525s%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=ZAP+%25251%2521s%25252%2521s%25253%2521s%25254%2521s%25255%2521s%25256%2521s%25257%2521s%25258%2521s%25259%2521s%252510%2521s%252511%2521s%252512%2521s%252513%2521s%252514%2521s%252515%2521s%252516%2521s%252517%2521s%252518%2521s%252519%2521s%252520%2521s%252521%2521n%252522%2521n%252523%2521n%252524%2521n%252525%2521n%252526%2521n%252527%2521n%252528%2521n%252529%2521n%252530%2521n%252531%2521n%252532%2521n%252533%2521n%252534%2521n%252535%2521n%252536%2521n%252537%2521n%252538%2521n%252539%2521n%252540%2521n%250A

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zApPX30sS

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%2526cat+%252Fetc%252Fpasswd%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%2526sleep+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%2526timeout+%252FT+15.0%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%253Bcat+%252Fetc%252Fpasswd%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%253Bsleep+15.0%253B%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+%252F+sleep%252815%2529+%252F+%2522

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+AND+%25221%2522%253D%25221

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+AND+%25221%2522%253D%25221%2522+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2522+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2526cat+%252Fetc%252Fpasswd%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2526sleep+15.0%2526

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2526timeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2526type+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2526cat+%252Fetc%252Fpasswd%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2526sleep+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2526timeout+%252FT+15.0%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2526type+%2525SYSTEMROOT%2525%255Cwin.ini%2526%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%253Bcat+%252Fetc%252Fpasswd%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%253Bsleep+15.0%253B%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+%252F+sleep%252815%2529+%252F+%2527

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+AND+%25271%2527%253D%25271

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+AND+%25271%2527%253D%25271%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2527+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529+%2522+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529+%2527+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+%2528

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%2529+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bcat+%252Fetc%252Fpasswd%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bget-help

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bget-help+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bsleep+15.0%253B

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bstart-sleep+-s+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%253Bstart-sleep+-s+15.0+%2523

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%257Ctimeout+%252FT+15.0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com%257Ctype+%2525SYSTEMROOT%2525%255Cwin.ini

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+%252F+%2522java.lang.Thread.sleep%2522%252815000%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+%252F+%2528DBMS_SESSION.SLEEP%252815%2529%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+%252F+case+when+cast%2528pg_sleep%252815.0%2529+as+varchar%2529+%253E+%2527%2527+then+0+else+1+end+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+%252F+sleep%252815%2529+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+and+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+AND+1%253D1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+AND+1%253D1+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+and+exists+%2528+select+%2522java.lang.Thread.sleep%2522%252815000%2529+from+INFORMATION_SCHEMA.SYSTEM_COLUMNS+where+TABLE_NAME+%253D+%2527SYSTEM_COLUMNS%2527+and+COLUMN_NAME+%253D+%2527TABLE_NAME%2527%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+and+exists+%2528DBMS_SESSION.SLEEP%252815%2529%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+or+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+UNION+ALL+select+NULL+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+WAITFOR+DELAY+%25270%253A0%253A15%2527+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com+where+0+in+%2528select+sleep%252815%2529+%2529+--+

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy%2540example.com0W45pz4p

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy@example.com

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy@example.com%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%2523%257B8497*5640%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%2523set%2528%2524x%253D7012*4092%2529%2524%257Bx%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%2524%257B5936*1211%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%253C%2525%253D3998*4811%2525%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%253Cp+th%253Atext%253D%2522%2524%257B7252*2014%257D%2522%253E%253C%252Fp%253Ezj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%25238279*2896%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%25402021*1914%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%2540math+key%253D%25225842%2522+method%253D%2522multiply%2522+operand%253D%25221506%2522%252F%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%257B%253D5257*5639%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%257B36460%257Cadd%253A35690%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%257B5080*5870%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B%257Bprint+%25223314%2522+%25225376%2522%257D%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj%257B4965*6026%257Dzj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zj+5964*7932+zj

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/1746862657241008944

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/8990322647722219266

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/.env

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/.htaccess

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/4745089604537539255

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup%3F-s

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries%3Fname=abc

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/trace.axd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users%3Fclass.module.classLoader.DefaultAssertionStatus=nonsense

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users%3Fname=abc

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
* URL: http://api-gateway:8080/WEB-INF/classes/27/802.class

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/WEB-INF/classes/27/811.class

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
* URL: http://api-gateway:8080/zap686345911624325107

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
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/forgot-password%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `401`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `401`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `409`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy@example.com

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `429`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `429`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `409`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `429`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `409`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `405`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries/

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `415`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users%3F-d+allow_url_include%253d1+-d+auto_prepend_file%253dphp://input

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
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
* URL: http://api-gateway:8080/api/v1/admin/users//role

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `400`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `404`
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


Instances: 462

### Solution



### Reference



#### CWE Id: [ 388 ](https://cwe.mitre.org/data/definitions/388.html)


#### WASC Id: 20

#### Source ID: 4

### [ Authentication Request Identified ](https://www.zaproxy.org/docs/alerts/10111/)



##### Informational (High)

### Description

The given request has been identified as an authentication request. The 'Other Info' field contains a set of key=value lines which identify any relevant fields. If the request is in a context which has an Authentication Method set to "Auto-Detect" then this rule will change the authentication to match the request identified.

* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `email`
  * Attack: ``
  * Evidence: `password`
  * Other Info: `userParam=email
userValue=zaproxy@example.com
passwordParam=password`


Instances: 1

### Solution

This is an informational alert rather than a vulnerability and so there is nothing to fix.

### Reference


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/)



#### Source ID: 3

### [ Information Disclosure - Sensitive Information in URL ](https://www.zaproxy.org/docs/alerts/10024/)



##### Informational (Medium)

### Description

The request appeared to contain sensitive information leaked in the URL. This can violate PCI and most organizational compliance policies. You can configure the list of strings for this check to add or remove values specific to your environment.

* URL: http://api-gateway:8080/api/v1/users/lookup%3Femail=zaproxy@example.com

  * Method: `GET`
  * Parameter: `email`
  * Attack: ``
  * Evidence: `zaproxy@example.com`
  * Other Info: `The URL contains email address(es).`


Instances: 1

### Solution

Do not pass sensitive information in URIs.

### Reference



#### CWE Id: [ 598 ](https://cwe.mitre.org/data/definitions/598.html)


#### WASC Id: 13

#### Source ID: 3

### [ Non-Storable Content ](https://www.zaproxy.org/docs/alerts/10049/)



##### Informational (Medium)

### Description

The response contents are not storable by caching components such as proxy servers. If the response does not contain sensitive, personal or user-specific information, it may benefit from being stored and cached, to improve performance.

* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `no-store`
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users//role

  * Method: `PUT`
  * Parameter: ``
  * Attack: ``
  * Evidence: `PUT `
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

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
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/admin/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/login/mfa

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/register

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/auth/reset-password

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/confirm

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/email-verification/resend

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/interest-zones

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/disable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/enable

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/recovery-codes

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/me/mfa/setup

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://api-gateway:8080/api/v1/users/summaries

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``


Instances: 264

### Solution



### Reference


* [ https://owasp.org/wstg ](https://owasp.org/wstg)



#### Source ID: 1


