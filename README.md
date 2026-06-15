# BLOCK ZERO · Wallet

**Modern BTC code. A second chance at Genesis.**

User-facing wallet for Block Zero — hold, send, and receive **BLOZ** with software you control.

Fair launch. No presale. No insiders.

---

## Official links

| | |
|---|---|
| **Website** | https://bloz.org |
| **Pool** | https://pool.bloz.org *(test release)* |
| **Explorer** | https://explorer.bloz.org · testnet: https://texplorer.bloz.org |
| **Bridge** | https://bridge.bloz.org |
| **Discord** | https://discord.gg/FbJzrwAU2W |
| **X (Twitter)** | https://x.com/Block_Zero_2009 |
| **Full list** | [official-links.md](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md) |

**Mainnet seed:** `217.160.46.61:8210`

> **Warning:** Copycat sites (e.g. `.cc` domains) and third-party pools are **not affiliated** with Block Zero — we have no insight into their code and accept **no liability** for malware, wrong-chain mining, fraud, or unfair pool payouts. [Read the full warning →](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md#warning-copycat-sites--unofficial-services)

---

## Download & install (GUI wallet)

**Official binaries:** https://github.com/Rexemre/blockzero-core/releases

Download the latest **Windows** zip (`blockzero-*-win64.zip`), extract, run **`bitcoin-qt.exe`**.

### Sync stuck at launch day (June 6)?

Block Zero has **no DNS seeds**. If the wallet shows **100% progress** but **unknown blocks remaining** and the last block is still from **6 Jun 2026**, it has **no peer** to the network.

**Fix (all releases):** create or edit `bitcoin.conf`:

| OS | Path |
|----|------|
| Windows | `%LOCALAPPDATA%\BlockZeroMainnet\bitcoin.conf` |
| Linux / macOS | `~/.blockzero-mainnet/bitcoin.conf` |

Minimum contents:

```ini
server=1
txindex=1

[main]
listen=1
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
rpcport=8332
addnode=217.160.46.61:8210
```

Restart the wallet. Height should climb toward the live chain (~1000+ — check https://explorer.bloz.org).

**Verify in Debug console** (Help → Debug window → Console):

```
getconnectioncount   → should be ≥ 1
getblockcount        → should match explorer height
```

If `getconnectioncount` stays 0, your firewall may block outbound **TCP 8210**.

**Easier setup (Windows):** [blockzero-ops `mine-mainnet.ps1`](https://github.com/Rexemre/blockzero-ops/tree/main/scripts/mainnet) creates wallet + config automatically.

### Built-in seed (core v1.0.0-rc10+)

Newer releases embed the mainnet seed as a **fixed fallback peer** — `bitcoin-qt` connects out of the box without `bitcoin.conf`. The `addnode` line above still helps if the seed is unreachable.

---

## Status

**In development.** Today, wallet functionality ships inside `bitcoind` / `bitcoin-qt` from [blockzero-core](https://github.com/Rexemre/blockzero-core/releases).

A dedicated wallet app (GUI and/or mobile) will land here.

---

## Meanwhile

| Task | How |
|------|-----|
| Mine on pool | [pool-mining quickstart](https://github.com/Rexemre/blockzero-ops/blob/main/runbooks/pool-mining-quickstart.md) |
| Mine testnet | [Quick Start](https://github.com/Rexemre/blockzero-docs/blob/main/quickstart-mining.md) |
| Run a node | [Node Guide](https://github.com/Rexemre/blockzero-docs/blob/main/node-guide.md) |
| CLI wallet | `bitcoin-cli -rpcwallet=…` |

---

## Repositories

| Repo | Link |
|------|------|
| Core | [blockzero-core](https://github.com/Rexemre/blockzero-core) |
| Docs | [blockzero-docs](https://github.com/Rexemre/blockzero-docs) |
| Ops | [blockzero-ops](https://github.com/Rexemre/blockzero-ops) |
| **Wallet** (here) | [blockzero-wallet](https://github.com/Rexemre/blockzero-wallet) |

---

## Disclaimer

Block Zero is open-source software. BLOZ/TBLOZ carry no promised value, liquidity or return.
