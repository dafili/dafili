<div align="center">

<img src="https://raw.githubusercontent.com/dafili/dafili/main/assets/banner.jpg" alt="Renhua Wei — homelab desk: code, books, and the rack the tools are tested on" width="100%" />

# Renhua Wei · `dafili`

**Building zero-dependency CLI tools for Linux auditing and B2B data extraction.**

Independent developer · Sichuan, China

[![Vaultcheck](https://img.shields.io/badge/Vaultcheck-Linux%20audit-0b7285?style=flat-square)](https://vaultcheck.dafili.cn)
[![NPILift](https://img.shields.io/badge/NPILift-B2B%20data-5f3dc4?style=flat-square)](https://npilift.dafili.cn)
[![Dev.to](https://img.shields.io/badge/Dev.to-dafili-0a0a0a?style=flat-square&logo=dev.to&logoColor=white)](https://dev.to/dafili)
[![Hashnode](https://img.shields.io/badge/Hashnode-blog-2962ff?style=flat-square&logo=hashnode&logoColor=white)](https://mediaforge-studio.hashnode.dev)
[![Email](https://img.shields.io/badge/Email-support%40dafili.cn-c92a2a?style=flat-square&logo=maildotru&logoColor=white)](mailto:support@dafili.cn)

</div>

---

## What I work on

Most monitoring lies in a specific way: it reports success it never verified. A backup job exits `0` while the dump was truncated. A probe reports `timeout` and cannot say whether the target died or the probe did. A check passes because the thing it was supposed to test was never actually run.

I build tools that separate **"the command finished"** from **"the thing is actually true"**, and I write about the difference with measurements rather than assertions.

---

## Projects

| | Project | What it does |
|---|---|---|
| 🔍 | **[Vaultcheck](https://vaultcheck.dafili.cn)** | Read-only Linux health and backup-freshness audit. Eleven checks, pure Python standard library, zero dependencies. Its point is the failure it catches: a backup that stopped three weeks ago while every dashboard stayed green. |
| 📊 | **[NPILift](https://npilift.dafili.cn)** | US healthcare provider data extraction. NPI-registered organisations filtered by specialty and state, exported to CSV with deduplication and quality scoring. |

Both are shipped, both are sold to real customers, and both exist because I hit the problem myself first.

---

## Open source

Where I can add something a maintainer would otherwise have to write, I send the tests and the measurement rather than an opinion.

### Merged

| Repository | Pull request | Change |
|---|---|---|
| **[AfterShip/email-verifier](https://github.com/AfterShip/email-verifier)** | [#235](https://github.com/AfterShip/email-verifier/pull/235) | `+112 −0` — test coverage for `GenerateRandomEmail` and `getMD5Hash`, the two pure functions with none. Reviewed and merged by the maintainer. |
| **[HeyPuter/puter](https://github.com/HeyPuter/puter)** | [#4411](https://github.com/HeyPuter/puter/pull/4411) | `+19 −1` — install documentation: the Docker path that the instructions skipped, reproduced before it was written up. |

### In review

| Repository | Pull request | Change |
|---|---|---|
| **[AfterShip/email-verifier](https://github.com/AfterShip/email-verifier)** | [#238](https://github.com/AfterShip/email-verifier/pull/238) | `+188 −0` — pins the MX-before-dial ordering in `newSMTPClient`, offline and deterministically. Opened after the maintainer pointed at the missing seam. |
| **[restic/restic](https://github.com/restic/restic)** | [#22160](https://github.com/restic/restic/pull/22160) | `+10 −2` — documents that `--read-data-subset=n/t` can produce empty groups, verified by running it on a four-pack repository. |
| **[tenstorrent/tt-metal](https://github.com/tenstorrent/tt-metal)** | [#63655](https://github.com/tenstorrent/tt-metal/pull/63655) | `+1 −1` — `RelWithDebugInfo` → `RelWithDebInfo`, a build-type typo that silently produced an unoptimised build. |

> Two merged, three awaiting review. I do not describe an open pull request as merged — that distinction is the whole subject of the writing below.

---

## Writing

I write about verification failures with the numbers attached, usually after doing the experiment that either confirms or kills the hypothesis.

- **[Your monitor is reporting its own network problems](https://dev.to/dafili/your-monitor-is-reporting-its-own-network-problems-4fah)** — a 48-second timeout that cannot distinguish a dead target from a dead probe, with the IPv6 blackhole case measured at 259 ms versus 48,048 ms.
- **[Three checks that look like they passed, but validated nothing](https://dev.to/dafili/three-checks-that-l…they-passed-but-validated-nothing-ejd)** — a `pg_dump` killed mid-pipe that still exits `0`, passes `gzip -t`, and lists all seven tables in `pg_restore -l`.
- **[My backup exited 0 for three weeks and nothing paged me](https://dev.to/dafili/my-backup-exited-0-for-three-weeks-and-nothing-paged-me)** — artifact age versus exit code, and why the exit code is the weaker signal.

All of it also lives on [Dev.to](https://dev.to/dafili) and [Hashnode](https://mediaforge-studio.hashnode.dev).

---

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![systemd](https://img.shields.io/badge/systemd-000000?style=flat-square&logo=systemd&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

<div align="center">

**If you found a bug in something I shipped, tell me — the reproduction is worth more than the complaint.**

<sub>Every number on this page was measured, not estimated. Where it was wrong, it was corrected in public.</sub>

</div>
