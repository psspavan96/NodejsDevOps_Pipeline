# Steps to Install Jenkins on Google VM(Ubuntu) Instance #
### Prerequisites ###
</br>
1) Google VM Instance With Internet Access and Security Group with Port 8080 open for internet
</br>
2) Java

## Installing Java ##
</br>
1) Open a terminal window on your Ubuntu server.
</br>
2) Once you are connected to the server type "sudo su" command in the terminal to go to the root.
</br>
3) Issue the command "sudo apt install default-jdk-headless"
</br>
4) Allow the installation to complete
</br>
5) To check the version of Java, issue the command "java -version"

## Installing Jenkins ##
</br>
1) Download and install the necessary GPG key with the command "wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -".
</br>
2) Add the necessary repository with the command "sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'".
</br>
3) Add the universe repository with the command "sudo add-apt-repository universe".
</br>
4) Update apt with the command "sudo apt-get update".
</br>
5) Install Jenkins with the command "sudo apt-get install jenkins -y".
</br>
6) Allow the installation to complete.

## How to access Jenkins ##
</br>
Open a web browser and point it to "http://SERVER_IP:8080" (where SERVER_IP(Public IPv4 in Google VM Instance) is the IP address of the hosting server). You will then be prompted to copy and paste a password that was created during the Jenkins installation. 
</br>
To retrieve that password, go back to the terminal window and issue the command "cat /var/lib/jenkins/secrets/initialAdminPassword"

#### Next Steps ####
</br>
1) Once you've unlocked Jenkins, you can then finish the installation by either installing the suggested plugins or installing only the plugins you want. 
</br>
2) When the plugin installation completes, you will then be prompted to create an admin user.
</br>
3) Fill out the necessary information for the admin user and click Save And Continue. You will then be shown the Jenkins URL. Click Finish and you're ready to start using Jenkins.

#### Change admin password ####
Go to Admin > Configure > Password

#### Configure java path ####
Go to Manage Jenkins > Global Tool Configuration > JDK

#### Note ####
</br>
The following plugins are required to be installed on Jenkins Server before executing this code:
</br>
1) Docker 
</br>
2) Docker Pipeline
</br>
3) Git and GitHub 
</br>
4) Node.js 
</br>
In order to install these plugins Go to Jenkins Home > Manage Jenkins > Manage Plugins
</br>
Once the above plugins are installed, go to Manage Jenkins > Global Tool Configuration to configure the plugins




