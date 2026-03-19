# Welcome to SAMES-Americas on GitHub

This is the official GitHub organization for **SAMES-Americas**. This space hosts repositories for software development projects, Power Platform solutions, shared libraries, and infrastructure configuration managed by our development teams.

---

## 📁 What You'll Find Here

Our repositories are organized using a consistent naming convention to make navigation easy:

| Prefix | Type | Example |
|--------|------|---------|
| `pp-` | Power Platform solutions | `pp-employee-onboarding` |
| `app-` | Traditional applications | `app-customer-portal` |
| `lib-` | Shared libraries / reusable components | `lib-shared-utilities` |
| `infra-` | Infrastructure and configuration | `infra-azure-pipelines` |

Every repository includes a `README.md` describing its purpose and a `.gitignore` appropriate to the project type.

---

## 🚀 Getting Started

New to the organization? Here is what you need before contributing:

1. A GitHub account added to this organization by an administrator.
2. **GitHub Desktop** installed on your workstation (submit an IT ticket if needed).
3. Access granted to the appropriate team(s) and repository(ies).
4. A basic familiarity with version control concepts — if you are new to Git, start at [docs.github.com](https://docs.github.com).
5. For **Power Platform contributors**: access to the Dev, PreProd, and Prod environments and permission to export solutions.

---

## 🌿 Branching Strategy

We follow **GitHub Flow** for traditional projects and a **three-branch environment model** for Power Platform work.

**For all projects**, development happens in short-lived branches named with the following prefixes:

- `feature/` — new functionality
- `bugfix/` — non-critical bug fixes
- `hotfix/` — urgent production fixes
- `chore/` — maintenance and documentation tasks

**For Power Platform projects**, three long-lived environment branches are maintained:

- `dev` — active development; all feature work merges here first
- `preprod` — pre-production; changes are promoted here after dev testing
- `main` — production; only fully tested and approved changes land here

Delete your feature and bugfix branches after they have been successfully merged to keep repositories clean.

---

## ✅ Pull Request Standards

All changes to protected branches must go through a pull request. Before you submit:

- Ensure your branch is up to date with the target branch.
- Write a **clear title and description** explaining what changed, why, and what testing was done.
- Assign at least one reviewer — junior developers must assign a senior developer.
- Keep pull requests small and focused; break large features into incremental PRs where possible.

At least **one approving review** is required before any pull request can be merged. All review comments must be resolved, and approvals are invalidated if new commits are pushed after approval.

> 📄 For the full pull request and code review guidelines, see the [GitHub Best Practices Guide](https://github.com/SAMES-Americas/SamesGitHubDocumentation) in the **SamesGitHubDocumentation** repository.

---

## 💬 Commit Message Standards

Write commit messages in the **imperative present tense** (e.g., "Add approval step" not "Added approval step") and keep the summary under 72 characters. Begin each message with a type prefix:

| Prefix | Use |
|--------|-----|
| `feat:` | New feature or capability |
| `fix:` | Bug fix |
| `docs:` | Documentation changes only |
| `chore:` | Maintenance tasks, no functional change |
| `refactor:` | Code restructuring, no behavior change |
| `pp:` | Power Platform solution export or update |

Avoid vague messages like `"updates"`, `"WIP"`, or `"fix stuff"`. Each commit should clearly communicate what changed and why.

---

## 🔒 Branch Protection

The following protections are enforced on `main` in all repositories, and on `preprod` and `dev` in all Power Platform repositories:

- Direct pushes to protected branches are **not permitted** — all changes must arrive via a reviewed and approved pull request.
- At least **1 approving review** is required before merging.
- Approvals are **dismissed when new commits are pushed** after approval.
- The source branch must be **up to date** with the target before merging.
- These rules apply to **all contributors**, including organization administrators.

---

## 👥 Roles and Permissions

| Role | Responsibilities |
|------|-----------------|
| **Owner / Admin** | Organization management, team creation, security settings. Limited to designated IT administrators. |
| **Senior Developer** | Reviews and approves pull requests, enforces code standards, makes final merge decisions. |
| **Junior Developer** | Works in assigned feature/bugfix branches, writes clear commits, submits PRs, acts on review feedback. |

Access is granted at the **team level**, not to individual users directly. Repository access is reviewed on a **quarterly basis**. Follow the principle of least privilege — do not assign Admin access when Write access is sufficient.

---

## 🔐 Security Practices

- **Never commit secrets.** API keys, passwords, and connection strings must not appear in any repository. Once committed, a secret is permanently exposed in the history.
- All repositories must have a properly configured **`.gitignore`** that excludes environment config files, local IDE settings, build output, and for Power Platform repos, exported `.zip` files.
- **GitHub Secret Scanning** is enabled at the organization level. Administrators are alerted if a known secret pattern is detected in a commit.
- If a secret is accidentally committed and pushed, **immediately rotate or revoke the credential** — removing it in a follow-up commit is not sufficient.

---

## ⚙️ Power Platform Version Control

We currently use a **manual export and commit** process for Power Platform solutions:

- Always export in **unmanaged format** from the source environment.
- Extract the solution `.zip` and commit the **folder structure**, never the raw zip file.
- Commit to the branch matching the environment the solution was exported from.
- Use descriptive commit messages prefixed with `pp:`.

The long-term goal is to automate this process with **Azure DevOps pipelines**. Following the naming and branching conventions established today will ensure a smooth transition to automation without restructuring repositories later.

---

## 📚 Documentation

Full guidance on all of the above is documented in the **[GitHub Best Practices Guide](https://github.com/Sames-Americas/SamesGithubDocumention)** located in the **SamesGithubDocumentation** repository. All contributors are expected to review that document before working in this organization.

---

*Maintained by the SAMES-Americas development team.*
