# Git-Cheat-Sheet



## Basic Flow: Daily Usage of Git

1. Initialize a local Git repository, creating the directory if it doesn't exist. Change directory to the repo, add files, and commit.

   ```shell
   git init demo && cd demo
   cp ~/Code/mycode.py mycode.py
   git add mycode.py
   git commit -m 'My first commit'
   ```

   Initialize a local Git repository, creating the directory if it doesn't exist. Change directory to the repo, add files, and commit.

2. As you begin to work with local files, you commit them at regular intervals. The `--all` option commits changes to existing files (use `git add` to add new files).

   ```shell
   git show
   git diff
   git commit --all -m 'Another commit'
   ```

3. After accumulating several commits, you may want to view the commit history in a more organized way.

   ```shell
   git log --graph --abbrev-commit
   ```

4. If you decide that some of your recent commits should be combined into a single meaningful commit, you can use the following steps:

   ```shell
   git reset --soft HEAD~3
   git diff --cached
   git commit -am 'Message for 3 commits'
   ```

5. Finally, you can push your local changes to a remote repository, designated as `origin`.

   ```shell
   git push origin HEAD
   ```

## Working with a Remote Repository: Contributing to Public Repositories

1. Download all commits and references from a remote repository using the following commands:

   - Fetch all commits and references:

     ```shell
     git fetch --all
     ```

   - Merge all commits since your last common commit from the remote branch without a merge commit:

     ```shell
     git pull --rebase <remote> <branch>
     ```

2. If you have uncommitted changes but need to switch to another branch or work on a different task, you can save those changes temporarily using `git stash` and then restore them when needed.

   - Save uncommitted changes:

     ```shell
     git stash
     ```

   - Restore saved changes:

     ```shell
     git stash pop
     ```

3. Other commonly used commands when working with Git repositories include:

   - Add a file to the staging area, to be committed:

     ```shell
     git add <file>
     ```

   - Commit changes with a commit message:

     ```shell
     git commit -m 'commit message'
     ```

   - Create and checkout a new branch:

     ```shell
     git checkout -b <new_branch>
     ```

   - Switch to the main branch and update it:

     ```shell
     git checkout main && git pull --rebase
     ```

   - Erase all local changes:

     ```shell
     git reset head --hard origin/main
     ```

   - Push your changes and the current branch to the origin repository:

     ```shell
     git push -u origin HEAD
     ```

   - Push your changes to the origin repository:

     ```shell
     git push origin HEAD
     ```

Most projects have a format for commit messages, so make sure to follow any guidelines in your project.

