#Git Notes

##What is Git?

Git is a version control system. Can be distributed through GitHub and also local. 

##Basic Workflow
1. Make changes
2. Stage changes 'git status' and 'git add'
3. Commit changes 'git commit'
4. Push to GitHub 'git push'

## Basic Commands
git init
git add
git status
git commit
git push
git pull
git log
.gitignore
git remote
git log


#Learning Notes

##Day 1 & 2 - 25/26 Aug 2026 (Written up on 27 Aug)

Topic: Learning What Git/GitHub is and learning basic commands 

Learned
- Installed git and GitHub desktop
- Initialised git and connecting it to GitHub
- Read up on Pro Git (Scott Chancon and Ben Straub)
- Learnt basic git workflow (what untracked is, staging area and committing)
- Created a local repository and connected it to GitHub
- Created notes (this file) to track progress of git learning whilst practicing git itself
- Practiced basic commands such as git init, add, status, commit, and Push

What I can do now:
- Create repository 
- Connect it to GitHub
- Commit changes
- Push changes

Next session -> Learn pull, branches, remote

##Day 3 - 27 Aug 2026

Topic: Continuing learning git basics and Practiced

What I learned:
- Skipping staging part (adding -a to git commit 'git commit -a -m 'Commiting')
- Practiced git clone (cloning easy python projects)
- Read up on git remote
- Read up on branching and merging (what branches are, how to set up one, its usefulness, and how to merge branches)

###Branching

Branching is a top git feature that allows you to work on a copy of the repository without messing up the main development

Because Git captures snapshots, everytime you commit and push it captures a snapshot and points back to the previous snapshot. 
Creating a new branch means you create a new base in which to start pointing 
- Switch branches by 'git checkout [branch name]'
- Close branch by using -d 'git branch -d [branch name]'

###Merging

'git merge [branch name]'
The command would merge the branch with the branch that is currently pointed at by 'git checkout [branch name]' i.e. HEAD

What I can do now:
- Clone a repository
- Troubleshooting an embedded repository error
