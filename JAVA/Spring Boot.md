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
https://blog.csdn.net/xiaozhegaa/article/details/89474544
@Primary：在众多相同的bean中，优先选择用@Primary注解的bean（该注解加在各个bean上）

@Qualifier：在众多相同的bean中，@Qualifier指定需要注入的bean（该注解跟随在@Autowired后）
## 带有参数的构造方法类的装配
## 条件装配Bean
## Bean作用域
## 连接点
https://blog.csdn.net/github_34889651/article/details/51321499
https://blog.csdn.net/sinolover/article/details/104490634
连接点（JoinPoint） 这个就更好解释了，就是spring允许你引用通知（Advice）的地方，那可就真多了，基本每个方法的前、后以及前后都包括，或抛出异常时都可以是连接点，spring只支持方法连接点。其他如AspectJ还可以让你将构造器、属性注入作为连接点。不过那不是咱们关注的，只要记住，和方法有关的前前后后都是连接点，也就是可以引入通知的地方都是连接点。
定义：连接点是一个应用执行过程中能够插入一个切面的点。
连接点可以是调用方法时、抛出异常时、甚至修改字段时、
切面代码可以利用这些点插入到应用的正规流程中
程序执行过程中能够应用通知的所有点。
## 切面
切面（Aspect） 切面是通知和切入点的结合。现在发现了吧，没连接点什么事，连接点就是为了让你好理解切点搞出来的，明白这个概念就行了。通知说明了干什么和什么时候干（什么时候通过方法名中的befor，after，around等就能知道），二切入点说明了在哪干（指定到底是哪个方法），这就是一个完整的切面定义。
定义：切面是通知和切点的集合，通知和切点共同定义了切面的全部功能——它是什么，在何时何处完成其功能。
## 切点
切入点（Pointcut） 上面说的连接点的基础上，来定义切入点，你的一个类里，有15个方法，那就有十几个连接点了对吧，但是你并不想在所有方法附近都使用通知（使用叫织入，下面再说），你只是想让其中几个，在调用这几个方法之前、之后或者抛出异常时干点什么，那么就用切入点来定义这几个方法，让切点来筛选连接点，选中你想要引入通知的方法。
定义：如果通知定义了“什么”和“何时”。那么切点就定义了“何处”。切点会匹配通知所要织入的一个或者多个连接点。
通常使用明确的类或者方法来指定这些切点。
作用：定义通知被应用的位置（在哪些连接点）
## 环绕通知
https://blog.csdn.net/qq_33576276/article/details/88786090
指包围一个连接点通知，在被通知的方法调用之前和之后执行自定义的方法。
## 引入
允许我们向现有的类添加新方法属性。这不就是把切面（也就是新方法属性：通知定义的）用到目标类中吗
## 通知获取参数
## 织入
 为了把切面应用到目标对象，而创建一个新的代理对象的过程。有三种方式，spring采用的是运行时，为什么是运行时，在上一文《Spring AOP开发漫谈之初探AOP及AspectJ的用法》中第二个标提到。
## 默认数据源
https://blog.csdn.net/wangmx1993328/article/details/81834974
Springboot默认支持4种数据源类型，定义在 org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration 中，分别是：
org.apache.tomcat.jdbc.pool.DataSource
com.zaxxer.hikari.HikariDataSource
org.apache.commons.dbcp.BasicDataSource
org.apache.commons.dbcp2.BasicDataSource
对于这4种数据源，当 classpath 下有相应的类存在时，Springboot 会通过自动配置为其生成DataSource Bean，DataSource Bean默认只会生成一个，四种数据源类型的生效先后顺序如下：Tomcat--> Hikari --> Dbcp --> Dbcp2 。
## 自定义数据源
https://www.cnblogs.com/guchunchao/p/10043133.html
## Spring声明式数据库事务约定
## @Transactional的配置项
https://blog.csdn.net/wangmx1993328/article/details/89644934
propagation（传播）事务传播行为，默认值为 Propagation.REQUIRED，它是一个枚举，可选值如下：

REQUIRED：如果当前存在事务，则加入该事务，如果当前不存在事务，则创建一个新的事务。required（必须的）。
SUPPORTS：如果当前存在事务，则加入该事务；如果当前不存在事务，则以非事务方式继续运行。supports（支持的）
MANDATORY：如果当前存在事务，则加入该事务；如果当前不存在事务，则抛出异常。mandatory（强制的）
REQUIRES_NEW：重新创建一个新的事务，如果当前存在事务，暂停当前的事务。requires_new（依赖新的）
NOT_SUPPORTED：以非事务的方式运行，如果当前存在事务，暂停当前的事务。not_supported（不支持的）
NEVER：以非事务的方式运行，如果当前存在事务，则抛出异常。never（从不）
NESTED：和 REQUIRED 效果一样。nested（嵌套）

isolation（隔离）事务隔离级别，默认值为 Isolation.DEFAULT，它是一个枚举，可选择如下：

DEFAULT：使用底层数据库默认的隔离级别。
READ_UNCOMMITTED：未提交读。无法防止。
READ_COMMITTED：可提交读。可以防止脏读。
REPEATABLE_READ：可重复读。可以防止脏读、可重复读。mysql 默认隔离级别。
SERIALIZABLE：串行事务。最高事务隔离级别，可以防止脏读、可重复读、幻读。
## 线程池
https://blog.csdn.net/yu102655/article/details/114846051