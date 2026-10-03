```text
           .:ldkOOOOOkdl:.               soham@arch-runtime
       .cx0XNNNNNNNNNNNNNNX0xc.          ------------------
     .oKWNNNNNNNNNNNNNNNNNNNNWKo.        OS          ──►  Linux (x86_64) / Darwin (arm64)
   .dKNNNNNNNX0OkkkkkO0XNNNNNNNKd.       Kernel      ──►  Custom Low-Latency / Userspace Ring Buffers
  .kNNNNNN0l'             'l0NNNNNNk.    Uptime      ──►  Autonomous Engine Active (24/7)
 .OWNNNNk.                   .kNNNNWO.   Shell       ──►  Zsh 5.9 / Bash POSIX
 :NNNNNl                       lNNNNN:   IDE/Tooling ──►  Neovim, LLVM/Clang, GDB, Valgrind
.OWNNNk                         kNNNWO.
:NNNNN:                         :NNNNN:  Languages.Systems  ──►  C++20, C17, Java 21, Rust
:NNNNN:                         :NNNNN:  Languages.Script   ──►  Python 3.12, POSIX Shell, Zsh
.OWNNNk                         kNNNWO.  Architecture.Focus ──►  LSM Engines, Zero-Copy, Consensus
 :NNNNNl                       lNNNNN:
 .OWNNNNk.                   .kNNNNWO.   Engine.Status      ──►  Hardened (ASAN/UBSAN Verified)
  .kNNNNNN0l'             'l0NNNNNNk.    Verification       ──►  CI/CD Pass Rate 100%
   .dKNNNNNNNX0OkkkkkO0XNNNNNNNKd.       Deployment         ──►  Cloud Autonomous Matrix (Cron 2h)
     .oKWNNNNNNNNNNNNNNNNNNNNWKo.
       .cx0XNNNNNNNNNNNNNNX0xc.          GitHub Stats
           .:ldkOOOOOkdl:.               ------------------
                                         Public Repos: 235+ │ Commits: 2,100+ │ Rank: A+


```
<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-06b6d4?style=flat-square&logo=opensourceinitiative&logoColor=white)](https://opensource.org/licenses/MIT)
[![Infrastructure: Zero--Copy](https://img.shields.io/badge/Architecture-Lock--Free_LSM-0f172a?style=flat-square&logo=cplusplus)](https://github.com/sohamshewani)
[![Security: Hardened](https://img.shields.io/badge/Security-ASAN_%7C_UBSAN-10b981?style=flat-square&logo=shield)](https://github.com/sohamshewani)
[![Status: Autonomous 24/7](https://img.shields.io/badge/Cloud_Pipeline-Active-8b5cf6?style=flat-square&logo=githubactions)](https://github.com/sohamshewani)

</div>

---

### 🧬 Systems Architecture & Core Invariants

```text
 ┌──────────────────────┐       Zero-Copy Write Path       ┌──────────────────────┐
 │  Active MemTable     │ ───────────────────────────────► │ Write-Ahead Log      │
 │  (Lock-Free CSLM)    │ ───┐                             │ (CRC32 Checksummed)  │
 └──────────────────────┘   │ Atomic Freeze                └──────────────────────┘
                            ▼
 ┌──────────────────────┐  Pointer Swap Barrier            ┌──────────────────────┐
 │ Immutable MemTable   │ ───────────────────────────────► │ Tiered SSTables (L0) │
 │ (Concurrent Readers) │                                  │ (Bloom Filter Pruned)│
 └──────────────────────┘                                  └──────────────────────┘
```

* **Storage Engines & Compaction:** Log-structured merge-tree (LSM) engines, write-ahead logging (WAL), multi-way tiered compaction, and sparse-index binary searches.
* **Kernel Bypass & Runtimes:** Zero-copy circular ring buffers, sliding-window flow control, memory arena pooling, and asynchronous epoll/kqueue event loops.
* **Distributed State:** Raft consensus state machine replication, leader election, and SWIM gossip failure detection.

---

### 📊 Real-Time Telemetry & Systems Activity

<div align="center">
  <img src="[https://github-readme-stats.vercel.app/api?username=sohamshewani&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=06b6d4&text_color=c9d1d9&icon_color=06b6d4](https://github-readme-stats.vercel.app/api?username=sohamshewani&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=06b6d4&text_color=c9d1d9&icon_color=06b6d4)" height="155" alt="GitHub Stats" />
  <img src="[https://github-readme-stats.vercel.app/api/top-langs/?username=sohamshewani&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=06b6d4&text_color=c9d1d9](https://github-readme-stats.vercel.app/api/top-langs/?username=sohamshewani&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=06b6d4&text_color=c9d1d9)" height="155" alt="Language Metrics" />
</div>

<br/>

<div align="center">
  <img src="[https://github-readme-streak-stats.herokuapp.com/?user=sohamshewani&theme=tokyonight&hide_border=true&background=0d1117&ring=06b6d4&fire=06b6d4&currStreakLabel=06b6d4&sideNums=c9d1d9&sideLabels=8b949e](https://github-readme-streak-stats.herokuapp.com/?user=sohamshewani&theme=tokyonight&hide_border=true&background=0d1117&ring=06b6d4&fire=06b6d4&currStreakLabel=06b6d4&sideNums=c9d1d9&sideLabels=8b949e)" alt="Commit Streak" />
</div>

---

### 🏛️ Core Architectural Deployments

| System Node | Engine Domain | Core Invariant | Production Verification |
| :--- | :--- | :--- | :--- |
| **`lsmkv-engine`** | Storage Engine | Single-writer, multi-reader lock-free MemTable | `ASAN / UBSAN Verified` |
| **`docuquery`** | Document Intelligence | 100% On-premise air-gapped LLM inference | `Passed (Zero-Telemetry)` |
| **`codedoctor`** | Runtime Sandbox | Subprocess stderr fault interception & patching | `Self-Healing (Active)` |
| **`auto-cloud-maker`** | Autonomous Daemon | Continuous cloud multi-stage systems synthesis | `Verified 24/7 CI/CD` |

---

<div align="center">
  <sub>All systems authored under strict memory ownership invariants. Monitored continuously via GitHub Actions.</sub>
</div>
