# Branch Protection & Merging Rules

This repository is protected by strict branch rules to ensure high code quality and integrity of the main branch.

## 🔒 Branch Protection

- **Protected branch:** `main`
- **Merging allowed:** Only via approved Pull Requests (PRs)
- **Allowed merge method:** Squash only — this keeps the commit history clean by combining all PR commits into one.
- **Force pushes:** Blocked
- **Branch deletions:** Restricted
- **Updates to main:** Restricted (must go through PR process)

## ✅ Pull Request Rules

- **Required approvals:** 1 approval needed before merging
- **Who can approve:** Only repository admins (myself / my secondary account)
- **Auto-dismiss stale approvals:** Enabled (new commits require fresh approval)
- **Require most recent reviewable push approval:** Enabled
- **Require conversation resolution:** Enabled (all code review conversations must be resolved before merge)

## 🚫 Direct edits

- Collaborators (including friends) cannot:
  - Push directly to `main`
  - Force push or delete `main`
  - Merge without PR approval

## 🔑 Bypass

- Only **repository admins** can bypass protection rules
- No other roles or teams are exempt

## ℹ Why squash only?

Squash merging is enforced to:
- Keep a clean and readable main branch history
- Reduce noise from multiple intermediate commits
- Make it easier to rollback changes if necessary

---

**Note:** If you are a collaborator, always create a new branch and open a PR for any change.  
The admin will review and approve or request changes.
