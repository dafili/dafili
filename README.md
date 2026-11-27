<div align="center">

<img src="https://raw.githubusercontent.com/dafili/dafili/main/assets/banner.jpg" alt="Renhua Wei — homelab desk: code, books, and the rack the tools are tested on" width="100%" />

# Renhua Wei · `dafili`

**Seven tools shipped and running, 12 patches merged into other people's projects, 18 postmortems with the numbers still attached.**

Independent developer · Sichuan, China

[![Vaultcheck](https://img.shields.io/badge/Vaultcheck-Linux%20audit-0b7285?style=flat-square)](https://vaultcheck.dafili.cn)
[![NPILift](https://img.shields.io/badge/NPILift-B2B%20data-5f3dc4?style=flat-square)](https://npilift.dafili.cn)
[![WIPLink](https://img.shields.io/badge/WIPLink-shop%20floor-2f6f4e?style=flat-square)](https://wiplink.com)
[![Dev.to](https://img.shields.io/badge/Dev.to-dafili-0a0a0a?style=flat-square&logo=dev.to&logoColor=white)](https://dev.to/dafili)
[![Hashnode](https://img.shields.io/badge/Hashnode-blog-2962ff?style=flat-square&logo=hashnode&logoColor=white)](https://mediaforge-studio.hashnode.dev)
[![Email](https://img.shields.io/badge/Email-support%40dafili.cn-c92a2a?style=flat-square&logo=maildotru&logoColor=white)](mailto:support@dafili.cn)

</div>

---

## What I work on

Most monitoring lies in a specific way: it reports success it never verified. A backup job exits `0` while the dump was truncated. A probe reports `timeout` and cannot say whether the target died or the probe did. A check passes because the thing it was supposed to test was never actually run.

I build tools that separate **"the command finished"** from **"the thing is actually true"**, and I write about the difference with measurements rather than assertions.

---

## Shipped and running

Seven tools, all live, all built solo. Each one started as a problem I hit myself and had to solve before I could sell anyone anything.

| | Project | What it does |
|---|---|---|
| 🔍 | **[Vaultcheck](https://vaultcheck.dafili.cn)** | Read-only Linux audit in one command: what is about to break, and did last night's backup actually run. Pure Python standard library, zero dependencies. |
| 📊 | **[NPILift](https://npilift.dafili.cn)** | US provider data extraction. NPI-registered organisations filtered by specialty and state, exported to CSV with deduplication and quality scoring. |
| 📡 | **[Recall Radar](https://recall.dafili.cn)** | Watches CPSC and FDA recall feeds against the SKUs you actually sell, and mails you the same day one matches. |
| 📦 | **[eFiling Preflight](https://efiling.dafili.cn)** | Seven-point check of a CPC/GCC data file before the broker files it into ACE, where a bad file kills the shipment. |
| 📄 | **[DocMatch](https://docmatch.dafili.cn)** | Invoice, packing list, test report: mismatches found line by line, each one tied to the regulation it breaks. |
| 🚚 | **[ShipMargin](https://shipmargin.dafili.cn)** | Shopify orders against the carrier bill: which zones, weight bands and box presets leak money on shipping, and by how much. |
| 🪵 | **[WIPLink](https://wiplink.com)** | Job tracking for 3–20 person woodworking shops. Scan a QR sticker at each stage; good and scrap counts land on the office board without the phone call. |

---

## Open source

Where I can add something a maintainer would otherwise have to write themselves, I send the test and the measurement instead of an opinion.

### Merged — 12 pull requests across five repositories

| Repository | PRs | Change |
|---|---|---|
| **[magitech-ai/animas](https://github.com/magitech-ai/animas)** | [#53](https://github.com/magitech-ai/animas/pull/53) [#56](https://github.com/magitech-ai/animas/pull/56) [#57](https://github.com/magitech-ai/animas/pull/57) [#58](https://github.com/magitech-ai/animas/pull/58) [#61](https://github.com/magitech-ai/animas/pull/61) [#83](https://github.com/magitech-ai/animas/pull/83) [#84](https://github.com/magitech-ai/animas/pull/84) | `+565 −48` across seven — logger clipping on visible width and re-closing open SGR sequences, throttle windows driven by the monotonic clock, disposer wired before a service becomes visible, absolute and nested target paths in `Scaffold.start`, an `ERROR` level read as unset, and infinite recursion when `__cause__` loops back on itself. |
| **[daniel-ospina/tortoise](https://github.com/daniel-ospina/tortoise)** | [#14726](https://github.com/daniel-ospina/tortoise/pull/14726) | `+652 −55` — the `#appeal` section `appeal_url()` names, plus a guard on the fragment class. |
| **[AfterShip/email-verifier](https://github.com/AfterShip/email-verifier)** | [#238](https://github.com/AfterShip/email-verifier/pull/238) [#235](https://github.com/AfterShip/email-verifier/pull/235) | `+282 −0` — pins the MX-before-dial ordering in `newSMTPClient` so it is offline and deterministic; covers `GenerateRandomEmail` and `getMD5Hash`, the two pure functions with none. |
| **[RobinaMirbahar/railpulse-gemma-cloudrun](https://github.com/RobinaMirbahar/railpulse-gemma-cloudrun)** | [#3](https://github.com/RobinaMirbahar/railpulse-gemma-cloudrun/pull/3) | `+167 −8` — a guardrail that read a missing sensor as "no wind" now fails closed on unknown blocks, occupied sidings and unreadable wind. Nine failing tests written first, all nineteen green after. |
| **[HeyPuter/puter](https://github.com/HeyPuter/puter)** | [#4411](https://github.com/HeyPuter/puter/pull/4411) | `+19 −1` — install documentation: the Docker path the instructions skipped, reproduced before it was written up. |

### Open — 4

| Repository | Pull request | Change |
|---|---|---|
| **[bytedance/deer-flow](https://github.com/bytedance/deer-flow)** | [#8732](https://github.com/bytedance/deer-flow/pull/8732) | sandbox provisioner rollback, scoped to the Pod this request created rather than whatever the cleanup sweep found. |
| **[tenstorrent/tt-metal](https://github.com/tenstorrent/tt-metal)** | [#63655](https://github.com/tenstorrent/tt-metal/pull/63655) | `+1 −1` — `RelWithDebugInfo` → `RelWithDebInfo`, a build-type typo that silently produced an unoptimised build. |
| **[VeridionLabs/veridion](https://github.com/VeridionLabs/veridion)** | [#121](https://github.com/VeridionLabs/veridion/pull/121) [#120](https://github.com/VeridionLabs/veridion/pull/120) | the argument-less `SorobanClient` spec that broke `format:check`, and a timestamp-dependence detection plugin. |

> Twelve merged, four open. I do not describe an open pull request as merged — that distinction is the whole subject of the writing below.

---

## Writing

Eighteen published postmortems in the Silent Failure series, each built around one real bug I hit, with the failing output kept in the post. Recent three:

- **[#17 The reply that landed while the script was still waiting](https://dev.to/dafili/silent-failure-17-the-reply-that-landed-while-the-script-was-still-waiting-f8d)** — a `--wait 90` inner budget of 270 seconds against a 180-second outer timeout that always fired first, and the reply that had in fact posted in two seconds while the log said nothing happened.
- **[#16 The sweep counted what I planned, not what I read](https://dev.to/dafili/silent-failure-16-the-sweep-counted-what-i-planned-not-what-i-read-3hmi)** — `skip article 5031601: <urlopen error timed out>` printed to stderr, and the sweep still exited `0` with a clean-looking count.
- **[#15 The draft that existed and was never shown](https://dev.to/dafili/silent-failure-15-the-draft-that-existed-and-was-never-shown-22ga)** — two gates in one sync script that both failed open: `EXIT=0`, and `grep -c` for the draft returned 0.

All eighteen live on [Dev.to](https://dev.to/dafili), mirrored to [Hashnode](https://mediaforge-studio.hashnode.dev).

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

<sub>Every number on this page was measured, not estimated. Where it was wrong, it was corrected in public. Counts last checked 2026-11-28.</sub>

</div>
