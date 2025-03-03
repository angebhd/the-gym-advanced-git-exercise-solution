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