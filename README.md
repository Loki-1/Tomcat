Tomcat

**Install Tomcat as a Service**

----Login as a root user----
sudo su -

yum install wget unzip -y

cd /opt
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.76/bin/apache-tomcat-9.0.76.zip

unzip apache-tomcat-9.0.76.zip


cd /opt/apache-tomcat-9.0.76/bin

chmod u+x *.sh


ln -s /opt/apache-tomcat-9.0.76/bin/startup.sh /usr/bin/starttomcat

ln -s /opt/apache-tomcat-9.0.76/bin/shutdown.sh /usr/bin/stoptomcat

ps -fax | grep tomcat
netstat -tunlap
vi /opt/apache-tomcat-9.0.65/webapps/manager/META-INF/context.xml

Comment the below lines
<!-- <Valve className="org.apache.catalina.valves.RemoteAddrValve"
allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->

starttomcat

stoptomcat
 
**#Create a user**
vi /opt/apache-tomcat-9.0.44/conf/tomcat-users.xml

Troubleshooting
--------------------

tomcat server is not starting?

a)Check the catalina.out file which is available  in conf dir.
b)check java is installed or not using java -version command.

Unable to access Tomcat server URL in browser?

a)make sure port 8080 is opened in security groups - AWS ec2 instance.



