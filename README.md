# jenkins-watchR
Jenkins iWatch Notifications

# Steps to Build Jenkins Docker Container #

1. From the `/docker` directory running the command

```
sudo docker build -t jenkinswatchr .
```

...will build the jenkins docker container

2. Start the docker container by running the command

```
sudo docker run -d -p 8080:8080 -v /var/jenkins_home:/var/jenkins_home jenkinswatchr
```

This runs the docker container as a daemon `-d` mapping the **_host:container_** ports as `8080:8080` and the **_host:container_** as `/var/jenkins_home:/var/jenkins_home` file volumes

If you encounter issues running on a linux host with SELinux be sure 
to allow access to the host volume using the SELinux command below

```
sudo chcon -Rt svirt_sandbox_file_t /var/jenkins_home
```

3. Visit the Jenkins instance running at **http://localhost:8080**

4. Create jobs as you see fit....reference **/var/jenkins_home** to store files off to the HOST volume.




