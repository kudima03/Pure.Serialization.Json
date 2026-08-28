# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

All `dotnet` commands must be run from the `./src` directory.

```bash
dotnet restore
dotnet build --no-restore -warnaserror
dotnet format --verify-no-changes             # check code style (CI enforces this)
dotnet format && csharpier format .           # auto-fix code style
dotnet test --no-build                        # run xUnit tests (requires prior build)
dotnet pack --configuration Release -p:PackageVersion=<version> --output .
```

The test project targets `net10.0` only. Code coverage is collected by `coverlet`; CI enforces a minimum of 98% line and branch coverage.

## Architecture

`Pure.Serialization.Json` provides shared JSON serialization utilities and helpers for the Pure ecosystem, built on `System.Text.Json`.

**Multi-targeting:** net7.0, net8.0, net9.0, net10.0. `IsAotCompatible = true` — no reflection or dynamic code.

**Publishing:** triggered by pushing a semver tag (`*.*.*`). The tag value becomes `PackageVersion`. Packages are pushed to both GitHub Packages and NuGet.org (requires `NUGET_API_KEY` secret).

## Code Style

Enforced via `.editorconfig`, `dotnet format --verify-no-changes`, and `csharpier check .` in CI:

- No `var` — always use explicit types (`csharp_style_var_*` = false)
- No expression-bodied methods or constructors; expression-bodied properties are required
- File-scoped namespaces (`csharp_style_namespace_declarations = file_scoped`)
- Private fields: `_camelCase` prefix
- Braces always required (`csharp_prefer_braces = true`)
- `System.*` usings sorted first; all usings outside namespace
- Max line length: 90 characters

## Commit Messages

Do not mention Claude or AI assistance in commit messages.
