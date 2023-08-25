# GITHUB SKILL REVIEW

<img src="https://media.makeameme.org/created/code-github.jpg" width="200">

## Commands Cheat Sheet

| Action                                | Command                                              | Purpose                                         |
|---------------------------------------|------------------------------------------------------|-----------------------------------------------------|
| Clone Repository                     | `git clone <URL>`                                    | To copy the remote repository to your local machine.|
| Create New Branch                    | `git branch <branch-name>`                           | To create a new branch for separate work.           |
| Switch to Branch                     | `git checkout <branch-name>`                         | To switch to a different branch.                    |
| Add Changes                          | `git add .` or `git add <filename>`                  | To stage changes for commit.                        |
| Commit Changes                       | `git commit -m "Your message here"`                  | To save your changes with a message.                |
| Push Branch to GitHub                | `git push origin <branch-name>`                      | To upload your branch to the remote repository.     |
| Switch to Main Branch                | `git checkout main`                                  | To switch back to the main branch.                  |
| Pull Latest Changes from Main Branch | `git pull origin main`                               | To update the main branch with the latest changes.  |
| Fetch All Branches from Repository   | `git fetch origin`                                   | To get all remote branches without merging.         |
| List All Branches                    | `git branch -a`                                      | To see all available branches, local and remote.    |
| Checkout Remote Branch               | `git checkout -b <branch-name> origin/<branch-name>` | To create and switch to a branch from a remote one. |
| Merge Another Branch into Your Own   | `git merge <teammate's-branch-name>`                 | To combine changes from another branch into yours.  |

> Note that all these commands (except `git clone`) must be executed INSIDE THE REPO DIRECTORY!

## Vocabulary

| Term        | Definition                                                                                   |
|-------------|----------------------------------------------------------------------------------------------|
| Repository  | A container for a project, including all files, history, and branches. Can be local or remote.|
| Branch      | A parallel version of a repository, used to work on different features without affecting the main code.|
| Checkout    | A command to switch between different branches or specific commits.                            |
| Commit      | A saved set of changes with a unique ID and message, representing a snapshot of the project at a specific point in time.|
| Push        | The act of sending commits from a local repository to a remote repository.                    |
| Pull        | The act of fetching changes from a remote repository and merging them into the local branch.   |
| Merge       | The act of combining changes from one branch into another.                                     |
| Clone       | A copy of a repository that lives on your computer instead of on a website's server.           |

### Step 1: Creating the Repository
**Person in Charge**: One person should create the repository on GitHub.
1. Log in to GitHub.
2. Click the "+" sign in the top right corner, then "New repository."
3. Name the repository, add a description, and choose whether it's public or private.
4. Click "Create repository."

### Step 2: Inviting Collaborators
1. Go to the repository page on GitHub.
2. Click "Settings" > "Manage access" > "Invite collaborators."
3. Enter the GitHub usernames or emails of your teammates.
4. Click "Add."

### Step 3: Cloning the Repository (Everyone)
1. On the main page of the repository, click "Code" and copy the URL.
2. Open a terminal on your Linux machine.
3. Navigate to where you want to clone the repository.
4. Run `git clone <URL>`, replacing `<URL>` with the URL you copied.

### Step 4: Creating a Branch (Everyone)
1. Navigate into the cloned repository: `cd <repository-name>`.
2. Create a new branch with `git branch <branch-name>`, replacing `<branch-name>` with your chosen name.
3. Switch to the new branch with `git checkout <branch-name>`.

### Step 5: Making Changes (Everyone)
1. Make your changes in the code using your preferred editor.
2. Add the changes with `git add .` (or specify files with `git add <filename>`).
3. Commit the changes with `git commit -m "Your message here"`.

### Step 6: Pushing the Branch to GitHub (Everyone)
1. Push your branch with `git push origin <branch-name>`.

### Step 7: Merging Changes (Optional, Person in Charge)
If you're ready to merge the changes into the main branch:
1. On GitHub, go to the repository's main page.
2. Click "Pull requests" > "New Pull Request."
3. Select the branches you want to compare and merge.
4. Click "Create Pull Request."

### Step 8: Pulling Changes from the Main Branch (Everyone)
Before working on or continuing with your own branch, make sure you have the latest updates from the main branch:
1. Switch to the main branch with `git checkout main`.
2. Pull the latest changes with `git pull origin main`.

### Step 9: Fetching and Checking Out a Teammate's Branch (Everyone)
If you want to work on or review a branch that someone else created:
1. Fetch all branches from the remote repository with `git fetch origin`.
2. List all branches, including those from your teammates, with `git branch -a`.
3. Check out the branch you want with `git checkout <branch-name>`. If the branch doesn't exist locally, use `git checkout -b <branch-name> origin/<branch-name>`.

### Step 10: Merging Changes from a Teammate's Branch (Optional, Everyone)
If you need to merge changes from a teammate's branch into your own:
1. Make sure you've checked out your branch with `git checkout <your-branch-name>`.
2. Merge the other branch with `git merge <teammate's-branch-name>`.
