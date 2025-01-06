# GitHub Best Practices for HMIS
- HMIS already follows a lot of best practices when working with Git and GitHub. Infact, the only team that I've seen to follow this much of best practices and GitHub features consistently.
- HMIS needs improvements on areas such as;
    - [ ] Branching (creating, naming, syncing, merging)
    - [ ] Committing (message, frequency, committing only necessary files, reducing merge commits)
    - [ ] Deploying (managing environments, releasing frequency, respect environment hierarchy, Hotfix management)

## Branching
### Creating | Naming
- Let's follow the template ___\<ID\>-shortened-title___ (_ex: 3645-patient-info-update, 7738-report-print-bugfix_) when naming feature branches.
- Create feature branches directly from the default branch (in HMIS it's the _development_ branch).

### Syncing | Merging
- Only sync your working feature branches with the default branch _development_.
- When syncing (pulling & merging) with default branch, we can keep a clean and linear commit history by using `git pull --rebase`.
- When merging feature branch to the default branch, create a PR from feature branch to the default branch and after reviewing, merge when ready (fixed comments, no conflicts).
- After merging the feature branch, delete the branch for clarity and avoid using that branch by someone else in the future mistakenly.

