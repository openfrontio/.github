# openfrontio/.github

Shared GitHub Actions workflows for OpenFront repositories.

| Workflow | Purpose |
|---|---|
| `.github/workflows/claude-code-review.yml` | Claude Code PR review, called from each repo's thin `claude-code-review.yml`. Owns the prompt, tool allowlist, primary/backup account fallback and the "did it post?" gate. Callers own the trigger and `paths` filter. |
| `.github/workflows/claude-auto-fix.yml` | Label an issue `auto-fix` and Claude (Fable) implements it, opens a PR, waits for the review above, then verifies and fixes its findings. Label it `auto-fix:<repo>` instead (e.g. `auto-fix:infra`) when the PR belongs in another repo of the org: the run then dispatches that repo's `claude-auto-fix.yml` (needs the `AUTO_FIX_DISPATCH_TOKEN` PAT). Callers own the `issues: [labeled]` and `workflow_dispatch` triggers. |

Callers reference `@main`, so a change here lands in every repo at once. Test a
change by pointing one caller at `@your-branch` in a PR first.
