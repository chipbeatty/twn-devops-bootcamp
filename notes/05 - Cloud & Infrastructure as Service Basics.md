# 5 - Cloud & Infrastructure as Service Basics with DigitalOcean

> [!NOTE]
> Notes listed below the following screenshots

![java-react image](/images/05/java-react-example.png)

Instead of using Digital Ocean, I created a ec2 instance.

1. Create latest Ubuntu ec2 instance
2. Created .pem key and used chmod 400 to set up permissions.
3. Used new security group that allowed access from kports 22, 80 and 443
4. Was able to ssh into instance
5. Downloaded java

Next series involved the following project:

https://gitlab.com/twn-devops-bootcamp/latest/05-cloud/java-react-example

1. Cloned the above project locally
2. Ran gradle build
3. Used the command below to copy project to my ec2 instance

```
scp -i ~/documents/chip.pem -r build/libs/java-react-example.jar ubuntu@ec2-x-xx-xx-xx.compute-1.amazonaws.com:/home/ubuntu/
```

4. Ran java -jar java-react-example.jar successfully
5. In my ec2 instance added security rule to allow port 7071 for Tomcat server
6. Pulled up the site using public ip and port number
7. Installed net tools
