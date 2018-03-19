# spring framework
是一个ioc 容器，提供注入功能。

## Web 集成
在 tomcat“web.xml”中加入上下文监听器
```
<!-- 配置上下文 配置文件 -->
<context-param>  
	<param-name>contextConfigLocation</param-name>  
 	<param-value>  
     classpath:applicationContext.xml  
	</param-value>  
</context-param>
<!-- 配置监听器 -->
<listener>    
 <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>   
</listener>
```
