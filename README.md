# Delta Fix Library

Community library of reusable [Delta (Δ)](https://delta-lang.dev) fix and patch transforms.

## What is this?

The fix library is a collection of `.delta` files covering the most common code transformation patterns — null checks, async modernisation, API migrations, security fixes, and more.

Apply any fix to your project in seconds:

```bash
# Preview what will change
delta run fixes/typescript/null-checks.delta --preview

# Apply it
delta run fixes/typescript/null-checks.delta
```

## Structure

```
fixes/
  typescript/
    null-checks.delta       — strict equality, optional chaining
    async-modernisation.delta — Promise chains → async/await
    import-cleanup.delta    — unused imports, barrel exports
  python/
    type-hints.delta        — add type annotations to functions
    f-string-migration.delta — % and .format() → f-strings
  go/
    error-handling.delta    — bare error returns → wrapped errors
  security/
    sql-injection.delta     — raw string SQL → parameterised queries
    secret-exposure.delta   — hardcoded secrets → env vars
  migrations/
    react-18.delta          — React 17 → 18 API changes
    next-14.delta           — Next.js 13 → 14 API changes
```

## Contributing

1. Fork this repo
2. Add your `.delta` file in the appropriate directory
3. Include a comment block at the top with: what it fixes, language, severity
4. Open a PR

## Fix Format

Each fix file follows this convention:

```delta
// fix: <short description>
// lang: <TypeScript | Python | Go | ...>
// severity: <bug | perf | style | security>
// author: <your handle>

fix myFix {
  pattern: { old pattern }
  replace: { new pattern }
  scope:   "**/*.ts"
  severity: bug
  note:    "why this matters"
}

apply fix myFix to project preview
```
