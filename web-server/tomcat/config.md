## ��������java����
tomcat binĿ¼��catalina.bat�ļ�
set JAVA_OPTS=-Xms512m -Xmx1024m -XX:MaxPermSize=1024m

## web.xml
����error page
```
<welcome-file-list>
    <welcome-file>index.html</welcome-file>
</welcome-file-list>
<error-page>
    <error-code>404</error-code>
    <location>/500.html</location>
</error-page>
<error-page>
    <error-code>500</error-code>
    <location>/500.html</location>
</error-page>
```
