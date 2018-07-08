# config-repo
sprig cloud config 指向的配置文件存储位置

#动态刷新下配置功能
在该项目上配置多个webhook,该项目一提交便触发的请求：http://localhost:8091/refresh（可以配置多个）
从而动态刷新所有的配置;

#对以上的改进（上述的缺点）

.打破了微服务的职责单一性。微服务本身是业务模块，它本不应该承担配置刷新的职责。
.破坏了微服务各节点的对等性。
.有一定的局限性。例如，微服务在迁移时，它的网络地址常常会发生变化，此时如果想要做到自动刷新，那就不得不修改WebHook的配置。

改进方法见：http://www.ityouknow.com/springcloud/2017/05/26/springcloud-config-eureka-bus.html