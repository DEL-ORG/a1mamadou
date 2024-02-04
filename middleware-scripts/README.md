# middleware-scripts
Sonarqube installation on Centos-7

Created by Mama
Last updated: 02/20/23

What is SonarQube?
SonarQube is an open-source platform developed by SonarSource for continuous inspection of code quality. SonarQube does static code analysis, which provides a detailed report of bugs, code smells, vulnerabilities, code duplications.

Benefits of SonarQube
Here are some advantages of using SonarQube:

Sustainability - Reduces complexity, possible vulnerabilities, and code duplications, optimising the life of applications.

Increase productivity - Reduces the scale, cost of maintenance, and risk of the application; as such, it removes the need to spend more time changing the code

Quality code - Code quality control is an inseparable part of the process of software development.

Detect Errors - Detects errors in the code and alerts developers to fix them automatically before submitting them for output.

Increase consistency - Determines where the code criteria are breached and enhances the quality

Business scaling - No restriction on the number of projects to be evaluated

Enhance developer skills - Regular feedback on quality problems helps developers to improve their coding skills
su - vagrant
Step 1: Java 11 installation
The only prerequisite for running SonarQube is to have Java (Oracle JRE 11 or OpenJDK 11) installed on your machine. To install OpenJDK 11, run the following commands


sudo yum update -y
sudo yum install java-11-openjdk-devel -y
sudo yum install java-11-openjdk -y
#Step 2: Download SonarQube latest versions on your server
#Let’s navigate to the /opt directory before downloading
cd /opt
#If wget is not installed on your system, run the command to install it. Then download SonarQube #package:
sudo yum install wget -y
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.3.0.51899.zip
#Step 3: Extract packages
If unzip is not installed on your system, run the command 
sudo unzip /opt/sonarqube-9.3.0.51899.zip
#To install it. Now, unzip the previously installed package:
sudo unzip /opt/sonarqube-9.3.0.51899.zip
#Step 4: Change ownership to the user and Switch to Linux binaries directory to start service
sudo chown -R vagrant:vagrant /opt/sonarqube-9.3.0.51899
cd /opt/sonarqube-x.x/bin/linux-x86-64 

 ./sonar.sh start
#Connect to SonaQube
#Connect to the SonarQube server through the browser. It uses port 9000.

http://<your-ip-address>:9000

#NB: Some servers have firewall enabled. So if you are not able to connect from the browser, then you #might want to open the port 9000 with this command:

sudo firewall-cmd --permanent --add-port=9000/tcp
sudo firewall-cmd --reload