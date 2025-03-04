# Advanced Git Exercises Solutions

## Part 1 : Refining Git History

### 1. Missing File Fix

```bash
gymkura@kuras-iMac the-gym-advanced-git-exercise % git status
On branch master
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	test4.md

nothing added to commit but untracked files present (use "git add" to track)
gymkura@kuras-iMac the-gym-advanced-git-exercise % git log
commit abd766e577e5236bde79e8a9c89778521ec29a38 (HEAD -> master)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create third and fourth files

commit d6f04b333c6f821f1eb5d0fc0fd401ef7583cb79
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create another file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
gymkura@kuras-iMac the-gym-advanced-git-exercise % git add test4.md     
gymkura@kuras-iMac the-gym-advanced-git-exercise % git reset --soft HEAD~1                           
gymkura@kuras-iMac the-gym-advanced-git-exercise % git log
commit d6f04b333c6f821f1eb5d0fc0fd401ef7583cb79 (HEAD -> master)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create another file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
gymkura@kuras-iMac the-gym-advanced-git-exercise % git status
On branch master
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   test3.md
	new file:   test4.md

gymkura@kuras-iMac the-gym-advanced-git-exercise % git add .
gymkura@kuras-iMac the-gym-advanced-git-exercise % git commit -m "chore: Create third and fourth files"
[master 59fcd60] chore: Create third and fourth files
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
gymkura@kuras-iMac the-gym-advanced-git-exercise % git log
commit 59fcd60f482d6293e98f4806f822b2079e6d9048 (HEAD -> master)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:53:56 2025 +0200

    chore: Create third and fourth files

commit d6f04b333c6f821f1eb5d0fc0fd401ef7583cb79
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create another file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
gymkura@kuras-iMac the-gym-advanced-git-exercise % git status
On branch master
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
gymkura@kuras-iMac the-gym-advanced-git-exercise % 

```





### 2. Editing Commit History

```bash

gymkura@kuras-iMac the-gym-advanced-git-exercise % git log
commit 59fcd60f482d6293e98f4806f822b2079e6d9048 (HEAD -> main)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:53:56 2025 +0200

    chore: Create third and fourth files

commit d6f04b333c6f821f1eb5d0fc0fd401ef7583cb79
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create another file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file

---
edit d6f04b3 chore: Create second file
pick 59fcd60 chore: Create third and fourth files

# Rebase 283b826..59fcd60 onto 283b826 (2 commands)
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
---
git rebase -i HEAD~2
Stopped at d6f04b3...  chore: Create second file
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue
gymkura@kuras-iMac the-gym-advanced-git-exercise % git commit --amend
---
chore: Create second file

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Wed Feb 26 15:43:54 2025 +0200
#
# interactive rebase in progress; onto 283b826
# Last command done (1 command done):
#    edit d6f04b3 chore: Create second file
# Next command to do (1 remaining command):
#    pick 59fcd60 chore: Create third and fourth files
# You are currently editing a commit while rebasing branch 'main' on '283b826'.
#
# Changes to be committed:
#       new file:   test2.md
#
---
[detached HEAD 687414d] chore: Create second file
 Date: Wed Feb 26 15:43:54 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
gymkura@kuras-iMac the-gym-advanced-git-exercise % git rebase --continue
Successfully rebased and updated refs/heads/main.
gymkura@kuras-iMac the-gym-advanced-git-exercise % git log
commit 16b419d58298a7803e1e46f69732ddc9e0f7e3f9 (HEAD -> main)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:53:56 2025 +0200

    chore: Create third and fourth files

commit 687414d844919e56825dccf28f10c8d895f6242d
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create second file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
gymkura@kuras-iMac the-gym-advanced-git-exercise % 

```

### 3. Keeping History Tidy - Squashing Commits

### 4. Splitting a Commit

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git reset HEAD~
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test3.md
	test4.md

nothing added to commit but untracked files present (use "git add" to track)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add test3.md 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "chore: Create third file"
[main 2c506ce] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add test4.md 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "chore: Create fourth file"
[main bd070ed] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ 

```

### 5. Advanced Squashing

```bash

mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit bd070edcee0e871c8b07dbfb1338bbf06cff4609 (HEAD -> main)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:35:06 2025 +0200

    chore: Create fourth file

commit 2c506ce2dcf0ba21a3a85ff01b7d91b2cd681a01
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file

