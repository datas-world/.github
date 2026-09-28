# Contributing

Contribution access is controlled per repository. Not all repositories in this
organisation accept external contributions — check the repository's `README.md`
for its stated contribution policy.

The following rules apply wherever contributions are accepted.

## Communication

- Use English for all issues, pull requests, comments, and commit messages.
- Search for existing issues and pull requests before opening new ones to avoid
  duplicates.
- Keep one concern per issue.
- Security vulnerabilities must **not** be reported as public issues —
  see [SECURITY.md](SECURITY.md) for private disclosure instructions.

## Issues

- Provide a clear title and enough context to reproduce or understand the
  problem.
- Link pull requests to the relevant issue; open an issue first if none exists.

## Pull Requests

- Keep changes small and focused; prefer reviewable patches.
- All automated checks (build, tests, linters) must pass before requesting
  review.
- At least one approval is required before merge.
- No secrets, credentials, API keys, or privacy-relevant data may appear in
  commits, commit messages, or pull request descriptions.
- All PRs are merged by **squash merge**; the PR title becomes the single commit
  on the default branch.

### Issue references

Every PR must reference at least one issue in its description using a
[GitHub closing keyword](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword)
(`Closes #NNN`, `Fixes #NNN`, `Resolves #NNN`) or a reference-only keyword
(`Refs #NNN`).

If no suitable issue exists, open one before submitting the PR.  AI assistants
must propose creating an issue and help the author open it.  PRs without any
issue reference are only permitted with explicit approval from the
reviewer/merger.  **PRs from forks always require a linked issue.**

### Draft / work-in-progress PRs

Open a draft pull request early to signal intent and invite feedback.

| Rule | Details |
|---|---|
| Draft PR | Title **must** start with `[WIP] ` (including the trailing space) |
| Ready-for-review PR | `[WIP] ` prefix is **optional** |
| Transitioning to ready | Removing `[WIP] ` from the title can trigger automatic reviewer assignment |

The `pr-lint.yml` workflow (see [source](https://github.com/datas-world/org-workflows/blob/main/.github/workflows/pr-lint.yml), full
spec in [conventional-commits.instructions.md](.github/instructions/conventional-commits.instructions.md#work-in-progress-prs))
enforces that draft PRs always carry the `[WIP] ` prefix, re-running on every
push and on `converted_to_draft` / `ready_for_review` events.  A sticky comment
is posted on the PR if the title is invalid, and removed once corrected.

Non-draft PRs may keep the `[WIP] ` prefix — this is intentional and is used as
a lightweight signal that the PR is still being worked on or to trigger
reviewer-assignment automation when the prefix is eventually removed.

## Commit Messages

All commit messages — including PR titles, which become the squash-merge commit
— must follow [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/).

**Quick reference:**

```
type(scope): subject

[optional body]

[optional footers]
```

- Both **type** and **scope** are required.
- Subject starts with a lowercase letter; no trailing period; ≤ 72 characters.
- Use `!` or a `BREAKING CHANGE:` footer for breaking changes.
- Every PR must include a `Closes #NNN` (or equivalent) footer referencing the
  linked issue.
- `Signed-off-by:` is required on all commits (configure with
  `git config --global format.signOff true`).

For the full specification — scope tables, footer ordering, imperative-mood
rules, body guidelines, full examples — see
[.github/instructions/conventional-commits.instructions.md](.github/instructions/conventional-commits.instructions.md).

## Code Style

Follow the conventions already established in the repository you are
contributing to. Repository-specific guidance takes precedence over this
document.

Organisation-wide commit conventions are specified in
[.github/instructions/conventional-commits.instructions.md](.github/instructions/conventional-commits.instructions.md).

Individual repositories carry their own `AGENTS.md`, `.github/copilot-instructions.md`,
`.github/instructions/`, `.github/agents/` and `.github/prompts/` files. These are
per-repository by design and are not inherited from this repository.
