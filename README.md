# openfrontio/.github

Shared GitHub Actions workflows for OpenFront repositories.

| Workflow | Purpose |
|---|---|
| `.github/workflows/claude-code-review.yml` | Claude Code PR review, called from each repo's thin `claude-code-review.yml`. Owns the prompt, tool allowlist, primary/backup account fallback and the "did it post?" gate. Callers own the trigger and `paths` filter. |

Callers reference `@main`, so a change here lands in every repo at once. Test a
change by pointing one caller at `@your-branch` in a PR first.
