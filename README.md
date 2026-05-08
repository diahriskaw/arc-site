# Arc — Programmable Money L1 (demo site)

An elegant, single-file marketing site for [Arc](https://docs.arc.network) generated from `docs.arc.network/llms.txt`.

## Features
- 5 rotating hero variants (Aurora, Grid, Beams, Orbits, Mesh) — click **Home** in nav to cycle
- Structured sections: Network, Build, App Kit, Tools, Skills (cards link to official docs)
- **Connect Wallet** (EIP-1193) with auto add/switch to **Arc Testnet** (chainId `5042002`, USDC as gas)
- Live USDC gas balance via `eth_getBalance`, message signing via `personal_sign`
- Unified Balance simulator on App Kit panel
- Tailwind CDN + Inter / Space Grotesk via Google Fonts. No build step.

## Run locally
```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Network
| Param      | Value                              |
| ---------- | ---------------------------------- |
| Network    | Arc Testnet                        |
| Chain ID   | `5042002` (`0x4CF7D2`)             |
| RPC        | `https://rpc.testnet.arc.network`  |
| Currency   | USDC                               |
| Explorer   | https://testnet.arcscan.app        |
| Faucet     | https://faucet.circle.com          |

Content adapted from <https://docs.arc.network/llms.txt>.
