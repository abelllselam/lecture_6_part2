**Git and Amazon Web Services**

# Git

- It is a version control system (VCS).
- It is a system that keeps track of changes made to files that is not linear which means other parallel branches can exist.
- There are two types of version control systems:
- Centralized and distributed VCSs

# Centralized VCS:

- Repository is on a central server and client only has one version branch. Some example are CVS and Subversion SVN.

# Distributed VCS:

- The full repository is local and has full history. Server is involved but you can commit offline. You can also push and pull from repos.

# Git Basics

- Nearly every operation is local which makes it fast.
- Git uses 40 character SHA-1 hash which is computed and assigned to every commit, branch and tag.
- Git only adds data for the most part, nothing is deleted.
- Example of 40 character SHA-1 hash

```js
Input: "Hello World";
Output: "0a4d55a8d778e5022fab701977c5d840bbc486d0";
```

Git Setup:

- Git configuration commands set user-specific information such as name and email.
- Example:

```js
git config --global user.name "Jane Doe"
git config --global user.email JaneDoe@example.com
```

- (--global) sets these configurations for all repositories on your current machine.
- user.name specifies your name
- user.email specifies your email address.
- When you commit git records these details in the commit metadata.

# Retrieving configuration values:

- git config user.name - will give Jane Doe

# Create a new Repository (Create a new repo)

○ $cd projects - move into the project folder.
○ $git init - initialize a new Git repository.(creates .git/)
○ $git add . (. Adds the entire current directory with subdirectories) stages all the changes for commit.
○ $git commit -m “Initial commit”
○ $git push origin <branch-name> - push your local commit to the remote repository (like GitHub)

# Cloning an existing Repo

- git clone http://www.someurl.git (the URL comes from the github)

# Important Git Commands:

- git status - gives the current state of the repository, which shows the files that were added, removed, or edited.
- git add <file/dir> - adds untracked files, add tracked file to staging area.
- git commit -m "some message" - this will commit (save) the staged files to your local repository.
- git push origin <branch> - this will push or send/save your file to a remote repository that exists some where else like GitHub, Bitbucket, etc...
- git revert Head - undo the last commit by creating a new commit that reverses its changes.

# What is a branch in Git:

- Allow team members to wok concurrently on the same project
- The easiest way of adding new features to a project without disrupting workflow.
- Every Git repository wil have a master/main branch. Which the master should always have the current working version.
- It is often protected cant be deleted or forced-pushed to in team environments to prevent accidental breaking changes.
- It is also called the production or release branch.
- These branches will branch from Master/main and will incorporate new features into the product. When the branch is completed, tested, working correctly this branch will be merged into master/main.
- Branching Examples:
  - Endpoint called "/example", we wanted to add a new endpoint called /branch. Is this product is in production the best practice would be to create a branch from the master and create a branch called "<yyy>- branch-feature" add the end point and test thoroughly and merge the feature branch back to the master and then redeploy master so it is a seamless update.

# View Branches in Git

- $git branch -a -v : is the command to view all branches that are checked out locally and exist remotely.
  - git branch - lists local branches by default.
  - -a stands for all (All branches, shows both local and remote branches)
  - -v - verbose - adds extra informaion shows the lates commit hash and the commit message summary for each branch.
  - Example output:
  ```js
      $ git branch -a -v
      * main                a1b2c3d First working version of app
      feature/login       3d4e5f6 Added login form UI
      remotes/origin/main a1b2c3d First working version of app
  ```

# Create a branch in Git:

- git checkout -b <branch-name> to create a new branch.

  - What does it all mean:
    - Normally used to switch between branches or restore files.For instance (git checkout main) to switch to the amin branch.
    - (-b) - stands for branch, tells git to create a new branch with the name you give.
    - (<branch-name>) - the name you want to give your new branch.
    - git checkout -b feature/contact-form : will create a new branch switches to it and starting from the branch your currently on and switches to that new branch immediately so you can start working on it.
    - git checkout -b feature/contact-form origin/main
      creates the branch starting from origin/main.
    - To remove a branch use (git branch -d <branch-name>), the (-d) stands for delete.

# One thing to Note:

- if you are working on your branch and another branch gets pulled into master that means you are one commit behind HEAD (which just means master is getting updated so your feature branch is currently out of date). So you need to pull from the master!
- (git pull origin master From https://bitbucket.org/jal/sleepin) - we need to specify origin master when the master is not being tracked otherwise we can just say git pull.
