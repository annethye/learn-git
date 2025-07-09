# JavaScript Homework
Let’s keep applying the Git collaboration skills we’re learning.

In this project, we’ll be using Git to write comments on your student’s JavaScript homework.


### 1. Clone remote
There is a remote called maryrose-hw which contains your student’s JavaScript homework.

Clone the remote, giving it the name maryrose-hw-local
```
$ pwd
/home/ccuser/workspace/js-homework
$ ls
maryrose-hw
$ git clone maryrose-hw maryrose-hw-local
Cloning into 'maryrose-hw-local'...
done.
$ ls
maryrose-hw  maryrose-hw-local
```

### 2. Move into the cloned repository
Move into the maryrose-hw-local repository.
```
$ cd maryrose-hw-local/
```

### 3. Open homework.js in code editor
Use the file navigator to open homework.js in the code editor. These are the contents of homework.js in the clone not the remote:
```
// Mary Rose's JavaScript Homework

// 1. Write an if/else statement
var APPLE_QUANTITY = 5;

if (APPLE_QUANTITY < 5){
  console.log("You have fewer than 5 apples.");
} else {
  console.log("You have 5 or more apples. Hurrah!");
}

// 2. Write a "for" loop
for(i = 0; i < APPLE_QUANTITY; i ++){
  console.log("WEEEEEEE! I'm looping!")
}

// 3. Write a function
var sayHello = function(){
  console.log("Hello!")
}

// 4. Create an object
var mary = {
  name: "Mary Rose",
  codeNinja: true,
  country: "UK"
}
```

### 4. Create new branch
From the terminal, create a new branch with Git. This branch will be used to comment on Mary Rose’s JavaScript homework, so it will be named maryrose-hw-comments. 

Remember to switch to the new branch.
```
$ git branch maryrose-hw-comments
$ git checkout maryrose-hw-comments
Switched to branch 'maryrose-hw-comments'
```

### 5. Leave comments
Time to start commenting on Mary Rose’s JavaScript homework.

The following comments are added to the bottom of the file homework.js and the file is saved:
```
// Very clear and good code execution! Good work.
// I would appreciate more comments in your code to explain behaviour.
// Try let or const instead of var.
// Remember semicolons after all function calls.
```

### 6. Add changes to the staging area
```
$ git add homework.js
```

### 7. Make a commit
```
$ git commit -m "Correction of Mary Rose's js homework"
[maryrose-hw-comments 2425336] Correction of Mary Rose's js homework
 1 file changed, 7 insertions(+)
```

### 8. Push branch to remote
Push your branch up to the remote.
```
$ git push origin maryrose-hw-comments
Counting objects: 3, done.
Delta compression using up to 16 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 444 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To /home/ccuser/workspace/js-homework/maryrose-hw
 * [new branch]      maryrose-hw-comments -> maryrose-hw-comments
```

### 9. Inspect branch you pushed
Change directories back to the remote
```
cd ../maryrose-hw
```
Now take a look at the new branch that has been pushed to the remote.
```
$ git branch
  maryrose-hw-comments
* master
```