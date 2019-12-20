---
layout: post
title: Java开发相关技术知识梳理
categories: Algorithm
description: 有关Java的知识梳理。
keywords: Java
---


@[TOC](Java开发相关技术知识梳理)
## 控制层
		
 -  ####   Spring  
 	- ###### 核心:
 
 		##### 1. IoC：控制反转
 		>DI:依赖注入：Spring在管理某个类的时候会将该类依赖的属性注入（设置）进来，也就是说在创建对象的过程中，向类里面的属性中设置值
 		三种注入方式：(1)接口注入(2)Construct注入(3)Setter注入
 		
 		>底层实现原理:工厂设计模式+反射+XML配置文件
 		
 		##### 2. AOP：面向切面编程
 		>灵活处理一些具有横切性质的系统级服务，如事务处理、安全检查、缓存、对象池管理等
 		
		- 方面（Aspect）：***一个关注点的模块化，这个关注点实现可能另外横切多个对象。事务管理是一个很好的横切关注点例子。方面用Spring的Advisor或拦截器实现， 然后可以通过@Aspect标注或在applictionContext.xml中进行配置***
		
		- 连接点（Joinpoint）：***程序执行过程中的行为，如方法的调用或特定的异常被抛出***
			> String toString();         //连接点所在位置的相关信息  
		    String toShortString();     //连接点所在位置的简短相关信息  
		    String toLongString();     //连接点所在位置的全部相关信息  
		    Object getThis();         //返回AOP代理对象  
		    Object getTarget();       //返回目标对象  
		    Object[] getArgs();       //返回被通知方法参数列表  
		    Signature getSignature();  //返回当前连接点签名  
		    SourceLocation getSourceLocation();//返回连接点方法所在类文件中的位置  
		    String getKind();        //连接点类型  
		    StaticPart getStaticPart(); //返回连接点静态部分  
		    
		- 切入点（Pointcut）:***指定一个Adivce将被引发的一系列连接点的集合。AOP框架必须允许开发者指定切入点，例如，使用正则表达式。***
		-  通知（Advice）:***在特定的连接点，AOP框架执行的动作。各种类型的通知包括“around”、“before”和“throws”通知***
		
			>**AfterReturning 增强处理处理只有在目标方法成功完成后才会被织入。
	After 增强处理不管目标方法如何结束（保存成功完成和遇到异常中止两种情况），它都会被织入。**
		
		- 引介（Introduction）：***添加方法或字段到被通知的类，引入新的接口到任何被通知的对象。***
		
			>使用introduction要有三个步骤
			（1）声明新接口
			（2）创建自己的IntrouductionInterceptor通过ImplementsIntroductionInterceptor或extends DelegatingIntroductionInterceptor 并同implements(1)中声明的接口 
			（3）将新接口和自定义的IntroductionInterceptor配置DefaultIntroductionAdvisor中，然后将前三者配置到ProxyFactoryBean中。
		- 拦截器（Advisor ）
 		
 -  ####   SpringMvc
 
 	
 	- 优点：***简化WEB开发（有Spring的特点，并使用了MVC架构模式的思想，将web层进行职责解耦）***
 	- 工作流程：
 	![SpringMVC工作流程](https://img-blog.csdnimg.cn/20191216142847388.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMDcyOTUy,size_16,color_FFFFFF,t_70)
 -  ####   SpringBoot
	- [x]  [SpringBoot详解](https://blog.csdn.net/qq_43072952/article/details/103540549)
 - #### SpringData
 	- [ ]  [SpringData详解](https://spring.io/projects/spring-data)
 -  ####   Shiro
 	- [x]  [Shiro详解](https://blog.csdn.net/qq_43072952/article/details/103568017)
 -  ####   OAuth2
	- [x]  [OAuth2详解](https://blog.csdn.net/qq_43072952/article/details/103567515)
 -  ####   SpringSecurity
    - [ ]  [SpringSecurity详解](https://blog.csdn.net/Earth_Programer/article/details/88678078||https://www.cnblogs.com/yanfei1819/p/11350255.html)
## 数据层
 - #### Mysql
	- [x]  [Mysql详解](https://blog.csdn.net/qq_43072952/article/details/103574172)
- #### JDBCTemplate 详解
 	- [ ]  [JDBCTemplate 详解](https://blog.csdn.net/qq_43072952/article/details)
 - #### Mybatis
 	- [x]  [Mybatis详解](https://blog.csdn.net/qq_43072952/article/details/103568617) 
 - #### SpringDataJpa
	 - [x] [SpringDataJpa详解](https://blog.csdn.net/qq_43072952/article/details/103576775)
 - #### MybatisPlus
	 - [x] [MybatisPlus详解](https://mp.baomidou.com/)
 - #### Hibernate
	 - [x] [Hibernate详解](https://blog.csdn.net/qq_43072952/article/details/103578879)
 - #### 多数据源
	- [ ] [多数据源详解](https://blog.csdn.net/qq_31293575/article/details/82732239)
## 中间件
	
 - #### Redis
	- [ ] [Redis详解](https://blog.csdn.net/wangxinyao1997/article/details/103056024)
 - #### MongoDB 
	- [ ] [MongoDB 详解](https://blog.csdn.net/qq_36178899/article/details/81475094)
 - #### Kafka
	- [ ] [Kafka详解](https://blog.csdn.net/qq_36178899/article/details/85011522)
 - #### ActiveMQ 
 - - [ ] [ActiveMQ 详解](https://www.cnblogs.com/yanfei1819/p/11149170.html)
 - #### RabbitMQ
 	- [ ] [RabbitMQ详解](https://blog.csdn.net/m0_37743948/article/details/82864452)
 - #### Ehcache
	- [ ] [Ehcache详解](https://blog.csdn.net/shheaven/article/details/84479064)
## 通用性
 - #### Docker
 	- [x] [Docker详解](https://blog.csdn.net/qq_43072952/article/details/103584992)
 - #### Swagger2
 	- [x] [Swagger2详解](https://blog.csdn.net/qq_43072952/article/details/103585589)
 - #### HibernateValidatior
 	- [x] [HibernateValidatior详解](https://blog.csdn.net/qq_43072952/article/details/103586059)
 - #### Lombok
	- [x] [Lombok详解](https://blog.csdn.net/qq_43072952/article/details/103586488)
 - #### Jenkins
	- [x] [Jenkins详解](https://blog.csdn.net/qq_43072952/article/details/103586417)
 - #### JWT
	- [ ] [JWT详解](https://blog.csdn.net/weixin_43866856/article/details/84942710||http://www.luyixian.cn/news_show_228217.aspx)
## 搜索层
 - #### Lucene
 	- [ ] [Lucene详解](https://blog.csdn.net/ITITII/article/details/80555358)
 - #### ElasticSearch
	- [x] [ElasticSearch详解](https://blog.csdn.net/qq_43072952/article/details/103626665)
## 分布式
 - #### 分布式事务
 - [ ] [分布式事务详解](https://blog.csdn.net/sdrfengmi/article/details/83795957)
 - #### SpringCloud
  - [ ] [SpringCloud详解](https://blog.csdn.net/qq_41466024/article/details/81119220)
 - #### Redis锁
  - [ ] [Redis锁详解](https://blog.csdn.net/u010310183/article/details/90174421)
 - #### Zookepper锁
  - [ ] [Zookepper锁详解](https://blog.csdn.net/qq_39211866/article/details/84844005)
 - #### Redission锁
 - [ ] [Redission锁详解](https://blog.csdn.net/hgdzw/article/details/97241208)
## 网络层
 - #### Websocket
 - [ ] [Websocket详解](https://blog.csdn.net/muxiayayoumei/article/details/54894914)
 - #### t-io
 - [ ] [t-io详解](https://blog.csdn.net/zyw_java/article/details/80658683)
 - #### Nginx
 - [ ] [Nginx详解](https://blog.csdn.net/tjiyu/article/details/53027619)
## 渲染层
- [ ] [jsp详解](https://www.cnblogs.com/yanfei1819/p/10953600.html)
- [ ] [Thymelaf 详解](https://www.cnblogs.com/yanfei1819/p/10931435.html)
- [ ] Vue详解
- [ ] Element详解
## 切面层

## 功能模块
- #### 邮件服务
- [ ] [邮件服务](https://www.cnblogs.com/yanfei1819/p/11118340.html)
- #### 异常统一处理
- [ ] [异常统一处理](https://www.cnblogs.com/yanfei1819/p/10984081.html)
- #### 日志处理
- [ ] [日志处理](https://www.cnblogs.com/yanfei1819/p/10973583.html)
 - #### 文件上传
 - [ ] [文件上传详解](https://blog.csdn.net/qq_41151659/article/details/96574215)
 - ### 应用监控之Actuator
 - [ ] [应用监控之Actuator](https://www.cnblogs.com/yanfei1819/p/11226397.html)
 - #### 应用监控之Admin
 - [ ] [应用监控之Admin](https://www.cnblogs.com/yanfei1819/p/11457867.html)

 - #### 性能监控
 - [ ] 性能监控详解

## CODE
 - ####  简单的Demo 
 - ####  一般的项目
 - #### 复杂的项目
 - #### 手写系列
 - #### 开源框架
## 其他
 - #### 面试

