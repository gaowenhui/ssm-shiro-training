�����Ǿ����ʹ�÷����� 
1. Tomcat7���û���Ȩ�����ã���confĿ¼�£��ҵ�tomcat-users.xml�����managerȨ�޵��û��������Ұ����õ�Ȩ�޶���Ӹ�admin�û��ˣ�����������£� 
<role rolename="admin-gui"/>
<role rolename="admin-script"/>
<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>
<user username="admin" password="admin" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-script,admin-gui"/>
 
2. Maven��Server�����ã���Maven�İ�װ·���ҵ�confĿ¼�µ�setting.xml�ļ�����<servers>�ڵ������tomcat7�����õ��û���Ϣ
��id����������д����username��password����Ͳ���1һ�£���
 <server>
	<id>tomcat7</id>
	<username>admin</username>
	<password>admin</password>
</server>

3. ��Web��Ŀ��pom.xml�ļ���<plugins>�ڵ��У����tomcat7��maven����� 
<plugin>
    <groupId>org.apache.tomcat.maven</groupId>
    <artifactId>tomcat7-maven-plugin</artifactId>
    <version>2.1</version>
    <configuration>
        <!-- ע��˴���url -->
        <url>http://localhost:8080/manager/text</url>
        <server>tomcat7</server> <!-- �˴������ֱ����setting.xml�����õ�IDһ��-->
        <path>/mavenProject</path> <!-- �˴�����������Ŀ�����Ĺ�����-->
    </configuration>
</plugin>
 

4. ���ֻ��Ҫmvn tomcat7:deploy�Ϳ����ˣ�������������tomcat�������� 


��½��admin  123456

  http://localhost:8088/ssm-shiro-training/index