# Pure.Serialization.Json

JSON serialization utilities for the **Pure** ecosystem.

[![.NET build & test](https://github.com/kudima03/Pure.Serialization.Json/actions/workflows/build-and-test.yml/badge.svg?branch=main)](https://github.com/kudima03/Pure.Serialization.Json/actions/workflows/build-and-test.yml)
[![Build and Deploy](https://github.com/kudima03/Pure.Serialization.Json/actions/workflows/publish-nuget.yml/badge.svg?branch=main)](https://github.com/kudima03/Pure.Serialization.Json/actions/workflows/publish-nuget.yml)
[![NuGet](https://img.shields.io/nuget/v/Pure.Serialization.Json)](https://www.nuget.org/packages/Pure.Serialization.Json)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Overview

`Pure.Serialization.Json` provides shared JSON serialization utilities and helpers for the Pure ecosystem. It builds on `System.Text.Json` and is fully AOT-compatible.

## Design Principles

- **AOT-compatible** — fully compatible with Native AOT compilation; no runtime reflection.
- **Composable** — utilities integrate cleanly with other Pure serialization packages.
