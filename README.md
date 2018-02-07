Currently the AWS XRAY SDK only [supports tracing of out-going HTTP requests](https://github.com/aws/aws-xray-sdk-dotnet/tree/master#trace-out-going-http-requests-net-and-net-core--nuget) using `HttpWebRequest`

This is a simple class that utilizing the tracing functionality from [here](https://github.com/aws/aws-xray-sdk-dotnet/blob/master/sdk/src/Handlers/System.Net/HttpWebRequestTracingExtension.cs) in a `HttpClientHandler` which can be used with `System.Net.HttpClient`

Usage:
```
var client = new HttpClient(new XRayTracingMessageHandler());
[...]
client.GetAsync(...)
```
