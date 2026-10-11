# Engineering Checklists

## Frontend
- [ ] Layouts designed for 390 / 768 / 1280 / 1440+ (not just shrunk)
- [ ] Routing with per-role shells and guarded routes (guards are UX only — server also enforces)
- [ ] Forms: schema validation, inline errors, disabled/pending submit, success feedback
- [ ] Tables: sort, filter, search, pagination or virtualization, empty state, mobile card view
- [ ] Charts labelled in plain language; colorblind-safe palette; tooltips; no-data state
- [ ] Every async view has skeleton, empty, error (with retry), and permission-denied states
- [ ] Toasts/notifications for mutations; optimistic UI where safe
- [ ] Semantic HTML, landmarks, labels, focus management in modals, visible focus rings, AA contrast
- [ ] Images: dimensions set, lazy below fold, alt text; fonts: `font-display: swap`

## Backend
- [ ] Input validation at every boundary
- [ ] Authorization check in every handler (role + ownership + organization)
- [ ] Business logic in services; handlers stay thin
- [ ] Workflow transitions validated against an explicit state machine
- [ ] Idempotency for payments/webhooks; retries with backoff for jobs
- [ ] Consistent error shape; no stack traces or secrets in responses
- [ ] Rate limiting on auth, AI, upload, and search endpoints
- [ ] Audit log entries for sensitive actions (who, what, when, before/after)

## Database
- [ ] UUID/ULID PKs; FKs with correct `ON DELETE`; unique and check constraints
- [ ] Indexes on FKs and columns used for filters/sorts/search
- [ ] Status enums for lifecycle; audit columns; `organization_id` on tenant data
- [ ] RLS policies (Postgres/Supabase) or equivalent repository-layer scoping
- [ ] Migrations are forward-only and reproducible; seed script is idempotent

## Security
- [ ] `.env.example` committed, real secrets never committed or logged
- [ ] Secure session cookies; CSRF protection where relevant
- [ ] CSP, HSTS, X-Content-Type-Options, frame-ancestors
- [ ] File uploads: type/size limits, private storage, signed URLs, malware scanning noted for prod
- [ ] Cross-tenant access tests exist and pass
- [ ] Dependencies audited

## Observability
- [ ] Structured logging with request IDs
- [ ] Error tracking hook
- [ ] `/health` (and `/ready` if relevant)
- [ ] Analytics events for the core loop (signup, activation, key action)

## Testing
- [ ] Unit: business logic, scoring, permissions
- [ ] Integration/API: core endpoints incl. unauthorized cases
- [ ] Component: complex interactive components
- [ ] E2E (Playwright): one critical path per primary role, on desktop and mobile viewport
