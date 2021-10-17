## Bean的定义
- Bean 工厂是工厂模式的一个实现，提供了控制反转功能，用来把应用的配置和依赖从真正的应用代码中分离。最常用的就是org.springframework.beans.factory.xml.XmlBeanFactory ，它根据XML文件中的定义加载beans。该容器从XML 文件读取配置元数据并用它去创建一个完全配置的系统或应用。
## Bean的生命周期
> 在传统的Java应用中，bean的生命周期很简单。使用Java关键字new进行bean实例化，然后该bean就可以使用了。一旦该bean不再被使用，则由Java自动进行垃圾回收。相比之下，Spring容器中的bean的生命周期就显得相对复杂多了。正确理解Spring bean的生命周期非常重要，因为你或许要利用Spring提供的扩展点来自定义bean的创建过程。下图展示了bean装载到Spring应用上下文中的一个典型的生命周期过程。
## Bean的装配方式
Bean的装配可以理解为依赖关系注入，Bean的装配方式即Bean依赖注入的方式。Spring容器支持多种形式的Bean的装配方式，如基于XML的装配、基于注解（Annotation）的装配和自动装配（其中最常用的是基于注解的装配），本文章将主要讲解着三种装配方式的使用。

方式一：设置注入
条件：①Bean类必须有一个无参构造方法；②Bean类必须为属性提供setter方法。

方式二：构造注入
条件：Bean类必须提供有参构造方法

方式三：所谓自动装配，就是将一个Bean自动的注入到到其他Bean的Property中。 Spring的元素中包含一个autowire属性，我们可以通过设置autowire的属性值来自动装配Bean。autowire属性有5个值，其值及说明下表所示

## 面向切面编程
面向切面编程，指扩展功能不修改源代码，将功能代码从业务逻辑代码中分离出来。
主要功能：日志记录，性能统计，安全控制，事务处理，异常处理等等。
主要意图：将日志记录，性能统计，安全控制，事务处理，异常处理等代码从业务逻辑代码中划分出来，通过对这些行为的分离，我们希望可以将它们独立到非指导业务逻辑的方法中，进而改变这些行为的时候不影响业务逻辑的代码。
https://segmentfault.com/a/1190000022220468
## 数据源配置
Spring提供了3种配置数据源（DataSource）的Bean的方式,如下所示：
通过JNDI查找的数据源
连接池数据源
由JDBC驱动程序定义的数据源
Spring提供的嵌入式数据源
https://blog.csdn.net/sujz12345/article/details/53046840
## 容器
## 切面的声明
Spring AOP切面声明方式有注解和xml方式。
https://blog.csdn.net/wangzhengqu/article/details/99053639
## 使用JDBC
https://www.liaoxuefeng.com/wiki/1252599548343744/1282383699509281
## 使用ORM
## 事务管理
事务是一个不可分割操作序列，也是数据库并发控制的基本单位，其执行的结果必须使数据库从一种一致性状态变到另一种一致性状态。
当应用需要在不同的事务策略之间切换时，开发者必须手动修改程序代码。使用Spring事务管理策略，就可以避免这种尴尬。因为Spring的事务管理不需与任何特定的事务API耦合，并且其提供了两种事务管理方式：编程式事务管理和声明式事务管理。对不同的持久层访问技术，编程式事务提供一致的事务编程风格，通过模板化的操作一致性地管理事务；而声明式事务基于Spring AOP实现，却并不需要程序开发者成为AOP专家，亦可轻易使用Spring的声明式事务管理。
Spring 框架中，最重要的事务管理的 API 有三个：TransactionDefinition、PlatformTransactionManager 和 TransactionStatus。 所谓事务管理，实质上就是按照给定的事务规则来执行提交或者回滚操作。
Spring 的声明式事务管理是建立在 Spring AOP 机制之上的，其本质是对目标方法前后进行拦截，并在目标方法开始之前创建或者加入一个事务，在执行完目标方法之后根据执行情况提交或者回滚事务。
https://blog.csdn.net/justloveyou_/article/details/73733278
## 请求处理流程
https://juejin.cn/post/6844903846909575175
1、请求被web 容器接收，并且根据contextPath将请求发送给DispatcherServlet
2、DispatcherServlet接收到请求后，会设置一些属性（localeResolver、themeResolver等等），在根据request在handlerMappings中查找对应的HandlerExecutionChain；然后根据HandlerExecutionChain中的handler来找到HandlerAdapter，然后通过反射来调用handler中的对应方法（RequestMapping对应的方法）
3、handler就是对应的controller，调用controller中的对应方法来进行业务逻辑处理，返回ModelAndView（或者逻辑视图名称）
4、ViewResolver根据逻辑视图名称、视图前后缀，来获取实际的逻辑视图
5、获取实际视图之后，就会使用model来渲染视图，得到用户实际看到的视图，然后返回给客户端。

## 数据转换
https://blog.csdn.net/weixin_36380516/article/details/75370509
在Java的开发中，经常需要进行数据类型的转换，最常见的就是字符型转成Date类型存入数据库。以下介绍三种数据类型转换的方法。

一，使用ConversionService转换数据

二，使用自定义编辑器转换数据

三，注册全局自定义编辑器转换数据

三种数据类型转换器的优先级
对同一个类型的对象，可以用以上任何一种数据转换器来转换他的数据类型，不仅如此，还可以三种一起装配进去，如果装配了三种转换器，springMVC会根据以下顺序查找对应的编辑器：

1，查询通过@InitBinder装配的自定义转换器

2，查询通过ConversionService装配的自定义转换器

3，查询全局WebBindingInitializer自定义编辑器