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