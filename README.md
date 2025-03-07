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
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git reflog
a475b6b (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: commit: so;ution to exercise 9
40983bb HEAD@{1}: commit (merge): Merge branch 'main' of https://github.com/adeline 
6cc990e HEAD@{2}: commit: Added solution to the 7th and 8th exercise of the first part
d98b949 HEAD@{3}: cherry-pick: Implemented test 5
4d77207 HEAD@{4}: checkout: moving from ft/branch to main
191c0c7 (origin/ft/branch, ft/branch) HEAD@{5}: commit: Implemented test 5
4d77207 HEAD@{6}: checkout: moving from main to ft/branch
4d77207 HEAD@{7}: rebase (finish): returning to refs/heads/main
4d77207 HEAD@{8}: rebase (start): checkout HEAD~6
4d77207 HEAD@{9}: rebase (finish): returning to refs/heads/main
4d77207 HEAD@{10}: rebase (pick): added sltn to qtn 6 in the read me
f806dfd HEAD@{11}: rebase (pick): done with the first 5 challenges of the first part744e3d9 HEAD@{12}: rebase: fast-forward
c103e24 HEAD@{13}: rebase (start): checkout HEAD~6
6094e7e HEAD@{14}: rebase (finish): returning to refs/heads/main
6094e7e HEAD@{15}: rebase (start): checkout HEAD~6
6094e7e HEAD@{16}: commit: added sltn to qtn 6 in the read me
4b5a09b HEAD@{17}: rebase (finish): returning to refs/heads/main
4b5a09b HEAD@{18}: rebase (start): checkout HEAD~1
3f7efaa HEAD@{19}: commit: Unwanted commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)       
$

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)       
$ git checkout HEAD@{4}
Note: switching to 'HEAD@{4}'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false        

