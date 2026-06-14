# Contributing to the Delta Fix Library

Thanks for contributing! Here is everything you need to know.

## What makes a good fix?

- **Real problem**: Fixes should address actual pain points developers face daily
- **Safe default**: All fixes should default to `preview` mode so contributors see diffs before applying
- **One concern**: Each fix file should address one specific issue (but can include multiple related `fix` blocks)
- **Clear note**: Every `fix` block should have a `note` explaining *why* the change matters

## File naming

```
fixes/<language>/<short-description>.delta
fixes/security/<short-description>.delta
fixes/migrations/<from>-to-<to>.delta
```

## Fix file format

Every fix file must start with a comment header:

```delta
// fix: <short description>
// lang: <TypeScript | Python | Go | ...>
// severity: <bug | perf | style | security>
// author: <your GitHub handle>
```

## Severity guide

| Severity | When to use |
|---|---|
| `bug` | Code that is incorrect or will break at runtime |
| `security` | Code that introduces a vulnerability |
| `perf` | Code that is unnecessarily slow |
| `style` | Code that works but does not follow modern idioms |

## Testing your fix

Before submitting, test your fix against a real codebase:

```bash
# Install the Delta CLI
npm install -g @delta-lang/cli

# Preview what your fix would do
delta run fixes/typescript/my-fix.delta --preview

# Only apply if the diff looks right
delta run fixes/typescript/my-fix.delta
```

## Pull request checklist

- [ ] Comment header present (fix, lang, severity, author)
- [ ] All `apply` statements use `preview` by default
- [ ] Fix tested against at least one real-world file
- [ ] Note field explains *why* the change matters
- [ ] Added to `index.delta` with a comment

## Questions?

Open an issue or discussion on [GitHub](https://github.com/Delta-Lang-Dev/fix-library/issues).
