---
on:
  schedule: weekly
engine:
  id: copilot
  model: gpt-5.4
permissions:
  contents: read
  issues: read
  pull-requests: read
safe-outputs:
  create-pull-request:
    title-prefix: "chore: "
    protected-files: fallback-to-issue
  create-issue:
    title-prefix: "chore: "
    labels: [refactor]
---

# Automated refactoring

Review the codebase, identify opportunities for improvement and implement them.

## Instructions

1. Start with a deep research into understanding our codebase.
2. Check existing issues to make sure you don't create duplicate issues. Or work on existing issues.
3. Check existing pull requests to identify work in progress.
4. Identify an area to improve that won't cause merge conflicts with existing pull requests.
5. Apply fixes, improvements, recommendations and create a pull request to propose merging this work. 
6. [IMPORTANT] After the initial work **CREATE ISSUES** for all future work that does not fit the scope of your current work.
7. Always finish with a safe output:
   - use `create_pull_request` when you changed files,
   - use `create_issue` when follow-up work is needed but you are not opening a PR,
   - use `noop` with a short explanation when you intentionally take no action.

### Suggested Areas to Review:

- [High priority] Check if there are open dependabot pull requests and only update dependencies in your own branch when the target release is at least 7 days old. Dependabot security updates can bypass the cooldown, so review those case-by-case before applying them. Check if these new versions introduce changes which we can use to improve our codebase with.
- Folder structure
- Unused files that clutter the repo
- Code quality and maintainability
- Test coverage and reliability
- Documentation completeness
- Performance optimizations
- Security best practices
- Code duplication
- Error handling
- Dependencies and updates
- Use of custom code instead of established libraries

### Guidelines:

- Prioritize high-impact, low-risk improvements
- Run existing tests and linters before completing
- Document any significant changes
- Consider backward compatibility for trading positions and logging for the Azure Dashboards.
- Don't try to change/remove tests that rely on live executions. 
- **Delegate tasks to suitable agents** in the `.github/agents` folder when available

**Note:** If the scope is too large for a single session, create additional issues with the `refactor` label for remaining work.
