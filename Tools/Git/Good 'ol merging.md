# Fast Forwarding :LiFastForward:

- You were working on `iss53`, but you have to do a `hotfix`, so you create a branch from `master` named `hotfix`
![[Screenshot 2024-08-15 at 4.29.31 PM.png]]
- after finishing your work, you merge the `hotfix` into `master` for production with
```console
$ git checkout master
$ git merge hotfix
```
- and the response would be
```console
Updating f42c576..3a0874c
Fast-forward
 index.html | 2 ++
 1 file changed, 2 insertions(+)
```
- Git just move the `master` pointer to the `hotfix`'s pointer, since its directly about the `master`'s pointer since there is no divergent work
> Because the commit `C4` pointed to by the branch `hotfix` you merged in was directly ahead of the commit `C2` you’re on, Git simply moves the pointer forward. To phrase that another **way, when you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together** — this is called a “fast-forward.”
![[Pasted image 20240815164002.png]]
# Things heating up! Merge `iss53` into `master`
![[Screenshot 2024-08-15 at 4.48.30 PM.png]]
- in this case, we have divergent workflows
- Git does a 3 way merge with *two branch tips snapshots* and a *common ancestor snapshot* and creates a commit thats called `merge commit`
- `merge commit` has two parents, a special one
![[Screenshot 2024-08-15 at 4.57.49 PM.png]]
***Your'e lucky, you have no conflicts between `master` and `iss53`***

# Lets say, *CONFLICTS!*