HEAD is now at 4d77207 added sltn to qtn 6 in the read me

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((4d77207...)If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false        

HEAD is now at 4d77207 added sltn to qtn 6 in the read me

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((4d77207...)

HEAD is now at 4d77207 added sltn to qtn 6 in the read me

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((4d77207...)adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((4d77207...))

$ git reset --hard HEAD@{4}
HEAD is now at d98b949 Implemented test 5

```


## part 2 challenge 1
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch
  ft/branch
* ft/new-feature
  main

```

## part 2 Challenge 2 

```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> echo "Core functionality for the 
new feature" > feature.txt

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git add feature.txt

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git commit -m "Implemented core functionality for new feature"
[ft/new-feature 2a766ad] Implemented core functionality for new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt
```


## part 2 Challenge 3
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout main
M       README.md
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> echo "Welcome to the project. This is the introductory content." > readme.txt

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git add readme.txt

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git commit -m "Updated project readme"
[main 2b695a1] Updated project readme
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.txt
```
## part 2 Challenge 4
```bash 

```
## part 2 Challenge 5
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout main
M       README.md
Already on 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
  

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch -D ft/new-feature     
Deleted branch ft/new-feature (was 2a766ad).

```
## part 2 Challenge 6
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git log --oneline
2b695a1 (HEAD -> main) Updated project readme
9346aad (origin/main, origin/HEAD) all part 1 solutions
a475b6b so;ution to exercise 9
40983bb Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym   
6cc990e Added solution to the 7th and 8th exercise of the first part
d98b949 Implemented test 5
4d77207 added sltn to qtn 6 in the read me
f806dfd done with the first 5 challenges of the first part
4b5a09b done with the first 5 challenges of the first part
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
744e3d9 exercise restart
c103e24 chore: Save work before rebase
f873b72 chore: Create third and fourth files
67da5d0 chore: Create another file

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout -b ft/new-branch-from-commit 9346aad
M       README.md
Switched to a new branch 'ft/new-branch-from-commit'

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch
  ft/branch
* ft/new-branch-from-commit
  main

```

## part 2 Challenge 7
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout main
M       README.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git merge ft/new-branch-from-commit
Already up to date.
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git add .

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git commit -m "Merged ft/new-branch-from-commit into main"
[main a78bbdf] Merged ft/new-branch-from-commit into main
 1 file changed, 95 insertions(+)

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch --merged
  ft/new-branch-from-commit
* main
```

## part 2 Challenge 8
```bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout ft/new-branch-from-commit
Already on 'ft/new-branch-from-commit'

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git push origin ft/new-branch-from-commit --force
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1.67 KiB | 189.00 KiB/s, done.
Total 9 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (5/5), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/new-branch-from-commit' on GitHub by visiting:
remote:      https://github.com/adeline333/advanced_git_exercises_gym/pull/new/ft/new-branch-from-commit     
remote:
To https://github.com/adeline333/advanced_git_exercises_gym.git
 * [new branch]      ft/new-branch-from-commit -> ft/new-branch-from-commit
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> 
```

## part 2 Challenge 9
```bash
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout ft/new-branch-from-commit
M       README.md
Already on 'ft/new-branch-from-commit'
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch -m ft/improved-branch-name
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git branch
  ft/branch
* ft/improved-branch-name
  main
```



## Part 2 Challenge 10
``` bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git log --oneline
59fb274 (HEAD -> ft/improved-branch-name, origin/ft/new-branch-from-commit, origin/ft/improved-branch-name, main) part 2 read me (8) challenges
a78bbdf Merged ft/new-branch-from-commit into main
2b695a1 Updated project readme
9346aad (origin/main, origin/HEAD) all part 1 solutions
a475b6b so;ution to exercise 9
40983bb Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
6cc990e Added solution to the 7th and 8th exercise of the first part
d98b949 Implemented test 5
4d77207 added sltn to qtn 6 in the read me
2b14897 chore: Create third and fourth file
392e7a2 chore: Squashed create second file
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout 9346aad
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting 

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git checkout 9346aad                               
Note: switching to '9346aad'.

You are in 'detached HEAD' state. You can look around, make experimental
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 9346aad all part 1 solutions

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git status
HEAD detached at 9346aad
nothing to commit, working tree clean
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> 
```

Main branch changes: This is an update in the README on the main branch.



## Part 3 Challenge 1
``` bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git status
Your branch is up to date with 'origin/main'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git stash
Saved working directory and index state WIP on main: 8636576  part 2 exercise solutions

PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git stash list
stash@{0}: WIP on main: 8636576 part 2 exercise solutions
On branch main

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (d58ebbf489e1abc41cb054855299f05859a92507)
```


## Part 3 Challenge 2
``` bash 
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git stash list

stash@{0}: WIP on main: 8636576 part 2 exercise solutions
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (b8b340ffabc94d6ad030b855e821b5a0a5d12e0f)
```


## Part 3 Challenge 3
``` bash


working on merging conflicts
$ git checkout -b ft/feature-conflict
Switched to a new branch 'ft/feature-conflict'

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/feature-conflict)   
$ git add README.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/feature-conflict)   
$ git commit -m "changes in README on feature branch"
[ft/feature-conflict 79c41c0] changes in README on feature branch
 1 file changed, 50 insertions(+)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (ft/feature-conflict)   
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git add README.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git commit -m " Changes in README on main branch"
[main e82918a]  Changes in README on main branch
 1 file changed, 1 insertion(+)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git checkout main
Already on 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git merge ft/feature-conflict
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main|MERGING)
$ git add README.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main|MERGING)
$ git commit -m "Merged changes from main and feature branch"
[main 92af326] Merged changes from main and feature branch

```

## Part 3 Challenge 4
``` bash
git config --global merge.tool vimdiff2
PS C:\Users\adeli\Downloads\advanced_git_exercises_gym-1> git mergetool
Merging:
README.md

Normal merge conflict for 'README.md':
  {local}: modified file
  {remote}: modified file
4 files to edit
```

## Part 3 Challenge 5
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (main)
$ git checkout 92af326
Note: switching to '92af326'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false 

HEAD is now at 92af326 Merged changes from main and feature branch


adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((92af326...))
$ git status                                                                 326...))
HEAD detached at 92af326
nothing to commit, working tree clean

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((92af326...))                                                                     326...))
$ echo "Detached HEAD change" >> README.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((92af326...))
$ git commit -am "Made a change in detached HEAD"
warning: in the working copy of 'README.md', LF will be replaced by CRLF the 
next time Git touches it
[detached HEAD 2b8dc95] Made a change in detached HEAD
 1 file changed, 1 insertion(+)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 ((2b8dc95...))
$ git checkout -b saved-detached-branch
Switched to a new branch 'saved-detached-branch'

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym-1 (saved-detached-branch)
$ git log --oneline
2b8dc95 (HEAD -> saved-detached-branch) Made a change in detached HEAD
92af326 Merged changes from main and feature branch
e82918a  Changes in README on main branch
79c41c0 (ft/feature-conflict) changes in README on feature branch
8636576  part 2 exercise solutions
59fb274 (origin/ft/new-branch-from-commit, origin/ft/improved-branch-name) part 2 read me (8) challenges
a78bbdf Merged ft/new-branch-from-commit into main
2b695a1 Updated project readme
9346aad all part 1 solutions
a475b6b so;ution to exercise 9
40983bb Merge branch 'main' of https://github.com/adeline 333/advanced_git_exercises_gym
6cc990e Added solution to the 7th and 8th exercise of the first part
d98b949 Implemented test 5
```

## Part 3 Challenge 6
```bash

```