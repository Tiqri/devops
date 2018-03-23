# GIT Branching Strategy

## MASTER and DEVELOP branches

It's always wise to keep all branches simple based on the following concepts.

1. The central GIT repository holds two main branches with an infinite lifetime.
    * DEVELOP branch
    * MASTER branch
2. Let ORIGIN/MASTER to be the main branch where the source code of HEAD always reflects the production ready state.
3. Let ORIGIN/DEVELOP to be the main branch where the source code of the HEAD always reflects a state with the latest delivered development changes for the next release.  This is where typically any automatic nightly builds are built from (if there happens to be any).
4. When the source code in the DEVELOP branch reaches a stable point and is ready to be released, all of the changes should be merged back into MASTER somehow and then tagged with a release numbers. How this is done in detail will be discussed further on.
5. Therefore, each time when changes are merged back into MASTER, this is a new production release by definition.
6. Use feature branches for all new features, you could do the same for bugs fixes for any issues.
7. It's always good to keep bug(s) and feature(s) branches separately named, refer naming branches section for proper naming convention.
8. Merge feature branches into the main branch using pull requests.  Your main branch could be the MASTER or DEVELOP.
9. Always maintain a high-quality MASTER and DEVELOP branch.

A strategy that extends these concepts and avoids contradictions will result in a version control workflow for your team that is consistent and easy to follow.

## Features, Bug, Hotfixes and Releases.

Besides the main branches MASTER and DEVELOP, our development model should use a variety of supporting branches to help development between team members, ease tracking of features, prepare for production releases and to assist in quickly fixing live production problems.

Unlike the main branches (DEVELOP & MASTER), these branches always have a limited life time, since they will be removed eventually after the job is done.

The different types of branches which we may use.

1. Feature branches
2. Release branches
3. Bug fix branches
4. Hotfix branches

_Bug fixes are more long-term fixes where are hotfixes are more short-term fixes._

Each of these branches have a specific purpose and are bound to strict rules as to which branches may be their originating branch and which branches must be their merge targets. By no means are these branches special from a technical perspective. The branch types are categorized by how we use them. They are of course plain old GIT branches.

## Feature and Bug Branching

1. May branch off from - DEVELOP
2. Must merge back into -  DEVELOP

Feature and bug branches are used to develop new features for the upcoming or a distant future release. When starting development of a feature or fix of a bug, the target release in which this feature will be incorporated may well be unknown at that point. The essence of a feature or bug branch is that it exists if the feature or bug is in development but will eventually be merged back into DEVELOP (to add the new feature to the upcoming release) or discarded (in case of a disappointing experiment).

## Hotfix Branching

1. May branch off from: MASTER
2. Must merge back into: DEVELOP and MASTER

Hotfix branches are meant to prepare for a new production release. They arise from the necessity to act immediately upon an undesired state of a live production version. When a critical bug in a production version must be resolved immediately, a hotfix branch may be branched off from the corresponding tag on the MASTER branch that marks the production version

## Release Branching
TBD

## Branch Tagging
TBD

## Branch Naming Convention

Name all branches properly by using a consistent naming convention for your feature branches to identify the work done in the branch. You can also include other information in the branch name, such as who created the branch, but its always options

If you are working on a feature, make it a practice to name the branch with the following convention.

**feature/feature-Id-use-a-small-title-description-of-the-feature-here.**

If you are working on a bug, make it a practice to name the branch with the following convention.

**bug fix/bug-id-small-title-description-of-the-bug**

If you are working on a hotfix., make it a practice to name the branch with the following convention.

**hotfix/hot-fix-id-small-title-description-of-the-hot-fix**

The name of the branch could be the JIRA bug id or feature id followed by the text in the title of the bug or the feature.

# Best practises for branch merging
TBD

# Pull Requests

The review that takes place in a pull request is critical for improving code quality. Only merge branches through pull requests that pass your review process. Avoid merging branches to the MASTER or DEVELOP branch without a pull request.

Always review and merge code with pull requests.  However before sending a pull request, the developer should test his code locally thoroughly covering all scenarios

**A sizable team should have two reviewers for a single pull request**

Reviews in pull requests take time to complete, so your team should agree on what's expected from pull request creators and reviewers. Distribute reviewer responsibilities to share ideas across your team and spread out knowledge of your codebase. Take care assigning the same reviewer(s) to many pull requests. Pull requests work better when reviewer responsibilities are shared across the team.

Provide enough detail in the description to quickly bring reviewers up to speed with your changes.

Its always ideal for the reviewer to check out the code and run the changes locally first and do some basic testing before approving the pull request.

## Typical Git Workflow
TBD

#### What happens when you want to revert a feature branch which was merged to DEVELOP
TBD

## Continuous Integration
TBD

## Deployment Environments
TBD

