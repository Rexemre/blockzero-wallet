# BLOCK ZERO · Wallet

Documentation hub for the Block Zero GUI wallet.

**👉 Full guide: [How to Use the Wallet](https://github.com/Rexemre/blockzero-docs/blob/main/how-to-use-wallet.md)**

| | |
|---|---|
| **Download** | https://github.com/Rexemre/blockzero-core/releases/latest |
| **Then mine** | [How to Mine BLOZ](https://github.com/Rexemre/blockzero-docs/blob/main/how-to-mine.md) |
| **Help** | [FAQ](https://github.com/Rexemre/blockzero-docs/blob/main/faq.md) · [Discord](https://discord.gg/FbJzrwAU2W) |

---

## Quick reference

| Step | Action |
|------|--------|
| **Windows** | Download zip → **Extract All** → `Start Block Zero.bat` |
| **macOS** | `curl -fsSL …/install-macos.sh \| bash` → open `Block Zero.app` |
| **Get address** | **Receive** tab → copy `bz1q…` |
| **Prune or full?** | **Prune** for most users (saves disk) |
| **Backup** | **File → Backup Wallet** + **Settings → Encrypt Wallet** |

One-line macOS install:

```bash
curl -fsSL https://raw.githubusercontent.com/Rexemre/blockzero-ops/main/scripts/mainnet/install-macos.sh | bash
open "$HOME/Applications/Block Zero.app"
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| macOS "damaged" | [FAQ](https://github.com/Rexemre/blockzero-docs/blob/main/faq.md#macos-block-zero-is-damaged-and-cant-be-opened) |
| Windows DLL error | Extract zip first |
| Prune / txindex | Remove `txindex` from `bitcoin.conf` |
| 0 peers | Add `addnode=217.160.46.61:8210` |

Full troubleshooting: [how-to-use-wallet.md § 9](https://github.com/Rexemre/blockzero-docs/blob/main/how-to-use-wallet.md#9-troubleshooting)

---

## Status

The wallet ships inside [blockzero-core](https://github.com/Rexemre/blockzero-core) (`bitcoin-qt`, branded **Block Zero**). This repo holds user-facing guides only — the code lives in blockzero-core.

A standalone mobile wallet may land here later.

---

## Links

| | |
|---|---|
| Website | https://bloz.org |
| Pool | https://pool.bloz.org |
| Explorer | https://explorer.bloz.org |
| All docs | [blockzero-docs](https://github.com/Rexemre/blockzero-docs) |
| Official links | [official-links.md](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md) |

> Copycat sites and third-party pools are **not affiliated** with Block Zero. [Warning →](https://github.com/Rexemre/blockzero-docs/blob/main/official-links.md#warning-copycat-sites--unofficial-services)
