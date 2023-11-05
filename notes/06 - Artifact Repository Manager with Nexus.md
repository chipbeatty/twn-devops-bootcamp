6 - Artifact Repository Manager with Nexus

1. Created ec2 instance (8 gigs of memory and 30 gigs storage)
2. Created security group
3. Launched and then ssh into instance
4. I downloaded java
5. In the opt folder used sudo wget and link for nexus tar file
   https://download.sonatype.com/nexus/3/nexus-3.61.0-02-unix.tar.gz

6. Ran tar -zxvf nexus-3.61.0-02-unix.tar.gz
7. Created a user named nexus
8. Set permissions so nexus user can change files

```
sudo chown -R nexus:nexus nexus-3.61.0-02
```

```
sudo chown -R nexus:nexus sonatype-work
```

9. Run and change run_as_user="" to run_as_user="nexus" in vim editor

```
sudo vim nexus-3.61.0-02/bin/nexus.rc
```

10. Switch to nexus user

```
su - nexus
```

11. Start Nexus

```
/opt/nexus-3.61.0-02/bin/nexus start
```

12. Add port 8081 for Nexus in the security group for my instance
13. Logged into Nexus and setup new password.

Some Types of Nexus Repositories:

1. Maven Repository: Used for hosting and managing Maven artifacts, including Java libraries, JAR files, and related build artifacts.

2. NuGet Repository: Used for hosting .NET artifacts and packages, including libraries, assemblies, and related dependencies.

3. npm Repository: Used for hosting Node.js packages and modules.

4. Docker Repository: Used for hosting Docker container images.

Upload Jar File to Nexus

1. Create Nexus user
2. Created role (nx-view-maven-snapsots-\*) called nx-java
3. Assigned role to user
