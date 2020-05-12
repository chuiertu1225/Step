## 概述
Spring使开发Java企业级应用变得简单。它提供了企业环境中使用java语言所需的一切，支持虚拟机其他语言，Groovy和Kotlin,为各式各样的基于应用需求的框架提供了遍历性。Spring5.1需要JDK8以上的版本，为JDK11 LTS版本提供了开箱即用的支持，建议将Java SE 8更新60作为Java 8的最低修补程序版本，但通常建议使用最新的修补程序版本。  
Spring提供了广泛的应用场景。在一个大企业，应用经常存在很长时间并且运行在更新周期高于开发者控制的JDK和应用服务器中。其他的可能作为一个单jar包嵌入到服务器中，可能还运行在云环境中。还有其他的可能是不需要服务器的独立应用（比如批处理或集成工作）
Spring是开源的，它有着不断提供基于大量现实案例反馈的大活跃社区。这帮助Spring长时间的成功发展。 
## 1. Spring是什么意思
单词Spring在不同上下文中有不同意思。它能够用来指Spring Framework工程自己，一切开始的地方。随着时间推移，别的Spring工程要建立在Spring Franmework的基础上。大多时候，人们说起“Spring”，指的是整个工程系列。本参考文档重点关注基本：Spring框架本身。  
Spring框架分为几个模块。应用能够选择所需模块。核心是core container模块，包含了配置模型和依赖注入的机制。除此之外，Spring框架提供了不用应用架构的基本支持，包括通信，事务处理和持久层，还有web。也包括了基于Servlet的Spring MVC框架和Spring WebFlux 响应式web框架
## 2.Spring和Spring框架的历史
Spring起源于2003年作为早期j2ee具体的复杂性的解决方案。尽管一些人考虑J2ee和Spring竞争，事实上，Spring实际上是J2ee的补充。Spring程序不包含J2ee平台的具体规范；然而，它谨慎地整合了从EE保护伞中选择的个体规格：
Servlet API (JSR 340)  
WebSocket API (JSR 356)  
Concurrency Utilities (JSR 236)    
JSON Binding API (JSR 367)    
Bean Validation (JSR 303)  
JPA (JSR 338)  
JMS (JSR 914)  
和JTA/JCA setups for transaction coordination, if necessary.  
Spring框架也支持依赖注入（JSR 330）和应用开发者可能选择使用的取代Spring特有机制的和公共注解（JSR 250）

As of Spring Framework 5.0, Spring requires the Java EE 7 level (e.g. Servlet 3.1+, JPA 2.1+) as a minimum - while at the same time providing out-of-the-box integration with newer APIs at the Java EE 8 level (e.g. Servlet 4.0, JSON Binding API) when encountered at runtime. This keeps Spring fully compatible with e.g. Tomcat 8 and 9, WebSphere 9, and JBoss EAP 7.

Over time, the role of Java EE in application development has evolved. In the early days of Java EE and Spring, applications were created to be deployed to an application server. Today, with the help of Spring Boot, applications are created in a devops- and cloud-friendly way, with the Servlet container embedded and trivial to change. As of Spring Framework 5, a WebFlux application does not even use the Servlet API directly and can run on servers (such as Netty) that are not Servlet containers.

Spring continues to innovate and to evolve. Beyond the Spring Framework, there are other projects, such as Spring Boot, Spring Security, Spring Data, Spring Cloud, Spring Batch, among others. It’s important to remember that each project has its own source code repository, issue tracker, and release cadence. See spring.io/projects for the complete list of Spring projects.
## 3.设计哲学
当你学习框架的时候，知其然还要知其所以然是重要的。下面还是Spring框架的指导原则：  
- 各个层级可选。Spring让你推迟设计决定越晚越好。比如你可以切换持久层工具通过配置而不用改代码。很多其他的基本架构的考虑和三方API也是同理
- 容纳不同观点。 Spring带来便利不意味着理应如此。它提供了很多观点的应用需求。
- 保持向下兼容。 Spring的发展需要谨慎安排不同版本的重大变化。Spring支持很多JDK版本和促进应用维护的三方库和依赖Spring库的谨慎选择
- 关心接口设计。 Spring团队花了很多心思和时间在使得接口直觉化和经得起版本和岁月变迁。
- 代码质量高标。 Spring框架重点强调有意义的，同步的和准确的java文档。它是极少数的能宣称没有包中循环依赖的clean code架构
## 4.反馈和贡献
## 5.开始
如果你刚开始Spring,你可能想要考SpringBoot使用Spring框架。SpringBoot提供了快速可选的创建基于Spring的应用。它是基于Spring的，约定大于配置，设计来尽快搭建跑起来项目的。  
You can use start.spring.io to generate a basic project or follow one of the "Getting Started" guides, such as Getting Started Building a RESTful Web Service. As well as being easier to digest, these guides are very task focused, and most of them are based on Spring Boot. They also cover other projects from the Spring portfolio that you might want to consider when solving a particular problem.
## 核心技术
1. IOC容器
这个部分的文档包含了组成Spring框架的所有技术。  
最重要的技术要属IOC容器。