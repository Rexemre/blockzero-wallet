# BLOCK ZERO · Wallet

### **Mine with your CPU** — not a warehouse. **Start at Block Zero.**

Your Block Zero wallet — hold, send, and receive **BLOZ**, then mine on **pool.bloz.org** with the processor you already have. **RandomX** keeps ASIC & GPU farms out.

Fair launch. No presale. No insiders.

**👉 New here? [Join Discord →](https://discord.gg/FbJzrwAU2W)** · **⬇ [Download rc24](https://github.com/Rexemre/blockzero-core/releases/tag/v1.0.0-rc24)** · **⛏ [Mine on pool](https://github.com/Rexemre/blockzero-ops/tree/main/scripts/mainnet)**

---

## Download & install (GUI wallet)

**Latest Windows build:** **[v1.0.0-rc24](https://github.com/Rexemre/blockzero-core/releases/tag/v1.0.0-rc24)** — `blockzero-v1.0.0-rc24-windows-x64.zip`

Extract and run **`bin\bitcoin-qt.exe`**. MSVC runtime is bundled — no separate VC++ install needed.

All releases: https://github.com/Rexemre/blockzero-core/releases

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

Restart the wallet. Height should climb toward the live chain (**1726+** — check https://explorer.bloz.org).

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

## Then mine

1. Copy your **`bz1…` address** from the wallet (Receive tab)
2. Pool mine: [blockzero-ops/scripts/mainnet](https://github.com/Rexemre/blockzero-ops/tree/main/scripts/mainnet) → `./mine-pool.sh bz1YOURADDRESS`
3. Stats: [pool.bloz.org](https://pool.bloz.org) · Questions: **[Discord](https://discord.gg/FbJzrwAU2W)**

---

## Status

Wallet functionality ships inside `bitcoind` / `bitcoin-qt` from [blockzero-core](https://github.com/Rexemre/blockzero-core/releases). Latest: **v1.0.0-rc24**.

A dedicated standalone wallet app (GUI and/or mobile) may land in this repo later.

---

## Meanwhile

| Task | How |
|------|-----|
| Mine on pool | [pool-mining quickstart](https://github.com/Rexemre/blockzero-ops/blob/main/runbooks/pool-mining-quickstart.md) |
| Mine testnet | [Quick Start](https://github.com/Rexemre/blockzero-docs/blob/main/quickstart-mining.md) |
| Run a node | [Node Guide](https://github.com/Rexemre/blockzero-docs/blob/main/node-guide.md) |
| CLI wallet | `bitcoin-cli -rpcwallet=…` |

---

## Official links

| | |
|---|---|
| **Website** | https://bloz.org |
| **Pool** | https://pool.bloz.org |
| **Explorer** | https://explorer.bloz.org |
| **Discord** | https://discord.gg/FbJzrwAU2W |
| **Full list** | [official-links.md](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md) |

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

> **Warning:** Copycat sites (e.g. `.cc` domains) and third-party pools are **not affiliated** with Block Zero. [Read the full warning →](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md#warning-copycat-sites--unofficial-services)
