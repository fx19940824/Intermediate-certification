# AMQP基础
## AMQP（Advanced Message Queuing Protocol）高级消息队列协议
- 具有现代特征的二进制协议
- 是应用层协议的一个开放标准
- 为面向消息的中间件设计
## 核心概念
- Server：AMQP服务器实体
- Connection：应用程序与Broker的网络连接
- Channel：信道，每个Channel代表一个会话任务
- Message：消息。服务器和应用程序之间传送的数据，本质上是一段数据
- Exchange：交换机。接收消息，根据路由键转发消息到绑定的队列
- Binding：Exchange和Queue之间的虚机连接
- Routing key：虚机地址
- Queue：消息队列，保存消息转发消费者
- VirtualHost：里面可以有若干个Exchange和Queue，**权限控制**的最小粒度

# Exchange
- 接收消息，根据路由键转发消息到绑定的队列
## Exchange类型
### Direct Exchange
### Topic Exchange