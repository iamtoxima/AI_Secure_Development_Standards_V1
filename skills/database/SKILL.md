---
name: database
description: Database, ORM, schema, migration, RLS/policy, query, pagination, index, and data-access safety. Use when modifying persistent database behavior; do not use when the task does not touch a database.
---


# Database

- Do not use `SELECT *`; request explicit columns.
- Use parameterized queries or safe ORM/query-builder APIs.
- Never interpolate untrusted input into database queries.
- Build NoSQL filters from explicit allowed fields and scalar types.
- Paginate potentially large lists/feeds/history.
- Put practical upper bounds on page sizes.
- Prefer indexed access patterns for meaningful filtered/joined paths.
- Inspect existing schema/indexes before adding an index.
- Do not add an index to every filtered column automatically; justify it by access pattern and write/storage tradeoffs.
- Check for existing repository/query functions before creating duplicate access logic.
- Reuse already-fetched data when practical.
- Consider N+1 query behavior when relevant.
- Use least-privilege database credentials.
- For direct client database access, enforce robust row/object policies such as RLS where supported.
- Test owner, non-owner, unauthenticated, and privileged access when relevant.
- Privileged database functions should have explicit permissions and safe execution context.
- Treat migrations as production changes: review permissions, rollback/recovery, and compatibility.
