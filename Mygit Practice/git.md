 ### GIT PRACTICE


* Regression: New changes impacting working features and tests to identify this are called as Regression tests .

* API: Application Programming Interface means it is set of protocals and routines ans tools for building software also it allow to enable connection between software system allowing to work together seamly .

* API Testing: API testing is a process of testing the functionability realibility performance and security of an API by sending requests and verifing responces .

* Night Build: This build is done to consolidate all the work done by your dev team for the whole day
       * We do execute all the automated tests
       * This might take hours and gives confidence to manual testing team so that they can consider this build 

* Day Build: Every change submitted by developer during active work hours
       *  We do minimal test executions
       *  This should finish quickly

* Unit Testing: testing smaller units of code by writing code .

                                     Version Control Systems(VCS)

* VCS is a software tool that allows devoloper to manage changes to source code overtime . Enabling collabrations and providing a history of changes made to the codebase .

      GIT:
              1 . In Git we have 5 areas
              2 . Working tree/directory
              3 . Staging area/Cache area
              4 . Local repository
              5 . Remote Repository
              6 . Stash

* By using `git init` command we can create a empty/dummy repository .

* By using congigure means `git config --globel user.name vinod`
                           `git config --globel user.email vinod@gmail.com`
Above commands shows it is an one time job to create mail or name 

* using this command `git status` it show the status of the git what we done before .

* GIT has three main stages is first stage is working tree second stage Staging area and third stage Local area

* By using this command `git add one.txt/anything`  it is on working tree

* By using this command ` git commit -m "any name" ` it is an staging area

* by using this command `git push` it shows the file is get in to local area means this is an third stage . 

* `git checkout --` command used to switch between different branches or commits in repository .

* Using `git checkout -b <filename/id>` it change the head from one branch to another branch .

* By using `git checkout -` it get back to are changed to one brach to another branch what we added in head

* BY using `git reset HEAD~1 ` it reset the whole commited head mean it comes to 1st postion means head to master with out any committed heads .

* By using `git add . / git add -A` this two command shows to add all files where written in there directory .

* By using `git add -u` it add only modified files .

* By using `mkdir <foldername>` it create folder in your given repository .

* By using `touch <folder/filename>` it create the file in your folder When you create the file name then go to that file write any thing ans save it by that we can show the written names/number using `cat folder/filename`

* To remove permenetly the untracked files use `git clean -fd ` -f means force
                                                                -d means directories 

* By using `git rm --cached folder/filename`  it remove the file from the index not from the directory . it untracked . To undo the files again use `git restore --staged` & for source use `git restore --source` command .

* By using `rm <folder/filename>` it remove the file permenently from the folder .

* To delete the folders from the repository bu using `rm -r foldername`  -r means recursive means we are deleting all specified directory files and sub files included init .

* By using `git branch <name>` it create new branch . 

* To delete branch from git ` git branch -D <name> ` -D means delete the branch with merge status permenently .

* To reset the current branch to specified commit and  discard changes from commited from specified commit use `git reset --hard id/filename` this command is more caution this can permently delete changes made to the branches. it make thinks once to reset hard .

* To  keep changes after using commit use `reset --soft`

* `git push --all origin(name) ` Using this command we can move branches from multiple  repositories esaily .


                                    
                                    
                                    GIT MERGES TERMS

* There are four Types of git merge terms : 1. Fast Forwad Merge
                                            2. Three Way Merge
                                            3. rebase
                                            4. cherry pick

* FAST FORWARD MERGE:                                                                                   
https://console.aws.amazon.com/support/home?#/case/?caseId=13449839601 

