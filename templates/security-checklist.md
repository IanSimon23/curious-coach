# Security Pre-Deployment Checklist

**Run before every deployment. No exceptions.**

## API Keys & Secrets

- [ ] All API keys in `.env` file (never in code)
- [ ] `.env` added to `.gitignore`
- [ ] `.env.example` created with placeholder values
- [ ] No secrets committed to git history
- [ ] Environment variables validated on startup

## Input Validation

- [ ] All user input validated before processing
- [ ] Input sanitized to prevent injection attacks
- [ ] File uploads restricted by type and size
- [ ] URL inputs validated and sanitized
- [ ] Form data validated server-side (not just client-side)

## Data Isolation

- [ ] User data properly scoped (users can't see each other's data)
- [ ] RAG data isolated between users if applicable
- [ ] Database queries use parameterized statements
- [ ] Authorization checks on all data access
- [ ] Test performed: Can User A access User B's data?

## Error Handling

- [ ] Error messages don't leak system internals
- [ ] Stack traces hidden in production
- [ ] Sensitive data not logged
- [ ] Error logging captures enough for debugging
- [ ] User-facing errors are helpful but safe

## Dependencies

- [ ] Dependencies scanned for known vulnerabilities
- [ ] Unused dependencies removed
- [ ] Dependencies pinned to specific versions
- [ ] Regular dependency updates planned

## Rate Limiting

- [ ] API rate limiting implemented if applicable
- [ ] Anthropic API quota considered
- [ ] Abuse prevention for public endpoints
- [ ] Cost controls in place for API usage

## Authentication & Authorization

- [ ] Authentication required where appropriate
- [ ] Authorization checks on protected resources
- [ ] Session management secure
- [ ] Password requirements if applicable
- [ ] HTTPS enforced in production

## Deployment

- [ ] Production environment variables configured
- [ ] Debug mode disabled in production
- [ ] Logging configured for production
- [ ] Backup strategy in place if applicable
- [ ] Rollback plan documented

## Anthropic API Specific

- [ ] API key rotation plan exists
- [ ] Usage monitoring in place
- [ ] Cost alerts configured
- [ ] Prompt injection mitigation considered
- [ ] User data not sent to API unless necessary

## Final Checks

- [ ] Security review completed
- [ ] All items above verified
- [ ] Deployment approved
- [ ] Monitoring active

---

## Notes

Record any security decisions or exceptions:

**[Date]:** [Security decision and rationale]

---

*From [curious-coach](https://github.com/IanSimon23/curious-coach) - Security by Default standard*
