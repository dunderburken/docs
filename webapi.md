## Enable Cors

```
PM> Update-Package Microsoft.AspNet.WebApi.Cors

var cors = new EnableCorsAttribute("*", "*", "*");
config.EnableCors(cors);
```

Or via attribute:

```
[EnableCors("*", "*", "*")]
```
