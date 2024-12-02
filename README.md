# Jenkins-
### Launch EC2 instance(instance type- t2.medium, machine image- ubuntu, volume- 30GiB) 
![image](https://github.com/user-attachments/assets/4d7f358e-322c-43f1-8511-5cfe84d37f4d)

### Jenkins installations
````
sudo apt update -y
sudo apt install fontconfig openjdk-17-jre -y

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y
sudo apt-get install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
````
![image](https://github.com/user-attachments/assets/1efa15fb-f2b9-46fb-a70b-12cd10099947)

### Install Docker 
````
sudo apt install docker.io
````
**Give permission to docker of read, write and execution**
````
sudo chmod 777 /var/run/docker.sock
````
![image](https://github.com/user-attachments/assets/c6a3535a-c6d5-47c8-a7d0-44486b205ef4)

### Login into jenkins 
**publicIP instance:8080(jenkins port)**

###

