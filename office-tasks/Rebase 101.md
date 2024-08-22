#  What is `rebase` and its similarities with merge

- The first thing to understand about `git rebase` is that it solves the same problem as `git merge`. Both of these commands are designed to integrate changes from one branch into another branch—they just do it in very different ways.

- ![[Pasted image 20240708140228.png]]

- the command `git merge feature main` or `git checkout feature;git merge main` results in:
![[Pasted image 20240708140326.png]]

**Notice HOW there is an additional merge commit when using merge**

Here is what rebase does : 

![[Pasted image 20240708141656.png]]

### Things to keep in mind while rebasing:

1. Never rebase public branches for e.g. if you rebase main onto feature, the new main you have would be different from everybody else's main which will cause a problem.
2. Rebase first then raise a PR.
   
## If you're working solo,

1.  let the PR merge
2. pull dev from origin
3. start new branch from dev
4. make changes , commit
5. checkout to new branch
6. `git rebase dev`
7. push origin new branch
8. raise a PR

## Now in case there are multiple people working parallelly,

Follow these steps:

1. create a new branch from `dev`
2. make changes on this new branch `feat/new-feature`   (DO NOT COMMIT)
3. as mentioned in earlier step, **do not commit** you may _**shelve the changes.**_
4. Now when the feature is ready, you don't have an idea whether other PRs have been merged or not. So what you do is,   
      
    `git checkout dev`  
      
    `git pull origin dev`  
      
    `git checkout feat/new-feature`  
      
    `git commit`  (of course git add first)
      
    `git rebase dev`  
      
    `git push origin feat/new-feature`  
      
    
5. You're all set to raise a PR `dev -> feat/new-feature`.