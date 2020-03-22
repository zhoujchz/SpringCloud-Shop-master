# 基于Spring Boot、Spring Cloud的微服务应用

本项目内容基于Spring Boot、Spring Cloud开发。实现电商应用基础服务，包括用户服务，商品服务，订单服务,功能包括用户注册，用户鉴权，商品列表，商品详情，下单，查看订单列表，订单详情。

- 使用Spring Boot, Spring JPA实现底层服务的CRUD 
- 单元测试，[API测试](https://github.com/suxiongwei/SpringCloud-Shop/blob/master/web-app/src/test/java/com/kedacom/keda/WebAppTest.java) 
- 符合RESTful API规范 
- 实现服务注册发现组件
- 实现服务网关组件
- 实现服务的高可用

## 服务介绍
- api-gateway : 	服务网关       
- eureka-server : 	服务注册中心   
- config-server  : 	分布式配置中心 
- category-service :	 商品服务       
- order-service : 	订单服务       
- user-service  :	 用户服务       
- web-app  :	 web服务       

## 开发环境及项目框架介绍
- IDE: Intellij IDEA
- 缓存服务器(数据库): Redis
- 数据库: MySQL([数据库代码dbkeda.sql](https://github.com/suxiongwei/SpringCloud-Shop/blob/master/dbkeda.sql))
- 项目框架: Spring Boot + Spring Cloud

## 演示步骤
- 1、开启Redis和MySQL服务

- 2、分别启动各个微服务：EurekaServerApplication、ApiGatewayApplication、ConfigServerApplication、CategoryApplication、OrderApplication、UserApplication、WebApplication

- 3、服务调用

  - 方式一：运行单元测试[WebAppTest](https://github.com/suxiongwei/SpringCloud-Shop/blob/master/web-app/src/test/java/com/kedacom/keda/WebAppTest.java)

  - 方式二：通过Postman进行REST URL调用

    商品服务-查看商品详情功能[GET]：http://localhost:8080/web-app/category/introduction/1
  
    返回Json
    
    ```json
    {
        "code": 0,
        "msg": "成功",
        "data": {
            "id": 1,
            "name": "海味",
            "price": 29.99,
            "detail": ""
        }
    }
    ```
    
    用户服务-登录功能[POST]：http://localhost:8080/web-app/users/login?name=admin&password=123456
    
    返回Json
    
    ```json
      {
        "code": 0,
        "msg": "成功",
        "data": null
      }
    ```
    
    其它的接口参见代码路由，在这里不再赘述

## 学习记录
- [微服务框架](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/micro_service.md)
- [Spring Boot](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/spring_boot.md)
- [Spring Session的集成](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/spring_session.md)
- [Spring Boot配置事务管理](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/transactional.md)
- [Spring Cloud:负载均衡Ribbon](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/ribbon.md)
- [Feign声明式服务调用](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/feign.md)
- [Zuul实现微服务网关](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/zuul.md)
- [Config分布式统一配置中心](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/config.md)
- [SpringData-JPA的集成](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/spring/springData-jpa.md)
- [基于ACCESS TOKEN的权限解决方案](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/other/access_token.md)
- [集成redis做缓存](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/redis/redis_cache.md)
- [修改github上仓库的项目语言](https://github.com/suxiongwei/suxiongwei.github.io/tree/master/article/other/github_language.md)
- [Java 微服务框架选型（Dubbo 和 Spring Cloud？）](https://www.cnblogs.com/xishuai/archive/2018/04/13/dubbo-and-spring-cloud.html)

## 参考博客
- [Spring Boot基础教程](http://blog.didispace.com/Spring-Boot%E5%9F%BA%E7%A1%80%E6%95%99%E7%A8%8B/)
- [Spring-Cloud基础教程](http://blog.didispace.com/Spring-Cloud%E5%9F%BA%E7%A1%80%E6%95%99%E7%A8%8B/ )

## 更新日志
### 2019-08-05

#### 变更

* 重新维护项目，将配置文件拆分到单独的配置中心仓库中去
* 去除视图组件，通过REST URL调用（推介[Postman](https://www.getpostman.com/)进行测试）

#### 修复

* 修复依赖无法加载的问题



## 感谢
本项目的代码及功能仍十分简陋，一些功能也是简单的实现，偏重于对微服务的理解及构建微服务的一些组件的使用。但还是收到了很多朋友的Star，十分感谢。
