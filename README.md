\# Exchange App (Sprint 0)



Goal

\- Stand up a clean, security-first foundation for a buy/sell crypto app without moving funds yet (auth, docs, CI scaffolding, read-only markets).  

\- Keep all secrets out of the repo; use env.example files and a vault/HSM in later environments.  



Scope (Sprint 0)

\- Repo scaffolding, basic docs, security policies, and read-only market page to validate the stack.  

\- No deposits, withdrawals, private keys, or custody code in this sprint.  



Security Baseline

\- Enforce 2FA for admin accounts, signed commits, protected branches, and required reviews before merges.  

\- Add CI checks (lint, tests, dependency audit, secret scan) and block on failure.  



Next Steps

\- Create SECURITY.md with responsible disclosure and rules for secrets and access.  

\- Add .gitignore, then set up docs/ and .github/workflows/ with minimal CI (to be added in the next steps).  



