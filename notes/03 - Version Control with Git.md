Best Practices for GitHub:

1. **Commit changes often**: Don't check-in large amount of changes at once.

2. **Informative README**: Create a well-documented README file that explains what your project does, how to use it, and how to contribute.

3. **.gitignore**: Utilize a .gitignore file to specify which files and directories should be excluded from version control, such as build artifacts or sensitive information.

4. **Branching Strategy**: Adopt a branching strategy (Git Flow), to manage your project, like features, bug fixes, and releases.

5. **Descriptive Repository Names**: Choose descriptive names for your repositories.

6. **Issues and Milestones**: Use GitHub Issues to track tasks, bugs, and feature requests. Create milestones to group related issues and track progress.

7. **Code Reviews**: Regularly conduct code reviews.

8. **Continuous Integration (CI)**: Implement CI pipelines using GitHub Actions or other CI/CD tools to automate testing and deployment processes.

9. **Version Tags**: Use version tags to mark important project milestones and releases. This simplifies tracking changes and keeping users informed.

10. **Licensing and Legal**: Select an appropriate open-source license for your project, include it in your repository, and adhere to legal requirements.

3 Stages of Code in Local Repository

1. Working Directory
   - git add
2. Staging Area
   - git commit
3. Local Repo (Committed)

Steps for creating Repo

1. I created a new reo.
2. Made it public and included a README.md file and a LICENSE file
3. Added .gitignore file (not sure if I will need it)
4. Created a ssh key and added it locally and to the github account
5. I setup the local repository

```
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/username/repository.git
git push -u origin main
```

6. Pushed code successfully

Pushing a Local Project to New Repo

1. From terminal run git init. Make sure you are in right location.
2. Run git remote add orgin <git address> to connect from local repo to github repo.
3. Run get push --set-upstream orgin main to connect to branch

Branches

- create branch for each feature or bug fix
- prefix with feature/ or bugfix/
- git checkout -b branch name to create and checkout nes branch in terminal
- git push --set-upstream orgin branch name to link with github remote repo
- typical to have main branch and develop branch
- ideal goal is to deploy changes on every merge
- delete branches locally and remotely after merging
  git brach -d branch-name
- use git pull-r to pull remote merge changes on top of your own (rebase)
- use git stash to store changes and prevent from being overwritten
  git stash pop to get changes back
- use hash to go back into history
- use git reset to undo commit
