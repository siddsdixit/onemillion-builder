# Day 16: Security Audit

**Time: 20 minutes | Phase: GUARD**

---

## Learn (5 min)

The GUARD agent runs a 9-phase security audit before you ship. It scans for:

1. **Hardcoded secrets** — API keys, passwords in source code or git history
2. **Vulnerable dependencies** — CVEs in your pip and npm packages
3. **SAST** — static analysis for injection, eval(), dangerous patterns
4. **API surface** — every endpoint classified by auth requirement and validation
5. **OWASP Top 10** — all 10 categories checked with evidence
6. **Data privacy** — PII inventory, data in transit and at rest
7. **Infrastructure** — MongoDB Atlas config, Railway config, Vercel config
8. **Security headers** — X-Content-Type-Options, X-Frame-Options, etc.
9. **Agent threat model** — if you built an AI feature, prompt injection and cost explosion

Critical and High findings block shipping. They must be fixed.

## Do (10 min)

1. Run the guard agent:
   ```
   Continue to guard
   ```

2. Watch the phases run. When the audit completes, read the report:
   ```bash
   cat .onemillion/security-audit.md
   ```

3. Check the verdict:
   ```bash
   grep "BLOCKED\|PASSED" .onemillion/security-audit.md | head -5
   ```

4. If there are Critical/High findings, the BUILD agent will fix them:
   ```
   Fix the security findings
   ```

## Reflect (5 min)

**Assignment:** What did the security audit find that surprised you? What's the most important security concept you learned today? (CORS? IDOR? Secrets in git history?)

---

**→ Next: [Day 17 — Ship to Production](../day-17/learn.md)**
