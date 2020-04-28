#### Steps to install Docker on your Jenkins Server ####
</br>
1) First, update your existing list of packages using the command "sudo apt update"
</br>
2) Next, install a few prerequisite packages which let apt use packages over HTTPS using the command "sudo apt install apt-transport-https ca-certificates curl software-properties-common"
</br>
3) Then add the GPG key for the official Docker repository to your system using the command "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -"
</br>
4) Add the Docker repository to APT sources using the command "sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" "
</br>
5) Next, update the package database with the Docker packages from the newly added repo using the command "sudo apt update"
</br>
6) To Make sure you are about to install from the Docker repo instead of the default Ubuntu repo use the command "apt-cache policy docker-ce"
</br>
7) Install docker using the command "sudo apt install docker-ce"
</br>
8) To check whether docker is running or not use the command "sudo systemctl status docker"
</br>
9) Create a user called dockeradmin by using the commands "useradd dockeradmin" and "passwd dockeradmin".
</br>
10) Then add the user to the group by using the command "usermod -aG docker dockeradmin"
