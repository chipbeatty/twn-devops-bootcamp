8 - Build Automation & CI/CD with Jenkins

2 Ways to Install Jenkins

1. Install directly on OS

- requires more setup

2. Run Jenkins as a Docker container

- less configuration
- no need to setup a Jenkins user
- method I used

I setup up Jenkins on Ubuntu EC2 instance

1. Seleted t3 micro (8gb)
2. For security group opended port for Jenkins at 8080
3. SSH'd into ec2 instance
4. sudo apt update
5. sudo apt install docker.io
6. sudo docker run -p 8080:8080 -p 50000:50000 -d -v jenkins-home:/var/jenkins_home jenkins/jenkins:lts
7. sudo docker exec -it 4e45ef1067c8 bash
8. cat /var/jenkins_home/secrets/initialAdminPassword
9. Go to Jenkins UI and setup password

2 Roles for Jenkins App

1. Jenkins Admin

- Sets up Jenkins cluster
- Installs plugin
- Backup Jenkins data

2. Jenkins User

- Creates jobs to run workflows

Build Tools

1. Install Maven

Install Node and NPM on Container

1. sudo docker exec -u 0 -it 4e45ef1067c8 bash
2. apt update
3. curl -sL https://deb.nodesource.com/setup_20.x -o nodesource_setup.sh
4. bash nodesource_setup.sh

Create Freestyle Project (my-job)

1. simple use case
2. In configuration section added build step

- Execute Shell
- enter npm --version in Command section

3. Add build step for Maven

- select version created (maven-3.9)
- add --version command for Goals section

4. Built proram successfully
