# 1 Spring boot 2.x基础概念
- Spring框架：核心特性是依赖注入DI(Dependency Injection)和空值反转IOC(Inversion Of Control)
- Spring MVC：友好的方式来开发Web应用程序，Dispatcher Servlet、ModelAndView和View Resolver
- Spring Boot：自动配置和starters

- 所有Spring项目默认使用spring-boot-starter-parent作为应用程序的父项目

## 4 lombok注解简化开发
- Data注解：编译器自动生成
    - 成员变量get和set方法
    - equals方法
    - canEqual方法
    - hashCode方法
    - toString方法
- Slf4j注解
- Builder注解
- AllArgsConstructor注解：编译期自动生成全参构造函数
- NoArgsContructor注解：编译期自动生成无参构造函数

# 2 RESTFul接口实现与测试
## 2.1 RESTFul接口与http协议状态表述
- REST通过URI暴露资源时，不要在URI中出现动词，利用HTTP动词来表示对资源的操作
<table>
   <tr>
      <td>不符合REST的接口URI</td>
      <td>符合REST接口URI</td>
      <td>功能</td>
   </tr>
   <tr>
      <td>GET /api/getDogs</td>
      <td>GET /api/dogs/{id}</td>
      <td>获取一个小狗狗</td>
   </tr>
   <tr>
      <td>GET /api/getDogs</td>
      <td>GET /api/dogs</td>
      <td>获取所有小狗狗</td>
   </tr>
   <tr>
      <td>GET /api/addDogs</td>
      <td>POST /api/dogs</td>
      <td>添加一个小狗狗</td>
   </tr>
   <tr>
      <td>GET /api/editDogs/{id}</td>
      <td>PUT /api/dogs/{id}</td>
      <td>修改一个小狗狗</td>
   </tr>
   <tr>
      <td>GET /api/deleteDogs/{id}</td>
      <td>DELETE /api/dogs/{id}</td>
      <td>删除一个小狗狗</td>
   </tr>
</table>

- HTTP状态码
    - 200 OK
    - 400 Bad Request
    - 500 Internal Server Error

### Spring常用注解
1. @RequestBody与@ResponseBody：用于修饰请求参数和返回值，接收HTTP中的body，默认使用JSON格式
2. @RequestMapping
3. @RestController和@Controller
    - @Controller告诉Spring，被注解标注的类是一个Spring的Bean，需要被注入到Spring的上下文环境中
    - 该类里面所有被RequestMapping标注的注解都是HTTP的服务端点
    - @RestController相当于@Controller和@ResponseBody结合
4. @PathVariable和@RequestParam

# 3 spring boot 配置原理
## 3.1 bean自动装配原理
- spring以SpringApplication.run()作为应用程序入口，
- 通过注解或者一些简单的配置就能在 Spring Boot 的帮助下实现某块功能。
- 可以把 @SpringBootApplication看作是 @Configuration、@EnableAutoConfiguration、@ComponentScan 注解的集合