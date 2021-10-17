## Spring Boot优点
https://www.yiibai.com/spring-boot/pros-cons-of-spring-boot.html
使用Java或Groovy开发基于Spring的应用程序非常容易。
它减少了大量的开发时间并提高了生产力。
它避免了编写大量的样板代码，注释和XML配置。
Spring Boot应用程序与其Spring生态系统(如Spring JDBC，Spring ORM，Spring Data，Spring Security等)集成非常容易。
它遵循“自用默认配置”方法，以减少开发工作量。
它提供嵌入式HTTP服务器，如Tomcat，Jetty等，以开发和测试Web应用程序非常容易。
它提供CLI(命令行界面)工具从命令提示符，非常容易和快速地开发和测试Spring Boot(Java或Groovy)应用程序。
它提供了许多插件来开发和测试Spring启动应用程序非常容易使用构建工具，如Maven和Gradle。
它提供了许多插件，以便与嵌入式和内存数据库工作非常容易。
//更多请阅读：https://www.yiibai.com/spring-boot/pros-cons-of-spring-boot.html


## Spring MVC
首先用户的请求会到达 Servlet，然后根据请求调用相应的 Java Bean，并把所有的显示结果交给 JSP 去完成，这样的模式我们就称为 MVC 模式。

M 代表 模型（Model）
模型是什么呢？ 模型就是数据，就是 dao,bean
V 代表 视图（View）
视图是什么呢？ 就是网页, JSP，用来展示模型中的数据
C 代表 控制器（controller)
控制器是什么？ 控制器的作用就是把不同的数据(Model)，显示在不同的视图(View)上，Servlet 扮演的就是这样的角色。

传统的模型层被拆分为了业务层(Service)和数据访问层（DAO,Data Access Object）。 在 Service 下可以通过 Spring 的声明式事务操作数据访问层，而在业务层上还允许我们访问 NoSQL ，这样就能够满足异军突起的 NoSQL 的使用了，它可以大大提高互联网系统的性能。

作者：我没有三颗心脏
链接：https://www.jianshu.com/p/91a2d0a1e45a
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
## Spring Boot的对比
https://www.yiibai.com/spring-boot/spring-vs-spring-boot-vs-spring-mvc.html
## 依赖和自动配置
## 自定义配置
## IoC容器
https://www.liaoxuefeng.com/wiki/1252599548343744/1282381977747489
IoC全称Inversion of Control，直译为控制反转。
## 注解@Autowired
https://segmentfault.com/a/1190000023810881
首先检测容器内是否有与属性或方法参数类型相匹配的对象，假如有并且只有一个就直接将这个类型的对象生成注入到属性或方法参数中。
## 生命周期
https://zhuanlan.zhihu.com/p/130309481
首先实例化一个SpringApplication类对象然后调用其run方法
其中SpringFactoriesLoader类的loadFactoryNames会读取类路径下所有的META-INF/spring.factories文件里定义的所有接口实现类并缓存起来

定义了很多spring接口的实现类，典型的如ApplicationContextInitializer接口，对于旧的spring项目，如果我们写了ApplicationContextInitializer的实现类，是需要配置在web.xml文件中的，不过Spring Boot是把这些配置放到了META-INF/spring.factories文件，这样就可以被搜索到

上述接口的排序按照下列规则（spring接口实现类的排序基本都适用此规则），这个规则就决定了同一spring接口的多个实现类的执行顺序：

PriorityOrdered是一等公民，首先被执行，PriorityOrdered公民之间通过接口返回值排序
Ordered是二等公民，然后执行，Ordered公民之间通过接口返回值排序
都没有实现是三等公民，最后执行
## 属性文件
## AOP 术语和流程
## 扫描装配Bean
## 自定义第三方Bean
## @Primary和@Quelifier
## 带有参数的构造方法类的装配
## 条件装配Bean
## Bean作用域
## 连接点
## 切面
## 切点
## 环绕通知
## 引入
## 通知获取参数
## 织入
## 默认数据源
## 自定义数据源
## Spring声明式数据库事务约定
## @Transactional的配置项
## 线程池