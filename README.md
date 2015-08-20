# GitWiki

https://www.atlassian.com/git/tutorials/merging-vs-rebasing/the-golden-rule-of-rebasing

MMerge from develop to master:

1. IF master has commits that develop does not (this should happen rarely, e.g. when we create a hot fix) then the first step is to:

git checkout develop
git merge master

Resolve conflicts

Stage and commit

git push origin develop

2. Next create a release branch

git checkout master
git checkout -b feature-branch
git merge develop

Remove "SNAPSHOT" from al version numbers

Stage and commit

git push origin feature-branch

3. Merge the release branch into master

git checkout master
git merge feature-branch
git push origin master

4. Finally bump develop to a new SNAPSHOT version.


***Rebase non-shared feature branch
git reset --soft HEAD~1 or git reset soft <hashCode>
stage and commit
git push origin +<branchName>
