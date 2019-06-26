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

## Enable Tracing

https://docs.microsoft.com/en-us/aspnet/web-api/overview/testing-and-debugging/tracing-in-aspnet-web-api

```
PM> Install-Package Microsoft.AspNet.WebApi.Tracing
PM> Update-Package Microsoft.AspNet.WebApi.WebHost

Add in WebApiConfig.Register(HttpConfiguration config):
config.EnableSystemDiagnosticsTracing();
