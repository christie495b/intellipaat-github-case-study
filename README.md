# intellipaat-github-case-study

## below are the steps followed for this case study

# Initial commits on main and develop branches
git checkout -b develop
git commit -m "Initial commit on develop"
git checkout main
git commit -m "Initial commit on main"
git branch -d develop

# Developer works on a new feature
git checkout -b feature/new-feature develop
# Work on feature, commit changes

# Feature is complete, merge into develop
git checkout develop
git merge --no-ff feature/new-feature
git branch -d feature/new-feature

# Release preparation
git checkout -b release/2023-08 develop
# Test and fix issues, commit changes

# Release is ready, merge into main and develop
git checkout main
git merge --no-ff release/2023-08
git tag -a v1.0.0 -m "Release v1.0.0"
git checkout develop
git merge --no-ff release/2023-08
git branch -d release/2023-08

# Hotfix
git checkout -b hotfix/fix-issue main
# Fix critical issue, commit changes
git checkout main
git merge --no-ff hotfix/fix-issue
git tag -a v1.0.1 -m "Hotfix v1.0.1"
git checkout develop
git merge --no-ff hotfix/fix-issue
git branch -d hotfix/fix-issue
