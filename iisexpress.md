# Configure IIS Express in Windows

https://gist.github.com/justingarrick/6322779

```
>netsh http add urlacl url=http://<machinename>:<port>/ user=everyone
>netsh http add urlacl url=http://<machinename>.local:<port>/ user=everyone
>netsh advfirewall firewall add rule name="IISExpressWeb" dir=in action=allow protocol=TCP localport=<port>
```

## List config
```
>netsh http show urlacl
```

## \.vs\config\applicationhost.config

### /sites/bindings/


```
<binding protocol="http" bindingInformation="*:<port>:<machinename>.local" />
```

### /httpProtocol/customHeaders/

```
<add name="Access-Control-Allow-Origin" value="*" />
<add name="Access-Control-Allow-Headers" value="Content-Type" />

