# Steps to Install Jenkins on EC2(Ubuntu) Instance #
## Installing Java ##
</br>
1) Open a terminal window on your Ubuntu server.
</br>
2) Issue the command "sudo apt install default-jdk-headless"
</br>
3) Allow the installation to complete
</br>
4) To check the version of Java, issue the command "java --version"

## Installing Jenkins ##
</br>
1) Download and install the necessary GPG key with the command "wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -".
</br>
2) Add the necessary repository with the command "sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'".
</br>
3) Add the universe repository with the command sudo add-apt-repository universe.
</br>
4) Update apt with the command sudo apt-get update.
</br>
5) Install Jenkins with the command sudo apt-get install jenkins -y.
</br>
6) Allow the installation to complete.


