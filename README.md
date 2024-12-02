# Jenkins-
## Launch EC2 instance(instance type- t2.medium, machine image- ubuntu, volume- 30GiB) 
![image](https://github.com/user-attachments/assets/4d7f358e-322c-43f1-8511-5cfe84d37f4d)

## Jenkins installations
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

## Install Docker 
````
sudo apt install docker.io
````
**Give permission to docker of read, write and execution**
````
sudo chmod 777 /var/run/docker.sock
````
![image](https://github.com/user-attachments/assets/c6a3535a-c6d5-47c8-a7d0-44486b205ef4)

## Login into jenkins 
**publicIP instance:8080(jenkins port)**
![image](https://github.com/user-attachments/assets/5733d856-5d4f-4f2e-a576-63e4e1672ef4)


## Copy path to mentioned on login page and paste it to see the key to login 
````
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
````
## Installed all suggested plugins
![image](https://github.com/user-attachments/assets/af5f12e1-b10f-4d22-928f-0b7a69ed8d33)

## Create admin user 
![image](https://github.com/user-attachments/assets/bf39331f-c24c-40d1-b233-a52967a45166)

## Download all the plugins and install tools
**Managed jenkins-->plugins-->Available plugins**

**Docker plugins**
![image](https://github.com/user-attachments/assets/1436184d-5b7d-4114-a487-c49fb1eb10ce)
**stageview plugins**
![image](https://github.com/user-attachments/assets/644a15d4-6c66-4c87-9467-83642db1b12d)
**maven**

## Add tools
**Add maven**
![image](https://github.com/user-attachments/assets/7e85ca34-697d-4bd0-8b40-945eeb557194)


## Create Pipeline
![image](https://github.com/user-attachments/assets/25599a39-e6ba-4bbb-b9c9-500439c839bf)
````
pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage("code-deploy"){
            steps{
                sh 'docker pull nginx'
                sh 'docker run -itd --name c-1 -p 80:80 nginx'
            }
        }
    }
}
````
## Build pipeline
![image](https://github.com/user-attachments/assets/f0a425c7-afa5-40b3-86ce-b8deb69890bf)
![image](https://github.com/user-attachments/assets/17c399fb-7a50-4ee7-92ae-729ec9a4499c)





