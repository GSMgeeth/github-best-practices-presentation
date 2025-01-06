# GitHub Best Practices for HMIS
- HMIS already follows a lot of best practices when working with Git and GitHub. Infact, the only team that I've seen to follow this much of best practices and GitHub features consistently.
- HMIS needs improvements on areas such as;
    - Branching (creating, naming, syncing, merging)
    - Committing (message, frequency)
    - Deploying (managing environments, releasing frequency, respect environment hierarchy, Hotfix management)

## Branching
### Creating | Naming
- Let's follow the template ___\<ID\>-shortened-title___ (_ex: 3645-patient-info-update, 7738-report-print-bugfix_) when naming feature branches.
- Create feature branches directly from the default branch (in HMIS it's the _development_ branch).

### Syncing | Merging
- Only sync your working feature branches with the default branch _development_.
- When syncing (pulling & merging) with default branch, we can keep a clean and linear commit history by using `git pull --rebase`. This way, we can also reduce merge commits to a minimum. Use this with caution and resolve any conflicts carefully with collaboration with other contributors if necessary.
- When merging feature branch to the default branch, create a PR from feature branch to the default branch and after reviewing, merge when ready (fixed comments, no conflicts).
- When merging a PR, use __Squash Merge__ feature to keep default branch commits history meaningful and short.
- Use issue ID in the in the merge commit message if not already added by GitHub.
- After merging the feature branch, delete the branch for clarity and avoid using that branch by someone else in the future mistakenly.

## Committing
### Message
- Always write or generate a message that is meaningful to what you've done in the changes.
- No need to take a lot of time explaining everything. Just the important changes should be explained in summary.

### Frequency
- Make commits 
- While working, make commits frequently and push them to keep the upstream branch up-to-date. Since we will be using __Squash Merge__ when merging the PR, all these commits won't be included in the default branch.

## Deploying
### Managing Environments | Respecting Hierarchy
- When merging the default branch changes with relevant production branches via staging branch, always follow the hierarchy and don't commit directly to client production branches if it's not a hotfix.
- Since the HMIS default branch is _development_, the _main_ branch should act as the staging branch where all the tested and stable code lives.
- In a production release, the main branch which has the tested and stable codebase should be merged into the relevant client branch as a release.
- Normally, a release note should be maintained for each release but it's not necessary for every release or we can just ignore it all together for now.

### Release Frequency | Hotfixes
- The release frequency of the product should be controlled.
- If not actually necessary, frequent releases should be avoided and should make production releases only after QA tests are done in development and qa environments and through staging branch.
- Hotfixes are okay to be directly commited to production branches but always keep them synced with default branch where all developers get their updates from.