commit cd631b9beed27cdc5f0f5bce4c6567e1d85d526c
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git rebase -i HEAD~2
[detached HEAD 15ce09d] chore: Create third file and fourth file
 Date: Mon Mar 3 11:34:47 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 15ce09de075131abd9f9b45a23c0b7d5087be36f (HEAD -> main)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit cd631b9beed27cdc5f0f5bce4c6567e1d85d526c
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file

```
### 6. Dropping a Commit

```bash

mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ touch unwanted.txt
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	unwanted.txt

nothing added to commit but untracked files present (use "git add" to track)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git pull
Updating 15ce09d..971e109
Fast-forward
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 971e1095a48ce918eaf35edfdd146467fa8f05db (HEAD -> main, origin/main, origin/HEAD)
Merge: 15ce09d 4d66ebc
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:59:00 2025 +0200

    Merge remote-tracking branch 'refs/remotes/origin/main'

commit 15ce09de075131abd9f9b45a23c0b7d5087be36f
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 4d66ebc58b656c28f2cb8e08dce3be9fae614b70
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:41:20 2025 +0200

    chore: Create third and fourth files

mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	unwanted.txt

nothing added to commit but untracked files present (use "git add" to track)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add unwanted.txt 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "Unwanted commit"
[main e7de586] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git reset --hard HEAD~1
HEAD is now at 971e109 Merge remote-tracking branch 'refs/remotes/origin/main'
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git push origin HEAD --force
Everything up-to-date
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 971e1095a48ce918eaf35edfdd146467fa8f05db (HEAD -> main, origin/main, origin/HEAD)
Merge: 15ce09d 4d66ebc
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:59:00 2025 +0200

    Merge remote-tracking branch 'refs/remotes/origin/main'

commit 15ce09de075131abd9f9b45a23c0b7d5087be36f
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 4d66ebc58b656c28f2cb8e08dce3be9fae614b70
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:41:20 2025 +0200

    chore: Create third and fourth files

commit cd631b9beed27cdc5f0f5bce4c6567e1d85d526c
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ 

```

### 7. Reordering Commits


```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 5beb7bf357a3d4d5828d247bff5b2a0680cf76d4 (HEAD -> main)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 463b388ede194866e8751f1009cab2407cec37e8
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 4cfcd9794f2c85bbadb60a71d4200dc3404b46ce
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file
    
    chore: Create third file and fourth file
    
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ cd ..
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym$ cd the-gym-advanced-git-exercise
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 6eff7a5a59289f6f8763b476b9350e81243b0853 (HEAD -> main)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit cd631b9beed27cdc5f0f5bce4c6567e1d85d526c
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git rebase -i 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Successfully rebased and updated refs/heads/main.
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git rebase --continue
fatal: No rebase in progress?
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 2e68a4cbf9e9c1319410e26e827b5b8f1be2f239 (HEAD -> main)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 003d2d1c87c07d96d2568cdf5f7a0e19506efa3b
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Wed Feb 26 15:43:54 2025 +0200

    chore: Create initial file
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ 

```

### 8. Cherry-Picking Commits
```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ touch test5.md
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ vim test5.md 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
* ft/branch
  main
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add test5.md 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "Implemented test 5"
[ft/branch c0fff1b] Implemented test 5
 1 file changed, 2 insertions(+)
 create mode 100644 test5.md
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit c0fff1b4ae2658cb4394df4355e2020914b0dd1b (HEAD -> ft/branch)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 13:12:37 2025 +0200

    Implemented test 5

commit 2e68a4cbf9e9c1319410e26e827b5b8f1be2f239 (main)
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 003d2d1c87c07d96d2568cdf5f7a0e19506efa3b
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200

    chore: Create third file and fourth file

commit 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 2 and 6 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
* main
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git cherry-pick --no-commit c0fff1b4ae2658cb4394df4355e2020914b0dd1b
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 6 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test5.md

mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ 
```

### 9. Visualizing Commit History (Bonus)

```bash
git log --graph
```

### 10. Understanding Reflogs (Bonus)

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git reflog 
2e68a4c (HEAD -> main) HEAD@{0}: checkout: moving from ft/branch to main
c0fff1b (ft/branch) HEAD@{1}: commit: Implemented test 5
2e68a4c (HEAD -> main) HEAD@{2}: checkout: moving from main to ft/branch
2e68a4c (HEAD -> main) HEAD@{3}: rebase (finish): returning to refs/heads/main
2e68a4c (HEAD -> main) HEAD@{4}: rebase (pick): chore: Create second file
003d2d1 HEAD@{5}: rebase (pick): chore: Create third file and fourth file
283b826 HEAD@{6}: rebase (start): checkout 283b8267329ab1ff1d325e4a1849685a1b0ef9b8
6eff7a5 HEAD@{7}: rebase (finish): returning to refs/heads/main
6eff7a5 HEAD@{8}: rebase (start): checkout HEAD~
ce3596a (origin/main, origin/HEAD) HEAD@{9}: clone: from https://github.com/angebhd/the-gym-advanced-git-exercise.git

```

