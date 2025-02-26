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
