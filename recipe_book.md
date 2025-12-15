# Recipe Book
Let’s continue practicing our Git collaboration skills.

In this project, you’ll be playing the role of two collaborators working on a recipe book.

### 1. Move into the remote
Inspecting the folder we see the remote veggie-favorites and the clone veggie-clone.
```
$ pwd
/home/ccuser/workspace/recipe-book-a
$ ls
veggie-clone  veggie-favorites
```
Let's move into the remote veggie-favorites. 
```
$ cd veggie-favorites
```

### 2. Edit files, add and commit changes
Inside veggie-favorites make a change to chili.txt and squash-lasagna.txt in the code editor.

More chili powder should be added to the two recipes, so the following line was added to chili.txt and squash-lasagna.txt and the file was saved.
```
2 tbsp chili powder
```

Add changes to the Git staging area, and make a commit.
```
$ git branch
* master
$ git add chili.txt squash-lasagna.txt
$ git commit -m "Adding more chili to chili and squash-lasagna"
[master 2550ddc] Adding more chili to chili and squash-lasagna
2 files changed, 2 insertions(+)
```

### 3. Move into your clone
Move into your clone veggie-clone.
```
cd ../veggie-clone
```

### 4. Fetch from remote
Fetch all new work from the remote.
```
$ git branch
* master
$ git fetch
remote: Counting objects: 13, done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 13 (delta 7), reused 0 (delta 0)
Unpacking objects: 100% (13/13), done.
From /home/ccuser/workspace/recipe-book-a/veggie-favorites
 * [new branch]      master     -> origin/master
```

### 5. Merge changes
Merge origin/master into your local master branch.
```
$ git merge origin/master
Updating 4681ee4..2550ddc
Fast-forward
chili.txt          | 15 ++++++++-------
margherita.txt     | 11 +++++++----
squash-lasagna.txt |  4 +++-
3 files changed, 18 insertions(+), 12 deletions(-)
```
This was a simple fast-forward merge.

### 6. Create new branch and switch to it
Create a new branch, then switch over to it, to work on new-recipe.txt. The recipe can be whatever dish you’d like.

As we're working on a new recipe the new branch will be called new_recipe.
```
$ git branch new_recipe
$ git checkout new_recipe
Switched to branch 'new_recipe'
```
A falafel recipe was added to the file new_recipe.txt and saved.

### 7. Add and commit file
Add your file changes to the staging area and make a commit.
```
$ git add new-recipe.txt
$ git commit -m "Added new recipe for falafel"
[new_recipe d4d087d] Added new recipe for falafel
1 file changed, 18 insertions(+)
```

### 8. Fetch
Fetch one more time just for good measure.
```
$ git fetch
```
We confirm that there have been no changes.

### 9. Push your branch up to the remote.
Push the branch new_recipe to the origin (veggie-favorites)
```
$ git push origin new_recipe
Counting objects: 3, done.
Delta compression using up to 16 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 512 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To /home/ccuser/workspace/recipe-book-a/veggie-favorites
 * [new branch]      new_recipe -> new_recipe
```

### 10. Confirm presence of new branch in remote
Navigate back to the remote.
```
cd ../veggie-favorites
```
Confirm the presence of the new Git branch here.
```
$ git branch
* master
  new_recipe
```
We see that the new_recipe branch has been pushed to the remote origin repository.