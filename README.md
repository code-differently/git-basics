# Git Basics

## Objective

Become more familiar with git commands and version control

## What we'll cover

* Creating a Git repository
* Tracking files
* Staging and Commiting Files
* Logging

## Activity 1

Groups(not > 3) will work together to complete the following step. Each student should have there own work for this activity

### Step 1 - Set up the project

1. Using terminal, navigate to your projects(development) folder and create a new directory name 'git-basics-1'.
2. Change directory to the new 'git-basics-1' directory.
3. Verify you are in your new project folder with `pwd` or looking at the current directory in your command line prompt
4. List out the contents of this folder with `ls`. Since this is a new folder, there should be nothing listed.

### Step 2 - Initialize a new repository

When you initialize a new repository, you must be inside the folder you want to track the changes. Each project should have it's own git repository.

1. From termianl, make sure you are  inside the 'git-basics-1' directory.
2. Initialize a new repository with `git init`. What happens? What messages are output from the terminal?
3. Check the current status of the git repository whith, `git status`. What is the output? Notice the text inside the parenthesis `()`.
3. Run `ls -l`, what has changed?
4. Run `ls -la`, what do you see?

Git records all changes in a hidden folder named '.git'. This is why in order to see the folder we have to you the `-a` option to see all files and folders (including hidden ones)

`git status` is a way to see the current state of the repository. Git will also output some recommended steps sometimes. Use `git status` often, it doesn't cost anything and keeps you informed about the state of your repository

### Step 3 - Create a new file

Now ceate a simple text file and add some content.

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Create a new text file with `touch ./html5.txt`
3. Check to status of the repository again `git status`. What does it say? How is it different from the first time you checked the status?

In the status ouput, git displays a few things:

* **No commits yet** - This is just telling us there have been no changes that have been committed to the git history.
* **Untracked files** - When Git encounters a file for the first time, usually from a newly created file, Git will not track the changes automatically.
* **Nothing added to commit** - This is a notification to signal nothing that is being tracked has changes to be committed to the change history.

Git must be told to which files to start tracking (we will do this in the next step.) This is good because it give us a chance to choose which files to track and which files to ignore (we will see how to ignore files later) 
 
Don't forget to use the built in terminal manual for commands that you don't understand. `man touch` to learn more about create/modifying a file.

### Step 4 - Begin tracking a file

In order for git to begin tracking the changes to files, Git must know which files to track.

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status`, we see one untracked file. Lets change that
3. Run `git add ./html5.txt`. This will tell Git to start tracking the changes to this file.
4. Run  `git status` again. What is the output? How has it changed from before?

The 'untracked files:' has gone away and replaced with 'Changes to be comitted'. The output also describes the status of the file, 'new file'

At this point we have not commited any changes to the git history...yet. We have simply prepared the file to be committed by using `git add <filename>`. This is knowd as staging a file to be committed.

### Step 5 - Make the first commit

Now that the new file being tracked and added to staging, the next step is to commit the change to the git history.

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status` to check on the current state of the repository. There is one file (html5.txt) ready to be committed
3. Run `git commit -m 'add html5 file'`. What is the output. 
4. Run `git status`. What does it say? What changed?

Git commit messages should describe *what* happened with this change. Leave out the who or why.

### Step 6 - Modify the file

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Open the file with the default application for '.txt' files with `open ./html5.txt`
3. Open a web browser and navigate to [Wikipedia](https://en.wikipedia.org/wiki/Main_Page)
4. Search 'HTML5'
6. Copy the first paragraph from the article and paste it into the 'html5.txt' document. Save the file.
7. Return to terminal and run `git status`. What is the output? What changed? What is the status of the files.

* **Changes not staged for commit:** - files listed under this section are tracked files that have been modified or changed in some way. 

### Step 7 - View the difference

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status` and take note of your modified files
3. Run `git diff ./html5.html`. What happened? What is the output?

`git diff <file-name>` will show the differences of an file since the last commit. It will only work on files that have not been staged for the next commit.

### Step 8 - Stage the file

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status`.
3. Adding the file to staging with `git add ./html5.txt`. This will put the modified changes in to staging, thus marking them to be included with the next commit.
4. Run `git status`. What happened?

Using `git add <file-name>` adds the file to staging. Staging means that is will be included in the next commit.

* **Changes to be committed:** the files listed below this are files that ready to be added with the next commit.

### Step 9 - View the difference again

1. From terminal, make sure you are inside the 'git-basics-1' directory.
2. Run `git diff ./html5.txt`. What do you see? or what don't you see?
3. Run `git diff --staged ./html5.txt`. What do you see?

Running `git diff <file-name>` will only show differences in unstaged files from the last commit. Running `git diff --staged <file-name>` shows the differences between staged files and the last commit

### Step 10 - Commit the changes
1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status`.
4. Commit the staged file to the git history with `git commmit -m 'some meaningful message'`
5. 2. Run `git status`. What do you see?

Every iteration of a git commit cycle includes adding the modified files to staging. Then committing staged files to the git history (git commmit -m 'some meaningful message')


### Step 11 - Look at the logs

A major benitfit of having a change history is being able to look back to previous commits to see how files have been changed.

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Run `git status`.
3. Run `git log`. What do you see?

The log tells you the following info:

* A commit identifier - This long string of numbers and letters is unique for each commit. This can be used to get information about the commit. Such as, files, lines of code and more that changed during the commit. 
* Aurthor - who made the commit
* Date - when the commit happened
* Message - the message that was added for the commit

### Step 12 - More changes

Now we will repeat some of the steps to add and modify more files. Use the previous steps as reference when completing the following tasks

1. From termianl, make sure you are inside the 'git-basics-1' directory.
2. Open `html5.txt` again. Add another paragraph from Wikipedia and save the file.
3. Return to terminal and run 'git status'
4. Create a new file called 'css3.txt' and open it
5. Search wikipedia for 'CSS3'
6. Copy and paste a paragraph into the new 'css3.txt' file. Save the file
7. In terminal, run `git status`
8. Use git diff to see the changes
8. Add the changes to 'html5.txt' to staging with git add
9. Run `git status`
10. Commit the changes
11. Add 'css3.txt' to staging with git add
12. Run `git status`
13. Use `git diff <file-name>` and `git diff --staged <file-name>`
14. Commit the new changes

## Activity 2

Using terminal and Git version control, initialize a repository in an existing project

1. Using terminal, navigate to an existing project that you have created.
2. In the root of the project initialize a new git repository with `git init`
3. Using the commands you have learned so far add and commit the project files to the git history.
4. Open your code editor and make some changes to the project files(add some code, remove some code)
5. Use the git status and diff commands to examine the changes you've made
6. Use `git restore <file-name>` to undo any changes from the last commit.

