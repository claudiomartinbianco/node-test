# Jenkins Docker Example
This is the an example of a simple Node app, which shows how to run a Jenkins pipeline that will create a Docker image and run tests inside it.
This code was used in this [article](https://hackernoon.com/set-up-jenkins-ci-in-docker-container-and-run-your-tests-inside-their-own-container-a-how-to-guide-7h8u32yi)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details


## Modelo

https://hackernoon.com/set-up-jenkins-ci-in-docker-container-and-run-your-tests-inside-their-own-container-a-how-to-guide-7h8u32yi


docker build -f DockerfileJenkinsSetup -t gustavoapolinario/jenkins-docker .


docker run -d -p 8080:8080 \ 
-v /var/run/docker.sock:/var/run/docker.sock \
 -v /var/jenkins_home:/var/jenkins_home \ # Optional
 --name Jenkins_Docker gustavoapolinario/jenkins-docker

# One line:
docker run -d -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock -v /var/jenkins_home:/var/jenkins_home --name Jenkins_Docker gustavoapolinario/jenkins-docker


docker exec Jenkins_Docker cat /var/jenkins_home/secrets/initialAdminPassword
