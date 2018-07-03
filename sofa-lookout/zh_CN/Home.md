# SOFALookout 产品介绍

SOFALookout 是蚂蚁金服开源的一款解决系统的度量和监控问题的轻量级中间件服务。它提供的服务包括：Metrics 的埋点、收集、加工、存储与查询等。该开源项目包括了两个独立部分，分别是客户端与服务器端服务。

## 客户端部分

SOFALookout Client 是一个 Java 的 SDK，可以帮助开发者在项目代码中进行 metrics 埋点。通过它也可以查看该 JAVA 应用的实时的状态信息。

```
       +------------------+                      Reg:
 API:  | dimension meters +--------+
       +------------------+        |   flatmap   +---------------------------+
                                   +-----------> |  Default/DropwizardMetrics|
                                   |             +---------------------------+
                                   |
                                   |    http     +--------------+
                                   +-----------> |Lookout server|
                                   |             +--------------+
       +----------------------+    |  add common tags dimension
EXTS:  |   JVM,OS,GC...       +----+
       +----------------------+

```

## 服务器端服务

SOFALookout Server 可以帮助我们解决分布式环境下系统状态度量的问题，它的数据源包括但不限于使用 lookout-client 包的项目。服务端将在下个版本中提供，敬请期待。