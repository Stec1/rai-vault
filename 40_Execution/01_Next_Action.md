# Next Action

## Immediate Next Action
Prepare and execute ISSUE-04 (Authentication):
1. Create `40_Execution/ISSUE-04/` folder with Readiness, Prompt_For_Claude, Prompt_For_Code, Result files.
2. Run readiness check for ISSUE-04 against current infrastructure state.
3. Prepare Code prompt for ISSUE-04 execution.

## Execution Intent
- Implement authentication system (Better Auth, session cookies, email/password + Google OAuth).
- Unlock protected routes for all subsequent issues.
- Maintain strict issue-scoped execution per [[DL-004]].

## Dependencies
- ISSUE-03 completed (database baseline present) — confirmed in [[00_Current_State]].
- Infrastructure operational (PostgreSQL, Redis on Railway) — confirmed in [[31_Infrastructure_State]].
