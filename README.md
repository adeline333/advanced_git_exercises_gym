## part 1 challenge 1
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main) 
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main) 
$ git log --oneline
41daa8f (HEAD -> main) chore: Create third and fourth files
399aed6 chore: Create another file
80e6ffd chore: Create initial file
744e3d9 (origin/main, origin/HEAD) exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main) 
$ git add test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main) 
$ git commit --amend --no-edit -m "chore: Create third and fourth files"
[main fb4c5b0] chore: Create third and fourth files
 Date: Wed Feb 26 13:11:29 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

```

## 2. editing the commit history
```bash

$ git rebase --continue
Successfully rebased and updated refs/heads/main.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main|REBASE 1/2)
$ git rebase --abort

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git rebase -i HEAD~2
[detached HEAD 26246d8] chore: Create second file
 Date: Wed Feb 26 13:11:28 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

```
## 3. Keeping History Tidy - Squashing Commits:
```bash


adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git rebase -i HEAD~4
[detached HEAD 392e7a2] chore: Squashed create second file
 Date: Wed Feb 26 13:11:27 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git log --oneline
1fae54f (HEAD -> main) part 1 exercise 1 and 2
5fbda99 chore: Create third and fourth files
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files

```
## 4. Splitting a Commit:
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git log --oneline
5fbda99 (HEAD -> main) chore: Create third and fourth files
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit
    

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git reset HEAD~1 --soft

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git reset test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 4 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test3.md
  (use "git restore --staged <file>..." to unstage)
        new file:   test3.md
        new file:   test3.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
Untracked files:
  (use "git add <file>..." to include in what will be committed)
  (use "git add <file>..." to include in what will be committed)
        README.md
        test4.md



adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git commit -m "chore: Create Third File"
[main cda0ba5] chore: Create Third File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git add test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git commit -m "chore: Create Fourth File"
[main 0c569b3] chore: Create Fourth File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git log --oneline
0c569b3 (HEAD -> main) chore: Create Fourth File
cda0ba5 chore: Create Third File
392e7a2 chore: Squashed create second file      
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files    
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit
```

## 5. Advanced squashing
```bash




adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git rebase -i HEAD~2
[detached HEAD 2b14897] chore: Create third and fourth file
 Date: Fri Feb 28 10:13:43 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git log --oneline
2b14897 (HEAD -> main) chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

```


## 6. Dropping a commit
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ echo "This is an unwanted commit" > unwanted.txt

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will 
be replaced by CRLF the next time Git touches it        

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git commit -m "Unwanted commit"
[main 3f7efaa] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.


adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git log --oneline
4b5a09b (HEAD -> main, origin/main, origin/HEAD) done with the first 5 challenges of the first part
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
4b5a09b (HEAD -> main, origin/main, origin/HEAD) done with the first 5 challenges of the first part
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
```

## 7. Reordering Commits:
```bash
$ git log --oneline
6094e7e (HEAD -> main) added sltn to qtn 6 in the read me
4b5a09b (origin/main, origin/HEAD) done with the first 5 challenges of the first pa
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
4b5a09b (origin/main, origin/HEAD) done with the first 5 challenges of the first pa
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
4b5a09b (origin/main, origin/HEAD) done with the first 5 challenges of the first pa
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
67da5d0 chore: Create another file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git rebase -i HEAD~6
Successfully rebased and updated refs/heads/main.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git log --oneline
4d77207 (HEAD -> main) added sltn to qtn 6 in the read me
f806dfd done with the first 5 challenges of the first part
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit
```

## 8.Cherry-Picking Commits:
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/branch) 
$ echo "Some content for test 5" > test5.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/branch) 
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/branch) 
$ git commit -m "Implemented test 5"
[ft/branch 191c0c7] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/branch) 
$ git push origin ft/branch
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (9/9), 2.23 KiB | 114.00 KiB/s, done.
Total 9 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
remote:
remote: Create a pull request for 'ft/branch' on GitHub by visiting:
remote:      https://github.com/adeline333/advanced_git_exercises_gym/pull/new/ft/branch
remote:
To https://github.com/adeline333/advanced_git_exercises_gym.git
 * [new branch]      ft/branch -> ft/branch

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/branch) 
$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 2 and 3 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)


adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git log ft/branch --oneline
191c0c7 (origin/ft/branch, ft/branch) Implemented test 5
4d77207 (HEAD -> main) added sltn to qtn 6 in the read me
f806dfd done with the first 5 challenges of the first part
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit


adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)      
$ git cherry-pick 191c0c7
[main d98b949] Implemented test 5
 Date: Wed Mar 5 12:16:13 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git log --oneline
d98b949 (HEAD -> main) Implemented test 5
4d77207 added sltn to qtn 6 in the read me
f806dfd done with the first 5 challenges of the first part
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file
52a1150 chore: Create initial file
f63a00a getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$

```


