# SushiDB

SushiDB is a lightweight, single-node **ACID-compliant database engine** written in modern C++.  
It is designed as an educational and research-focused system that demonstrates the core mechanisms of transactional storage engines, including:

- **Write-Ahead Logging (WAL)** for durability
- **Buffer pool management** with clock replacement
- **B+-tree indexes** for point lookups and range scans
- **Multi-Version Concurrency Control (MVCC)** for snapshot isolation
- **Crash-safe recovery** (ARIES-style redo, no-undo)

SushiDB is not intended as a production-ready database. Instead, it is a learning project for systems enthusiasts who want to understand how databases are built from the ground up.

---

## Features

- Transaction lifecycle: `BEGIN`, `COMMIT`, `ABORT`
- Physical redo logging with page-level LSNs
- Slotted pages and heap files for variable-length records
- MVCC tuple versioning for concurrent reads and writes
- Crash recovery with fuzzy checkpoints
- Simple SQL subset (`CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`, `DELETE`)
- TCP-based client-server protocol with a command-line interface

---

## Roadmap

- [x] Page and buffer pool manager  
- [x] Write-ahead log and log manager  
- [ ] Recovery subsystem (redo, checkpoints)  
- [ ] Heap file storage with slotted pages  
- [ ] B+-tree indexes (unique and secondary)  
- [ ] Transaction manager and MVCC versioning  
- [ ] Basic SQL parser and execution engine  
- [ ] Networking layer and client CLI  
- [ ] Concurrency stress tests and benchmarking  

---

## Getting Started

### Prerequisites
- C++20 compiler (GCC 11+ or Clang 13+ recommended)
- CMake (>= 3.16)
- Linux or macOS (Windows is untested)

### Build
```bash
git clone https://github.com/<your-username>/sushidb.git
cd sushidb
mkdir build && cd build
cmake ..
make -j$(nproc)
