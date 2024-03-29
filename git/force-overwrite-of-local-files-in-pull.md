# Force Overwrite of Local Files in Pull

In git pull command,

1. Update all `origin/<branch>` refs to latest
    ```bash
    git fetch --all
    ```
2. Backup current branch
    ```bash
    git branch backup-master
    ```
3. Move to the latest commit on `origin/master` and checkout those files
    ```bash
    git reset --hard origin/master
    ```

[source](https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files)