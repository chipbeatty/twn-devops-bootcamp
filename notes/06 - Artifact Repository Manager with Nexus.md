# 6 - Artifact Repository Manager with Nexus

> [!NOTE]
> Notes listed below the following screenshots

![maven image](/images/06/maven-1.png)

![nexus image](/images/06/nexus-1.png)

![nexus image](/images/06/nexus-2.png)

![nexus image](/images/06/nexus-3.png)

![nexus image](/images/06/nexus-4.png)

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

Upload Jar File to Nexus for

1. Create Nexus user
2. Created role (nx-view-maven-snapsots-\*) called nx-java
3. Assigned role to user
4. In the java-app project, add:

For java-app project:

- add plugin in gradle.properties so we can publish to nexus
- gradle.properties with username and password updated
- update url for nexus repo (maven-snapshot) with my url
- in the settings.gradle file update name of project

For java-maven-app:

- add maven-deploy-plugin in pom.xml
- add distributionManagement and I entered my nexus url
- settup credentials in the .m2 folder of my mac
  -- using vim created a settings.xml file and added:
  ```xml
  <settings>
  <servers>
    <server>
      <id>nexus-snapshots</id>
      <username>xxxxxx</username>
      <password>xxxxxxxx</password>
    </server>
  </servers>
  </settings>
  ```
- in the terminal ran mvn package
- ran mvn deploy to publish to nexus repository

Nexus REST API:
run curl -u user:password -X GET 'http://100.27.4.254:8081/service/rest/v1/repositories' to get list of repositories from nexus that role allows us to see

Blob Store
is a fundamental component that plays a crucial role in managing and storing binary artifacts and their associated metadata. It is responsible for storing the physical files (blobs) that make up the artifacts in the repositories hosted by Nexus.

Component

1. A logical unit of code or a build artifact.
2. A high-level concept in Nexus that may consist of one or more related files or assets

Asset:

1. The individual file in the nexus repository

You can create a Cleanup Policy in Nexus but for now I am keeping the projects as is for future sections of the bootcamp
