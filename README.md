### URL Encode Injection (UTF-8)

Basic list of URL encoded UTF-8 characters for injection attacks. These types of attacks allows get bypass of login screens, database dumps, generation of custom payloads URL encode based, and many others results.

* %00
* %01
* %02
* %03
...

### Scope

With this basic list is possible make injections of special characters on web apps, API endpoints, and many other technologies. The purpose of these injections is to intentionally cause errors to obtain unexpected behaviors.

### References

Nowadays, there are no public references because is my own idea to bring null byte injection to the category of brute force or fuzzing process.

However, you can read more about Null Byte Injection and URL encoded attacks:

* https://www.cgisecurity.com/lib/URLEmbeddedAttacks.html
* https://owasp.org/www-community/attacks/Embedding_Null_Code
* https://book.hacktricks.xyz/pentesting-web/file-inclusion#basic-lfi-and-bypasses

### Example

If you have an API endpoint like this /v1/product/some-id/price or whatever similar, you can send the endpoint to Burp Suite Intruder and pass your URL encode dictionary in order to replace §some-id§, and inspect the responses.

§some-id§ can be a uuid, hash or whatever are used insted of "id".

Like null byte injection, the URL Encode Injection can be passed at the beginning or the end of your target entry point: 

* /v1/product/§dictionary§/price
* /v1/product/some-id§dictionary§/price
* /v1/product/§dictionary§some-id/price

### Custom & Advanced Dictionaries

If you want make your own dictionary and delve into the subject, i recommend the following character collection:

* https://www.fileformat.info/info/charset/index.htm
