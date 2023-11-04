Artifact - Package application into a single movable file

- Compile and compress
  Store in Artifact repostiory
- Nexus, JFrog
  Types are JAR and WAR

I first installed IntelliJ code editor
I am uising a Mac M2 so I followed the installation instructions for that

1. Installed IntelliJ but also use VS Code.
2. HomeBrew was previously installed
3. Git CLI was already installed
4. Installed latest version of (java 17.0.9)

5. Cloned java-maven-app
6. Created sym link
7. Next I installed Maven
8. Ran mvn package and successfully built project

9. Cloned java-app
10. Installed Gradle
11. Gradle build was successful
12. Got an error about the toolchanger. In Project Structure the wrong java sdk was referenced 17.0.7. Switched to 17.0.9 to solve it.
13. Project ran successfully

14. Cloned react.js project
15. Node and NPM was already installed and updated
16. Ran project and result: Server listening on the port::3080

Build Tools

1. JAR or WAR file
2. Maven (XML) or Gradle (Groovy)

Run the project:
java -jar build/libs/java-app-1.0-SNAPSHOT.jar
java -jar target/java-maven-app-1.1.0-SNAPSHOT.jar

Building JS apps

1. Use ZIP or TAR file
2. NPM or YARN package managers

- not build tools but package managers

3. NPM install

Run the app on the server:

1. Install dependencies
2. Unpack zip/tar
3. Run the app

Packaging code (2 Ways)

1. Package frontend and backend separately
2. Common artificate file

For React project

1. CD into api folder
2. Run npm install
3. Run npm run build

Python uses Pip package manager

Docker elimates need to use repositories

- no need to install dependencies
- no need to use zip or tar files
- Docker image is an artifact
- no need to install npm or java on the server
- pass env variables to image
- still need to build application

Tools needed for CICD:

1. npm/yarn test or gradle/mvn test
2. docker build
