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
