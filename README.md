# spring-cloud-config-server-repository
spring cloud config server file 20180729
spring-cloud入门环境搭建
1.什么是spring-cloud

pring Cloud为开发人员提供了快速构建分布式系统中一些常见模式的工具（例如配置管理，服务发现，断路器，智能路由，微代理，控制总线，一次性令牌，全局锁定，领导选举，分布式会话，集群状态）。分布式系统的协调导致锅炉板模式，使用Spring Cloud开发人员可以快速站起来实现这些模式的服务和应用程序。它们适用于任何分布式环境，包括开发人员自己的笔记本电脑，裸机数据中心和Cloud Foundry等托管平台。
spring-cloud是spring提供的微服务整合开发框架

★○●◎◇□◆☆■△▲※
2.为什么使用spring-cloud
经历过netflix业务考验，国外大规模使用
入门门槛低，国内大批量使用spring
快速搭建

3、什么是微服务
小巧，并且专注于做好一件事：

	★单一责任原则
	★两周内可以重写
	★够小，而不会更小

自主性：
	★避免在同一机器
	★独立变更 独立部署
	★解耦合

主要好处
	技术异质
	不同分为使用不同技术
	容易验证新技术

弹性
   隔舱概念：在多台机器上执行，减少崩溃


扩展
	只扩展需要扩展的服务

	资源要求不高的服务可以部署在较旧较小的机器

容易部署
	对单一服务做变更
	容易rollback

人员组织调校
	处理较小团队
	减少单一代码的基础人数

组合性
	开拓功能重复利用机会
	通盘考量各种使用途径
	最佳化可替换性
	容易重写服务，替换成本小

是什么构成好服务
	松耦合
		更改一个服务，不会影响其他服务
		松耦合服务，对其他协作服务所知甚少
	高度内聚
		相关行为聚合在一起，无关行为分散在不同地方
		改变某个行为，自在一个地方修改，也只需要重新部署少数
		服务，减少发生错误风险

Spring Boot  在线生成项目pom
	 青出于蓝，更胜于蓝
https://start.spring.io/

<!-- Spring Boot 监控  Actuator   与 Remote Shell-->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-remote-shell</artifactId>
		</dependency>
	</dependencies>

spring cloud 学习(5) - config server
disconf是把配置信息保存在mysql、zookeeper中，而spring cloud config是将配置保存在git/svn上 （即：配置当成源代码一样管理）
spring cloud config没有类似disconf的统一管理界面，既然把配置都当成git之类的源码来看待了，git的管理界面，就是配置的管理界面	
配置变化的通知机制不同
disconf中配置变化后，依赖zk的事件watcher来通知应用，而spring cloud config则是依赖git每次push后，触发webhook回调，最终触发spring cloud bus(消息总线），然后由消息总线通知相关的应用。
