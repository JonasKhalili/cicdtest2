# cicdtest2

The overall flow of Gitflow is:

1. A develop branch is created from main
2. A release branch is created from develop
3. Feature branches are created from develop
4. When a feature is complete it is merged into the develop branch
5. When the release branch is done it is merged into develop and main
6. If an issue in main is detected a hotfix branch is created from main
7. Once the hotfix is complete it is merged to both develop and main

## Create develop branch

git branch develop
git push -u origin develop

## create feature branch 

git checkout develop
git checkout -b feature_branch

## Finishing feature branch

git checkout develop
git merge feature_branch

## release branches

git checkout develop
git checkout -b release/0.1.0

### merge with main

git checkout main
git merge release/0.1.0

## Create a hotfix branch and finish

git checkout main
git checkout -b hotfix_branch

git checkout main
git merge hotfix_branch
git checkout develop
git merge hotfix_branch
git branch -D hotfix_branch
