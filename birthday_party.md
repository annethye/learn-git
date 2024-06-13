# Birthday Party
Let’s practice some Git branching.

In this project, you’ll be using Git to make a 1-page website for your friend Kay’s birthday party.

### 1. List the Git branches
```
$ git branch
* master
  moma
  whitney
```

### 2. Delete the branches moma and whitney
Kay wasn’t sure where she wanted to host the party, so you made several Git branches to explore different locations. Some of the branches are no longer needed. The option -D is necessary as these feature branches were never merged into master.
```
$ git branch -D moma whitney
Deleted branch moma (was 978e5a1).
Deleted branch whitney (was 9b384f9).
```

### 3. Create a new branch called unordered-list and switch over to it.
Kay wants to see a version of the webpage that includes an unordered list with bullet points instead of a paragraph to show information about the party.
```
$ git branch unordered-list
$ git checkout unordered-list
Switched to branch 'unordered-list'
```

### 4. Edit text in index.html
Open index.html and replace the following line:
```
<p>Description: Join Kay in celebrating their 29th birthday with free food and beverages, karaoke and a special appearance by Willy Nelson. Also, feel free to explore the Met museum before or after you stop by! Presents for Kay optional.</p>
```
with this unordered list:
```
<ul>
    <li>Join Kay in celebrating their 29th birthday with free food and beverages</li>
    <li>karaoke and a special appearance by Willy Nelson</li>
    <li>explore the Met museum before or after you stop by!</li>
    <li>Birthday presents optional</li>
</ul>
```
and save the file.

### 5. Add index.html to the staging area
```
$ git add index.html
```

### 6. Now make a commit
Add descriptive commit message.
```
$ git commit -m "Arranging info in unordered list"
[unordered-list dad7628] Arranging info in unordered list
 1 file changed, 7 insertions(+), 1 deletion(-)
```

### 7. Switch to master and merge
Kay approves the changes you made in the unordered-list branch. Now switch to master and merge unordered-list into master. This will be a fast forward merge.
```
$ git checkout master
Switched to branch 'master'
$ git merge unordered-list
Updating 1481f5a..dad7628
Fast-forward
 index.html | 8 +++++++-
 1 file changed, 7 insertions(+), 1 deletion(-)
```

### 8. Create new branch big-heading
Kay wants the heading to be way bigger. Create a new branch big-heading to make the changes.
```
$ git branch big-heading
```

### 9. Switch branch to big-heading and edit index.html
Switch branch to big-heading
```
$ git checkout big-heading
Switched to branch 'big-heading'
```
Open index.html and replace the following line:
```
<h1>Kay's Birthday Party</h1>
```
with this line:
```
<h1 style="font-size: 72px">Kay's Birthday Party</h1>
```
This results in a bigger heading. Remember to save the file.

### 10. Add index.html to the staging area
```
$ git add index.html
```

### 11. Make a commit
```
$ git commit -m "Heading size enlarged"
[big-heading e003597] Heading size enlarged
 1 file changed, 1 insertion(+), 1 deletion(-)
```

### 12. Switch to master and merge 
Kay approves of the giant heading!
Switch back over to the master branch. Then, merge big-heading into master.
```
$ git checkout master
Switched to branch 'master'
$ git merge big-heading
Updating dad7628..e003597
Fast-forward
 index.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```
