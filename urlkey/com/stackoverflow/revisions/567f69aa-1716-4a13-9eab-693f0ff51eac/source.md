To make a commit that looks like it was done in the past you have to set both `GIT_AUTHOR_DATE` and `GIT_COMMITTER_DATE`:

`GIT_AUTHOR_DATE=$(date -d'...') GIT_COMMITTER_DATE="$GIT_AUTHOR_DATE" git commit -m '...'`
where `date -d'...'` can be exact date like `2019-01-01 12:00:00` or relative like `5 months ago 24 days ago`.

To see both dates in git log use:

`git log --pretty=fuller`
