# �ؼ�����
- spring ���� tomcat
    - listener
    - encode filter
    - url-pattern ���� / /** /a* /a*.html /*.do /test.*
- spring ioc ����
- spring mvc ����
    - ����DispatchServlet ƥ��·��
    - ��̬��Դ·������ mvc:resources 
    - ������ mvc:interceptors
    - ��Դ��ͼ����
    - �쳣��������
    - url-pattern ���� /** /* /test*/**
    
- spring �����ļ�����
``` xml
<bean id="propertyConfigurer" class="com.zheng.common.plugin.EncryptPropertyPlaceholderConfigurer">
    <property name="locations">
        <list>
            <value>classpath:jdbc.properties</value>
            <value>classpath:redis.properties</value>
        </list>
    </property>
</bean>
<bean id="propertyConfigurer" class="org.springframework.beans.factory.config.PreferencesPlaceholderConfigurer">  
        <property name="location">  
        <value>classpath:config.properties</value>  
        </property>
        <property name="fileEncoding">   
       <value>UTF-8</value>   
     </property> 
</bean> 
<!-- �������ʹ�á�,������-->
    <context:property-placeholder     
           location="classpath:config.properties"    
           file-encoding="UTF-8"    
           ignore-resource-not-found=""   
           ignore-unresolvable=""    
           properties-ref=""    
           local-override=""    
           system-properties-mode=""   
           order=""    
    />  
```
- classpath* �� classpath �������� classpath* ��ȥ��������jar���е�����
# ���� spring MVC ��Ŀ��������

# spring test maven ����
1. �������� junit��spring test��spring������ bean context core 
``` xml
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>${junit.version}</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-test</artifactId>
    <version>${spring.version}</version>
    <scope>test</scope>
</dependency>
```
2. src/test/ ����test����
``` java
package com.chows.lab.springmvc.test;

import org.junit.runner.RunWith;
import org.springframework.test.context.ContextConfiguration;
import org.springframework.test.context.junit4.AbstractJUnit4SpringContextTests;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;

@ContextConfiguration(locations = { "classpath:spring/applicationContext.xml","classpath:spring/applicationContext-dao.xml","classpath:spring/springMVC.xml" })
@RunWith(SpringJUnit4ClassRunner.class)
public class SpringTestBase extends AbstractJUnit4SpringContextTests{

}
```