7.docker-compose.sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
5.ln -s /opt/apache-tomcat-9.0.55/bin/startup.sh /usr/local/bin/tomcatup
3.<role rolename="admin-gui"/>
<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/> 
<user username="admin" password="admin" roles="admin-gui,manager-gui,manager-script,manager-jmx,manager-status"/>
<user username="deployer" password="deployer" roles="manager-script"/>
<user username="tomcat" password="s3cret" roles="manager-gui"/>

5.freestyleproject.https://github.com/ajayithadi/freestyleproject.git
5.testing.https://github.com/sunildevops77/TestingNew.git

