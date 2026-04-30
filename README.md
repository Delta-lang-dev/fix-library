# Δ Delta Fix Library

The official standard library of reusable `.delta` transformation files for the [Delta Language](https://github.com/Delta-lang-dev/Delta).

## What is this?

Instead of writing the same fix patterns over and over, the fix library gives you ready-made Delta programs for the most common code transformations. Install the Delta CLI and apply any fix with one command.

## Usage

```bash
# Install Delta CLI
npm install -g @delta-lang/cli

# Apply a fix from this library to your project
delta run common/sql-injection.delta --preview
delta run common/sql-injection.delta
```

## Available Fixes

### common/
| File | What it fixes | Languages |
|---|---|---|
| `sql-injection.delta` | Raw f-string SQL queries | Python |
| `null-checks.delta` | Missing null guards | TypeScript, JavaScript |
| `off-by-one.delta` | Inclusive loop bounds | TypeScript, JavaScript |
| `missing-await.delta` | Missing await on async calls | TypeScript, JavaScript |

### typescript/
| File | What it does |
|---|---|
| `react-v17-to-v18.delta` | Migrates React 17 to React 18 |
| `strict-mode.delta` | Adds strict TypeScript settings |

### python/
| File | What it does |
|---|---|
| `f-string-safety.delta` | Converts unsafe f-string SQL to parameterized queries |
| `type-hints.delta` | Adds missing type hints to function signatures |

## Contributing

Want to add a fix? Read [CONTRIBUTING.md](https://github.com/Delta-lang-dev/Delta/blob/main/CONTRIBUTING.md) and open a pull request.

## Links

- [Delta Compiler](https://github.com/Delta-lang-dev/Delta)
- [VS Code Extension](https://github.com/Delta-lang-dev/vscode-delta)
- [Website](https://delta-lang.dev)

## License

MIT
