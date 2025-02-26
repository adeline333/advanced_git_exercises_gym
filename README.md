# advanced_git_exercises_gym


## Getting started
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ touch test{1..4}.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git add test1.md && git commit -m "chore: Create initial file"
[main 52a1150] chore: Create initial file       
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git add test2.md && git commit -m "chore: Create another file"
[main a16d45d] chore: Create another file       
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main faa32bb] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

```

## Part 1   
## 1.Missing File Fix:
```bash
adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)       
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git log --oneline
faa32bb (HEAD -> main) chore: Create third and fourth files
a16d45d chore: Create another file
52a1150 chore: Create initial file
f63a00a (origin/main, origin/HEAD) getting started
16bfb8f chore:Create third and fourth files
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git add test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
3766e1f chore: Create another file
352e0d9 chore: Create initial file
ffc4e7a Initial commit

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git add test4.md

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)

adeli@DESKTOP-SGKPF3E MINGW64 ~/Downloads/advanced_git_exercises_gym (main)
$ git commit --amend -m "chore: Create third and fourth files"
$ git commit --amend -m "chore: Create third and fourth files"
$ git commit --amend -m "chore: Create third and fourth files"
[main fffeca3] chore: Create third and fourth files
 Date: Wed Feb 26 12:05:19 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md                                                      

```

## Part 1   
## 2. Editing Commit History: