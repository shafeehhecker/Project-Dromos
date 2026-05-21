# Project Dromos 🛤️

> **High-Performance CPM Scheduling Engine** — A deterministic, strictly typed implementation of the Critical Path Method, architected entirely in Rust.

Conceived to supersede a legacy Python prototype, Project Dromos leverages Rust's rigorous ownership semantics and zero-cost abstractions to deliver unprecedented computational velocity and absolute memory safety.

---

## Architectural Overview

The application has been fundamentally re-engineered from a dynamic scripting paradigm into a robust, natively compiled systems architecture. By abandoning the Python Global Interpreter Lock (GIL) and garbage collection overhead, the engine executes graph traversals exponentially faster while remaining categorically immune to runtime type ambiguities and data races.

---

## Core Stack

| Layer | Technology |
|---|---|
| **Computational Engine** | Pure Rust (`std::collections::VecDeque`, `HashMap`, optimized adjacency lists) executing Kahn's Algorithm for topological sorting |
| **Application Framework** | Tauri — Native Rust backend orchestrating a lightweight, high-performance WebView frontend |
| **Data Persistence** | Asynchronous SQLite via `sqlx` with compile-time query verification and connection pooling |
| **Serialization** | `serde` for seamless, type-safe data serialization between the Rust backend and presentation layer |

---

## Primary Capabilities

- **Deterministic CPM Evaluation** — Executes strictly typed forward passes (ES/EF computation) and backward passes (LS/LF computation) with optimal CPU cache locality.
- **Memory-Safe State Management** — Employs Rust's advanced type-state patterns to enforce valid scheduling states exclusively at compile time.
- **Concurrent Execution Pipeline** — Offloads massive network calculations or parallel portfolio analyses via the `Tokio` async runtime and `Rayon` data parallelism.
- **Persistent Data Immutability** — SQLite operations execute asynchronously, preventing GUI thread occlusion during intensive I/O operations.
- **Cross-Platform Compilation** — Compiles to a lean, standalone binary for Windows, macOS, and Linux without secondary runtime environments or dependency installations.

---

## Build & Initialization

### Prerequisites

Ensure your environment is provisioned with the latest stable Rust toolchain and the requisite system dependencies for Tauri compilation.

```bash
# Verify toolchain installation
rustc --version
cargo --version
```

### Compilation

Clone the repository and execute the release compilation to invoke LLVM optimization passes:

```bash
# Development — with hot-reloading
cargo tauri dev

# Production — optimized binary
cargo tauri build
```

---

## Algorithmic Complexity Profile

Unlike the legacy Python implementation — which suffered from dictionary lookup overhead within tight loops — Project Dromos constructs optimal adjacency lists using numerical indices.

| Operation | Complexity | Notes |
|---|---|---|
| Topological Sort | $O(V + E)$ | $V$ = project activities, $E$ = dependencies |
| Forward Pass (ES/EF) | $O(V + E)$ | Contiguous memory access patterns |
| Backward Pass (LS/LF) | $O(V + E)$ | Contiguous memory access patterns |
| Memory Footprint | Minimal | `struct` padding optimization, no redundant object allocations |

---

## Roadmap — Phase II Enhancements

- [ ] **WebAssembly (Wasm) Compilation** — Compile the core scheduler to Wasm for native browser execution.
- [ ] **Resource Leveling** — Advanced heuristics for resource-constrained scheduling operations.
- [ ] **P6 XML Interoperability** — High-throughput parsing of Primavera P6 XML schemas via `quick-xml`.

---

## License

See [LICENSE](./LICENSE) for details.
