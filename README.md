# openfrontio/.github

Shared GitHub Actions workflows for OpenFront repositories.

| Workflow | Purpose |
|---|---|
| `.github/workflows/claude-code-review.yml` | Claude Code PR review, called from each repo's thin `claude-code-review.yml`. Owns the prompt, tool allowlist, primary/backup account fallback and the "did it post?" gate. Callers own the trigger and `paths` filter. |
| `.github/workflows/cherry-pick-milestone.yml` | Backports a merged PR onto the release branch named by its `vNN` milestone, called from each repo's thin `cherry-pick-milestone.yml`. Clean picks push to the branch; conflicts are resolved by Claude and opened as a PR against it. Callers own the trigger. |

Callers reference `@main`, so a change here lands in every repo at once. Test a
change by pointing one caller at `@your-branch` in a PR first.
