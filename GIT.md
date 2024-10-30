git commit -am "message"

## The Clean All (discard all changes)

`git clean -fd`

## How do you move a commit to the staging area in git?

`git reset --soft HEAD~1`

## Pushing empty commits to remote

`git commit --allow-empty -m "Trigger Build"`

---

Add existing repo
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/repo.git
git push --set-upstream origin master
git pull origin master --allow-unrelated-histories
git merge origin/master

## History

git log --graph --color --decorate --oneline --all

gitk --all
