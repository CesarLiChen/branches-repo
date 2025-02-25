# branches-repo

A new commit from the branch: **new-branch**

This will be the conflicting line. **main**.
New line inserted. **new-branch**

`git branch <branch-name>` -Creates a branch with given **branch-name**.  
`git checkout <branch-name>` -Switches to the stated branch.  
`git merge <branch-to-merge>` - After everything's done, merge branch.  

If there are merge conflicts:

   - Open problematic file, and do changes manually.
   - `git add .` and `git commit -m "<Commit message>"`

END  

2025-02-25:
- A change was made to repo from a *Remote* branch.
- On my cloned *Local* branch I did **not** `git pull` first.
   - Did changes on the same ***file*** that was now different in the *Remote* branch.
   - Did usual `git add .` -> `git commit -m "blah blah"` -> `git push`  
   - When `git push` was done, I was welcomed with:
      - Error msg 
     ```
      ! [rejected]        main -> main (fetch first)
      error: failed to push some refs to 'github.com:CesarLiChen/blahblah.git'
      hint: Updates were rejected because the remote contains work that you do
      hint: not have locally. This is usually caused by another repository pushing
      hint: to the same ref. You may want to first integrate the remote changes
      hint: (e.g., 'git pull ...') before pushing again.
      hint: See the 'Note about fast-forwards' in 'git push --help' for details.
      ```
- Things done to "fix" it, at least I think it's fixed.
   - `git fetch` gets changes from remote repo to local repo without merging.
   - `git diff {remoteBranch} {localBranch}` e.g. `git diff origin/main main`.
   - `git rebase`
      - Outputs to terminal the name(s) of the problematic file(s).
   - Opened problematic file(s) with Vim. (you could use any other text editor).
   - A few `<<<<<< HEAD`, `========`, and `>>>>>> {git log code}` were added into the file.
      - Erased a few of the these added things.
      - Reorganized the files where necessary.
   - When done making the changes from previous point, I did `git add .`.
   - `git add .` marks the conflicting files as resolved.
   - `git rebase --continue`
   - And finally, `git push`
    
### Pull requests, an attempt  

I'm adding a line from **a-new-branch**, which is the 3rd branch created.  

Pull requests requires another branch beside main. Create a new pull request within the Github's website.
