```shell
git branch --move old_name new_name
git push origin --set-upstream new_name
git push origin --delete old_name
```
Now you have a few more tasks in front of you to complete the transition:

- Any projects that depend on this one will need to update their code and/or configuration.
    
- Update any test-runner configuration files.
    
- Adjust build and release scripts.
    
- Redirect settings on your repo host for things like the repo’s default branch, merge rules, and other things that match branch names.
    
- Update references to the old branch in documentation.
    
- Close or merge any pull requests that target the old branch