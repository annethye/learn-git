# ASCII Portfolio
ASCII art is art made from only the letters, numbers and symbols you can type on your keyboard.

In this project, you’ll use Git backtracking commands to undo mistakes made to an ASCII art portfolio!

This project contains 3 files: 
- portrait.txt
- tree.txt
- house.txt


### 1. Discard changes to portrait.txt
Let's look at our project status.
```bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   portrait.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        house.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
Now let's see what has been commited.
```bash
$ git log
commit 8dd5126a5c0845d8e1d780706054903ac7721445
Author: danasselin <johndoe@example.com>
Date:   Thu Nov 19 12:08:42 2015 -0500

    Add goatee

commit 91711fc47253fcca4143923e5de4244e840548af
Author: danasselin <johndoe@example.com>
Date:   Thu Nov 19 12:07:30 2015 -0500

    Add dates

commit 0b7768ede8d03abfae8cd4797f3d8ef50bdd2f6c
Author: danasselin <johndoe@example.com>
Date:   Thu Nov 19 11:46:09 2015 -0500

    Change dimensions and positioning of tree

commit a99d80c10480bf77f3cd6d5ee6a4e0cfd29ed48d
Author: danasselin <johndoe@example.com>
Date:   Thu Nov 19 11:40:06 2015 -0500

    Add stump to tree

commit 7bf64043a20bfb2bf9603c19755c43f00a1126e6
Author: danasselin <johndoe@example.com>
Date:   Thu Nov 19 11:37:59 2015 -0500

    Start tree ASCII pic
```
Let's open the portrait.txt file:
```
            ___________
           /           \
          /             \
         |               |
        C|    O     O    |C
         |               |
         |               |
          \        >    /
           |           |
           |           |
           |   -----   |
            \         /
             \_______/


November 12, 2014       
```
The ASCII face in portrait.txt had a goatee in the last commit, but it was deleted in the working directory.
Taking a second look, you want the goatee back. Discard changes in the working directory.
```bash
$ git checkout -- portrait.txt
```
Close and reopen portrait.txt to see the result:
```
            ___________
           /           \
          /             \
         |               |
        C|    O     O    |C
         |               |
         |               |
          \        >    /
           |           |
           | MMMMMMMMM |
           |   -----   |
            \  MMMMM  /
             \__MMM__/
                MMM

November 12, 2014
```

### 2. Add eyebrows in portrait.txt 
That’s much better! Now, give your portrait some eyebrows and save the file.
```
            ___________
           /           \
          /             \
         |   ===   ===   |
        C|    O     O    |C
         |               |
         |               |
          \        >    /
           |           |
           | MMMMMMMMM |
           |   -----   |
            \  MMMMM  /
             \__MMM__/
                MMM

November 12, 2014
```

### 3. Add portrait.txt to staging area
```bash
$ git add portrait.txt
```

### 4. Commit changes
```bash
$ git commit -m "Adding eyebrows to portrait"
[master 5b0de0a] Adding eyebrows to portrait
 1 file changed, 1 insertion(+), 1 deletion(-)
```

### 5. Change completion dates of files
It looks like every file has its date written incorrectly. Change the completion dates on every file to:
```
February 22, 2022
```
Remember to save all three files.

### 6. Add changes to staging area
Next, add all your changes to the staging area with a single command.
```bash
$ git add house.txt portrait.txt tree.txt
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   house.txt
        modified:   portrait.txt
        modified:   tree.txt
```

### 7. Make a commit
```bash
$ git commit -m "Correcting dates on all files"
[master 147a46f] Correcting dates on all files
 3 files changed, 19 insertions(+), 2 deletions(-)
 create mode 100644 house.txt
```

### 8. Add artist name to files
You forgot to add your “artist name” to each file. Under the date, include the name:
```
L. Da Vinci
```
Save all three files again.

### 9. Add all files to staging area
If you know you want to add every file in the working directory to the staging area, instead of adding each file individually, you can use a shortcut `.` meaning all files.
```bash
$ git add .
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   house.txt
        modified:   portrait.txt
        modified:   tree.txt
```

### 10. Unstage house.txt
It turns out that house.txt is an experiment and doesn’t belong in the commit you’re staging. Reset the staging area to remove house.txt.
```bash
$ git reset -- house.txt
Unstaged changes after reset:
M       house.txt
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   portrait.txt
        modified:   tree.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   house.txt
```

### 11. Commit changes
Now make a commit.
```bash
$ git commit -m "Adding artist name to tree and portrait"
[master f5adbdb] Adding artist name to tree and portrait
 2 files changed, 3 insertions(+), 1 deletion(-)
```

### Current state of files

portrait.txt
```
            ___________
           /           \
          /             \
         |   ===   ===   |
        C|    O     O    |C
         |               |
         |               |
          \        >    /
           |           |
           | MMMMMMMMM |
           |   -----   |
            \  MMMMM  /
             \__MMM__/
                MMM

November 12, 2014
```

tree.txt
```
                ^
               / \
              /   \
             /_   _\
             /     \
            /_     _\
            /       \
           /_       _\
           /         \
          /_         _\
           /         \
          /           \
         /_____________\
               | |
             __| |___

February 22, 2022
L. Da Vinci
```

house.txt
```
          /\          _____________
         /  \        /             \
        /    \      /               \
       /______\    /                 \
       |      |    |                 |
       |      |____|                 |
       |                             |
       |                             |
       |                             |
       |                             |
    ======================================

February 22, 2022
L. Da Vinci
```