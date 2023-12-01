# GitHub Repository Guidelines
## Common topics
 - Documentation is done in the code repository, not in the Wiki
   - This has to enforce that documentation is done together with development
   - Documentation and development state should be one state
 - Working on new features, bugfixes, etc.
   - Create an Issue for each new feature, bugfix or other development tasks
   - Create a branch for that
   - Merge Issues into main branch using PullRequests. These PullRequests are basis for generated release notes on GitHub
 - One repository is one deployment unit
   - All projects in one repository share the same version
   - All projects in one repository are released at the same time

## Repository structure
- **.github** (for GitHub specific things like issue tempaltes, workflows, etc.)
- **assets** (optional. For assets like logos, etc.)
- **docs** (optional. For documentation)
- **subtrees** (optional. A place where to integrate other repositories via subtree machanism)
- **src** (for the source code itself)
- **scripts** (build- and publish scripts)
- **publish** (only locally. It is a common publish folder for all projects in ths repository)
- .gitignore
- CONTRIBUTING.md
- LICENSE.md
- README.md

## Branching strategy
- main
- Branches out of main
  - [IssueId]-*

## Creating releases
- Perform the following steps for creating a new release
  - Checkout main
  - Increase version if needed
  - Build, execute tests locally
  - Execute publish script(s) locally
  - Check generated executable and packages
  - Push to GitHub
  - Create release on GitHub, generate ReleaseNotes based on previously merged pull requests
  - Push to different platforms (like Nuget)
  - Increase version to the next one
  - Checkin again