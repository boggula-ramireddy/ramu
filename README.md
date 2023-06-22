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

3.	Click on deploy war/ear to container
	 Enter the path of the war file (or)
                      we can give **/*.war in war/ear files.
	 Context path: qaenv
	Repository URL - https://github.com/sunildevops77/TestingNew.git

	Build -- Add build Step  -- Execute shell
	( Command: java -jar  testing.jar )
	Command:   echo " Testing passed"

	Go to first job ( Free style ) --  configure 
	Post build actions -- add post build action -- build other project – 
	Projects to build - testing ( name of the job)

5.	Go to Development job 
	 Go to Post build actions tab
	Click on add post build action
	Click on Archive the artifacts
	 Enter      **/*.war

	Go to testing Job
	Click on configure
	Go to Build section
	Click on add build steps
	Click on copy artifacts from another project
	Enter Development as project name

	For Deployment Go to the Free Style job
	 Go to Post build actions section
	Click on add post build action
	Click on deploy war/ear to a container
	Enter **/*.war in war/ear files
	Context path : prodenv
	Click on add container 
	Select tomcat 9
	 Select your Credential






