# Day 13 Answers: Advance Git & GitHub for DevOps Engineers

## Git Branching

Branches are a core concept in Git that allow you to isolate development work without affecting other parts of your repository. Each repository has one default branch, and can have multiple other branches. You can merge a branch into another branch using a pull request.

Branches let you develop features, fix bugs, or safely experiment with new ideas in a contained area of your repository.

## Git Revert and Reset

Git reset and git revert are two commonly used commands that allow you to remove or edit changes you’ve made in the code in previous commits. Both commands can be very useful in different scenarios.

## Git Rebase and Merge

### What Is Git Rebase?

Git rebase is a command that lets users integrate changes from one branch to another, and the commit history is modified once the action is complete. Git rebase helps keep a clean project history.

### What Is Git Merge?

Git merge is a command that allows developers to merge Git branches while keeping the logs of commits on branches intact. Even though merging and rebasing do similar things, they handle commit logs differently.

For a better understanding of Git Rebase and Merge, check out this [article](https://www.simplilearn.com/git-rebase-vs-merge-article).

## Tasks with Answers

### Task 1: Feature Development with Branches

1. **Create a Branch and Add a Feature:**
   - Add a text file called `version01.txt` inside the `Devops/Git/` directory with “This is the first feature of our application” written inside. 

   - Create a new branch from `master`. 
     ```bash
     git checkout -b dev
     ```
**Answer**

![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%201.png)

2. - Commit your changes with a message reflecting the added feature.
     ```bash
     git add Devops/Git/version01.txt
     git commit -m "Added new feature"
     ```

   **Push Changes to GitHub:**
   - Push your local commits to the repository on GitHub.
     ```bash
     git push origin dev
     ```
**Answer**

![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%202.png)

3. **Add More Features with Separate Commits:**
   - Update `version01.txt` with the following lines, committing after each change:

     - 1st line: `This is the bug fix in development branch`
       ```bash
       echo "This is the bug fix in development branch" >> Devops/Git/version01.txt
       git commit -am "Added feature2 in development branch"
       ```

  - 2nd line: `This is gadbad code`
       ```bash
       echo "This is gadbad code" >> Devops/Git/version01.txt
       git commit -am "Added feature3 in development branch"
       ```

  - 3rd line: `This feature will gadbad everything from now`
       ```bash
       echo "This feature will gadbad everything from now" >> Devops/Git/version01.txt
       git commit -am "Added feature4 in development branch"
       ```
**Answer**

![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%202%20(2).png)
![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%202%20(3).png)

4. **Restore the File to a Previous Version:**
   - Revert or reset the file to where the content should be “This is the bug fix in development branch”.
     ```bash
     git revert HEAD~2
     ```
This command reverts the last two commits, effectively removing the "gadbad code" and "gadbad everything" lines.

### Task 2: Working with Branches

1. **Demonstrate Branches:**
   - Create 2 or more branches and take screenshots to show the branch structure.

**Answer**

![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%203.png)

2. **Merge Changes into Master:**
   - Make some changes to the `dev` branch and merge it into `master`.
     ```bash
     git checkout master
     git merge dev
     ```

   - Screenshot of branch structure:
     - To visualize the branch structure, you can use `git log` with graph options or a graphical tool like GitKraken. 

3. **Practice Rebase:**
   - Try rebasing and observe the differences.
     ```bash
     git rebase master
     ```
**Answer**

![image](https://github.com/Yash2526/DevOps/blob/dev/Task_Images/Task%204.png)

   - During a rebase, Git re-applies commits from the current branch (in this case, dev) onto the target branch (master). This results in a linear commit history.

