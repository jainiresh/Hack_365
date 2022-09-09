# CSTI => Client Side Template Injections

## Vulnerable softwares
 - Angular JS
 - Vue JS
 - JS libraries all that uses client side templates
 

## TESTING
 - Providing {{7*9}} in the suspected input field, and if the multiplication result is published, then the field is susceptible to CSTI
 - Can be escalated to XSS.
 
 
## RESOURCES
 - ANGULAR JS defence bypass can be viewed at 
 ```
 https://book.hacktricks.xyz/pentesting-web/client-side-template-injection-csti
 ```
 
 - The common payload for XSS is :
 ```
 {{this.constructor.constructor('alert(1)')()}}
 ```
 
 which would alert(1)
 
 
 - XSS testing payload in name fields : 
 ```
 xsstest{{'a'.constructor.prototype.charAt=[].join;$eval('x=alert(1)');}}
 ```
 - If the ANGULAR js uses ng-app then there is a high possiblility for CSTI
 
## REPORTS

 - https://hackerone.com/reports/587829
 - https://hackerone.com/reports/1265344
