# Arc — Programmable Money L1 (demo site)

An elegant, single-file marketing site for [Arc](https://docs.arc.network), generated from `docs.arc.network/llms.txt`. Multi-variant hero, structured docs cards, and a working **Connect Wallet** flow that auto-adds Arc Testnet (USDC as gas).

🌐 **Live demo:** https://diahriskaw.github.io/arc-site/

---

## Features
- 5 rotating hero variants (Aurora · Grid · Beams · Orbits · Mesh) — click **Home** in nav or the **↻ Re-roll** button
- Structured sections from `llms.txt`: Network · Build · App Kit · Tools · Skills
- **EIP-1193 Connect Wallet** with auto `wallet_addEthereumChain` / `wallet_switchEthereumChain` to **Arc Testnet** (chainId `5042002`, USDC as gas)
- Live USDC balance via `eth_getBalance`, message signing via `personal_sign`
- Unified Balance simulator on App Kit panel
- Zero build step. Tailwind CDN + Google Fonts.

---

## Quick start (1 command)

```bash
git clone https://github.com/diahriskaw/arc-site.git && cd arc-site && python3 -m http.server 8080
```

Buka **http://localhost:8080** di browser yang punya wallet (MetaMask / Rabby / Coinbase Wallet / Rainbow).

### Alternatif server
```bash
# Node (http-server)
npx http-server -p 8080 .

# PHP
php -S 0.0.0.0:8080

# Caddy
caddy file-server --listen :8080
```

### Buka di port lain / akses publik (VPS)
```bash
python3 -m http.server 8080 --bind 0.0.0.0
# lalu buka http://<IP_VPS>:8080
sudo ufw allow 8080/tcp     # kalau pakai UFW
```

---

## Connect Wallet (manual, kalau mau)

| Field      | Value                              |
| ---------- | ---------------------------------- |
| Network    | Arc Testnet                        |
| Chain ID   | `5042002` (`0x4CF7D2`)             |
| RPC URL    | `https://rpc.testnet.arc.network`  |
| Currency   | USDC                               |
| Explorer   | https://testnet.arcscan.app        |
| Faucet     | https://faucet.circle.com          |

Tombol **Connect Wallet** di nav otomatis nge-add network ini ke wallet kamu.

---

## Deploy your own copy

### A. GitHub Pages (gratis, HTTPS)
```bash
# 1. fork / push repo ini ke akun kamu
gh repo create arc-site --public --source=. --push

# 2. enable Pages dari main / root
gh api -X POST repos/<USER>/arc-site/pages -f source.branch=main -f source.path=/
# atau: Settings → Pages → Source: Deploy from a branch → main / (root)
```
URL: `https://<USER>.github.io/arc-site/`

### B. Netlify
```bash
npx netlify deploy --dir=. --prod
```

### C. Vercel
```bash
npx vercel --prod
```

### D. Cloudflare Pages
```bash
npx wrangler pages deploy .
```

---

## Project structure
```
arc-site/
├── index.html      # whole app (HTML + Tailwind CDN + vanilla JS)
├── README.md
└── .gitignore
```

Mau ubah tampilan? Edit `index.html`:
- **Hero variants** — cari komentar `// ---------- Hero rotation ----------`, tambah varian di array `variants` + `copy`
- **Konten cards** — edit object `D` di bawah (pull dari `llms.txt`)
- **Wallet** — bagian `// ---------- Wallet (EIP-1193, Arc Testnet) ----------`

---

## Credits
- Content adapted from <https://docs.arc.network/llms.txt>
- Built on the [Circle](https://www.circle.com) / Arc developer platform
- UI: TailwindCSS, Inter, Space Grotesk

## License
MIT
