# AGENTS.md

## Working rules

- Test command: `dotnet test` from the repository root. Run the whole solution. `dotnet format --verify-no-changes` must also pass; CI runs both.
- Do not run the AppHost. It needs a container runtime this worktree does not have. `dotnet build` and `dotnet test` are enough to verify a change here.
- Layout: `src/Store.Api/<Feature>/` and `tests/Store.Api.Tests/<Feature>/` mirroring them. One feature per folder.
- Always work on a feature branch, never on `main`.
- Before exiting a heartbeat: commit, `git push -u origin HEAD`, `gh pr create --fill --base main`.
- Paste the PR URL in your hand-over comment and hand over (status `done`). Paperclip sends it to review.
- Never `--no-verify`. Never force-push a shared branch. Never `gh pr merge --admin`.