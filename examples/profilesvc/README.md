# profilesvc

This example demonstrates how to use Go kit to implement a REST-y HTTP service.
It leverages the excellent [gorilla mux package](https://github.com/gorilla/mux) for routing.

此示例演示了如何使用Go kit来实现REST-y HTTP服务。他使用优秀的gorilla mux包进行路由。

Run the example with the optional port address for the service: 

使用服务的可选端口地址运行示例：

```bash
$ go run ./cmd/profilesvc/main.go -http.addr :8080
ts=2018-05-01T16:13:12.849086255Z caller=main.go:47 transport=HTTP addr=:8080
```

Create a Profile:

创建一个 简介/个人资料/配置文件：

```bash
$ curl -d '{"id":"1234","Name":"Go Kit"}' -H "Content-Type: application/json" -X POST http://localhost:8080/profiles/
{}
```

Get the profile you just created

获取您刚刚创建的个人资料

```bash
$ curl localhost:8080/profiles/1234
{"profile":{"id":"1234","name":"Go Kit"}}
```
