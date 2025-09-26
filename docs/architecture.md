\# Architecture Overview (Sprint 0)



Purpose

\- Establish a security-first foundation for a buy/sell crypto application with documented boundaries before building services.  

\- Keep Sprint 0 non-custodial/no-funds: focus on structure, policies, and read-only market views.  



Core components (high level)

\- Frontend (Web): Next.js/React TypeScript SPA for auth, dashboard, markets (read-only in Sprint 0).  

\- API Gateway (BFF): Single ingress for the frontend (REST/GraphQL), rate-limited, with auth/session enforcement.  

\- Auth Service: Email + OTP/TOTP 2FA, session management, device binding, and brute-force protections.  

\- User Service: Profiles, preferences, and account states; audit trails for changes.  

\- Market Data Service: Public market pairs, tickers, and orderbook snapshots (read-only in Sprint 0).  

\- Ledger Service (planning): Internal accounting for balances and transfers (deferred until a later sprint).  

\- Wallet/Custody (planning): Custodial HSM/MPC or non-custodial flows (decision pending; not in Sprint 0).  

\- Compliance/KYC (planning): Provider integration, sanctions screening, risk rules (deferred).  

\- Observability: Centralized logs, metrics, traces, and immutable audit events from day one.  



Environments

\- Dev: local Docker for services and databases; seeded data for testing.  

\- Staging: production-like environment with separate keys, accounts, and CI/CD promotion gating.  

\- Prod: hardened environment with least-privilege access, short-lived credentials, and restricted break-glass paths.  



Security baseline (applies to all services)

\- No real secrets in the repo; use env.example only, with a vault/HSM for actual credentials in non-dev environments.  

\- Mandatory 2FA for admin users, protected branches, signed commits, required reviews, dependency and secret scans in CI.  

\- Coordinated vulnerability disclosure policy in SECURITY.md with private reporting and safe harbor language.  



Data and storage (initial plan)

\- PostgreSQL for relational data (users, sessions, configs); Redis for caching/rate limits; object storage for logs/artifacts.  

\- Separate schemas per service with least-privilege DB roles and read-only replicas planned for analytics.  



Decision log (to fill as decisions are made)

\- Custody model: custodial (HSM/MPC) vs non-custodial — owner: TBD; due: TBD.  

\- Supported chains and pairs — owner: TBD; due: TBD.  

\- KYC provider and geographic scope — owner: TBD; due: TBD.  

\- Cloud region and network topology — owner: TBD; due: TBD.  