## Part 2 : Branching Basics

### 1. Feature Branch Creation

```bash
git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

```

### 2. Working on the Feature Branch

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ touch feature.txt
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ vim feature.txt 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add feature.txt 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "Implemented core functionality for new feature"
[ft/new-feature eb26b5d] Implemented core functionality for new feature
 2 files changed, 3 insertions(+)
 create mode 100644 feature.txt
 create mode 100644 test5.md
```

### 3. Switching Back and Making More Changes
 
```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ touch readme.txt
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ vim readme.txt 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add readme.txt 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "Updated project readme"
[main eba42aa] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

### 4. Local vs. Remote Branches

[Local vs. Remote Branches](https://www.baeldung.com/ops/git-synchronize-local-remote-branches)

### 5. Branch Deletion

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
  ft/new-feature
* main
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git merge ft/new-feature 
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 test5.md    | 2 ++
 2 files changed, 3 insertions(+)
 create mode 100644 feature.txt
 create mode 100644 test5.md
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch -d ft/new-feature 
Deleted branch ft/new-feature (was eb26b5d).
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
* main
```

### 6. Creating a Branch from a Commit

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout -b ft/new-branch-from-commit eba42aa1a35061f1cd2cc3b970a0b9d302778e53
Switched to a new branch 'ft/new-branch-from-commit'

```

### 7. Branch Merging

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
* ft/new-branch-from-commit
  main
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ mv readme.md README
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git add .
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git commit -m "Renaming readme file"
[ft/new-branch-from-commit 7a023e6] Renaming readme file
 1 file changed, 1 insertion(+)
 create mode 100644 README
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout main 
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 5 and 6 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git merge ft/new-branch-from-commit 
Merge made by the 'ort' strategy.
 README | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README

```

### 8. Branch Rebasing

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 7a023e67f55bbbad7bce24afec52e29cf00d5c78 (HEAD -> ft/new-branch-from-commit)
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Tue Mar 4 10:50:52 2025 +0200

    Renaming readme file

commit eb26b5deac431070e60674d9251a0d0cd2eef0be
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 14:01:27 2025 +0200

    Implemented core functionality for new feature

commit 2e68a4cbf9e9c1319410e26e827b5b8f1be2f239
Author: Asifiwe Buhendwa <mickaelbhd@gmail.com>
Date:   Mon Mar 3 10:40:55 2025 +0200

    chore: Create second file

commit 003d2d1c87c07d96d2568cdf5f7a0e19506efa3b
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Mon Mar 3 11:34:47 2025 +0200
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git log
commit 50bff9312609f943a9758c2c15172565bfc78cc3 (HEAD -> ft/new-branch-from-commit, main)
Merge: 1648968 7a023e6
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Tue Mar 4 10:51:16 2025 +0200

    Merge branch 'ft/new-branch-from-commit'

commit 7a023e67f55bbbad7bce24afec52e29cf00d5c78
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Tue Mar 4 10:50:52 2025 +0200

    Renaming readme file

commit 16489686c9118b2415365435fed90496171950d4
Merge: eba42aa eb26b5d
Author: Asifiwe BUHENDWA <mickaelbhd@gmail.com>
Date:   Tue Mar 4 10:34:00 2025 +0200

    Adding new fearure from 'ft/new-feature' branch


```

### 9. Renaming Branches

```bash
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
* ft/new-branch-from-commit
  main
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch -m ft/new-branch-from-commit ft/google-auth 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git branch
  ft/branch
* ft/google-auth
  main

```

### 10. Checking Out Detached HEAD

```bash

mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout 003d2d1c87c07d96d2568cdf5f7a0e19506efa3b
Note: switching to '003d2d1c87c07d96d2568cdf5f7a0e19506efa3b'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 003d2d1 chore: Create third file and fourth file
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
HEAD detached at 003d2d1
nothing to commit, working tree clean
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ 
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ touch tes5
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git status
HEAD detached at 003d2d1
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	tes5

nothing added to commit but untracked files present (use "git add" to track)
mickael-angebhd@AngeBHD-PC:~/Desktop/The Gym/the-gym-advanced-git-exercise$ git checkout main
Previous HEAD position was 003d2d1 chore: Create third file and fourth file
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 7 and 6 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

```



