# 01- Installing Windows AD

1. Scconfig - to Set the hostname, Set the network, Set static IP and setup DNS

```shell
Install-Windows-Feature AD-Domain-Services -IncludeManagementTools

import-Module ADDSDeployment

install-ADDSForest
```
2. Change the DNS from loopback to static DNS
```shell
Get-DNSClientServerAddress
Set-DNSClientServerAddress -InterfaceIndex i -ServerAddress ip
```
3. Adding the host to the domain

   ```shell
   Get-DNSClientServerAddress
   Set-DNSClientServerAddress -InterfaceIndex i -ServerAddress ip
   Add-Computer -DomainName "domain" -Credentials domain/user -Force -Restart
   ```