## 9.Visualizing Commit History (Bonus):
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)       
$ git log --oneline --graph --decorate --all
*   40983bb (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
|\
| * 4b5a09b done with the first 5 challenges of the first part
| |/
|/|
* | 4d77207 added sltn to qtn 6 in the read me
* | f806dfd done with the first 5 challenges of the first part
|/
* 744e3d9 exercise restart
:...skipping...
*   40983bb (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
|\
| * 4b5a09b done with the first 5 challenges of the first part
| * 2b14897 chore: Create third and fourth file
| * 392e7a2 chore: Squashed create second file
* | 6cc990e Added solution to the 7th and 8th exercise of the first part
* | d98b949 Implemented test 5
| | * 191c0c7 (origin/ft/branch, ft/branch) Implemented test 5
* | f806dfd done with the first 5 challenges of the first part
|/
:...skipping...
*   40983bb (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
|\
| * 4b5a09b done with the first 5 challenges of the first part
| * 2b14897 chore: Create third and fourth file
| * 392e7a2 chore: Squashed create second file
* | 6cc990e Added solution to the 7th and 8th exercise of the first part
* | d98b949 Implemented test 5
| | * 191c0c7 (origin/ft/branch, ft/branch) Implemented test 5
| |/
|/|
* | 4d77207 added sltn to qtn 6 in the read me
* | f806dfd done with the first 5 challenges of the first part
|/
* 744e3d9 exercise restart
* c103e24 chore: Save work before rebase
* f873b72 chore: Create third and fourth files
* 67da5d0 chore: Create another file
:...skipping...
*   40983bb (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
|\
| * 4b5a09b done with the first 5 challenges of the first part
| * 2b14897 chore: Create third and fourth file
| * 392e7a2 chore: Squashed create second file
* | 6cc990e Added solution to the 7th and 8th exercise of the first part
* | d98b949 Implemented test 5
| | * 191c0c7 (origin/ft/branch, ft/branch) Implemented test 5
| |/
|/|
* | 4d77207 added sltn to qtn 6 in the read me
* | f806dfd done with the first 5 challenges of the first part
|/
* 744e3d9 exercise restart
* c103e24 chore: Save work before rebase
* f873b72 chore: Create third and fourth files
* 67da5d0 chore: Create another file
* 52a1150 chore: Create initial file
* f63a00a getting started
* 16bfb8f chore:Create third and fourth files
:...skipping...
*   40983bb (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gymgithub.com/adeline 333/advanced_git_exercises_gym
|\  
| * 4b5a09b done with the first 5 challenges of the first part
| * 2b14897 chore: Create third and fourth file
| * 392e7a2 chore: Squashed create second file
* | 6cc990e Added solution to the 7th and 8th exercise of the first part
* | d98b949 Implemented test 5
| | * 191c0c7 (origin/ft/branch, ft/branch) Implemented test 5
| |/  
|/|   
* | 4d77207 added sltn to qtn 6 in the read me
* | f806dfd done with the first 5 challenges of the first part
|/  
* 744e3d9 exercise restart
* c103e24 chore: Save work before rebase
* f873b72 chore: Create third and fourth files
* 67da5d0 chore: Create another file
* 52a1150 chore: Create initial file
* f63a00a getting started
* 16bfb8f chore:Create third and fourth files
* 3766e1f chore: Create another file
:
```

## 10.Understanding Reflogs (Bonus):
```bash

```