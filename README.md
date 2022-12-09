# Mega Real-time End to End DevOps
 [Local Setup]
 
 Prerequisite
1.	Oracle VM VirtualBox
2.	Vagrant
3.	Git bash or equivalent editor

VM SETUP
1.	Clone source code
2.	Cd into the repository.
3.	Switch to the local-setup branch

Bring up vm
$ vagrant up

PROVISIONING
#Provisioning all services by Docker-Compose File.
Services 
1.	Jenkins [Docker Image]
Ci-Cd automation server
2.	SonarQube [Docker Image]
continuous inspection of code quality to perform automatic reviews
3.	Nexus [Docker Image]
open-source repository that supports many artifacts formats

SonarQube Configuration
a.	Create username and password
b.	Create your project 
•	Create a project manually.
•	Create project Name & Key.
•	Analyze your project locally.
•	Generate a project token.
•	describes your build tool [maven]
•	run mvn clean verify sonar:sonar with project parameters Url&Login&Key 

Nexus Configuration
a.	Create root username and password.
b.	Create Mega-Central Repository to download and store all dependencies.
c.	Create Mega-Snapshot Repository to store snapshot artifacts.
d.	Create Mega-Release Repository to store Releases artifacts.
e.	Create Mega-Group Repository to store all Repositories.

Jenkins Configuration
1.	New item.
2.	Select Pipeline type.
3.	pipeline script from SCM.
4.	Add Repository URL.
5.	Provide Git credentials if private repository.
6.	Select which branch.
7.	Configure maven on Jenkins.
8.	Install below sonar plugins: 
i.	SonarQube ScannerVersion
ii.	Sonar GerritVersion
iii.	SonarQube Generic CoverageVersion
iv.	Sonar Quality GatesVersion
v.	Quality GatesVersion
9.	Configure SonarQube server on Jenkins [URL, authentication type, Jenkins credentials]
10.	From global tool configuration add SonarQube Extension. 
11.	Install below nexus plugins:
	Nexus Artifact UploaderVersion


