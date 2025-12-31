# Justifyr: Lightweight Formal Specification Generator

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Rust 1.75+](https://img.shields.io/badge/rust-1.75+-orange.svg)
![Go 1.21+](https://img.shields.io/badge/go-1.21+-00ADD8.svg)
![TypeScript 5](https://img.shields.io/badge/TypeScript-5-blue)

Justifyr is a compiler plugin system that generates formal specifications from specially formatted code comments. It transforms `//@invariant: x > 0` into complete TLA+/Alloy specifications, making formal methods accessible to everyday developers.

## 🎯 Why Justifyr?
Writing formal specifications is notoriously difficult and time-consuming. Justifyr solves this by:
- Extracting specifications directly from code comments using a simple annotation system
- Generating complete formal models in TLA+, Alloy, and other specification languages
- Identifying unproven assumptions and highlighting verification gaps
- Providing zero runtime overhead through compile-time analysis

### Why LLMs Can't Solve This
Large language models hallucinate invariants and lack the rigorous parsing required for formal verification. Justifyr uses deterministic parsing and formal logic mapping to ensure specifications are mathematically sound.

## 🏗️ Architecture Overview
Justifyr follows a layered, modular architecture:

### Layer 1: Language-Specific Plugins
Go/Rust/TypeScript plugins that parse annotated comments and extract specifications:
- **Go**: `go-justifyr` compiler plugin using Go AST
- **Rust**: `rust-justifyr` procedural macro crate
- **TypeScript**: TypeScript transformer plugin

### Layer 2: Core Engine (Rust)
Language-agnostic formal logic engine that:
- Converts parsed comments to a unified AST
- Applies formal logic transformations
- Translates to TLA+/Alloy/Coq specifications
- Verifies internal consistency

### Layer 3: Specification Management
Enterprise-grade spec management with:
- **Spec Registry**: Versioned specification database
- **Verification Orchestrator**: Runs TLC, Alloy Analyzer, Coq
- **Spec Composer**: Combine and refine specifications
- **Dependency Manager**: Handle specification dependencies

### Layer 4: Developer Experience
IDE integration and tooling:
- VS Code extension with hover docs and completion
- IntelliJ plugin for JetBrains IDEs
- Language Server Protocol (LSP) for real-time analysis

### Layer 5: Cloud Platform (Future)
SaaS offering with:
- Web dashboard for specification visualization
- Distributed verification worker pool
- Team collaboration features

### Layer 6: Data Infrastructure
Analytics and ML capabilities:
- Public specification registry
- Anonymous usage metrics collection
- ML models for invariant suggestion

## 🚀 Quick Start
### Prerequisites
- Rust 1.75+ (for core engine)
- Go 1.21+ (for Go plugin) or Node.js 18+ (for TypeScript)
- Docker (for verification sandboxing)


---
**Justifyr**: Making formal verification accessible, one comment at a time.