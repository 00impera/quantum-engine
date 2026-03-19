# ⚡ QUANTUM ENGINE NFT

> On-Chain SVG NFT Protocol · Monad Mainnet · LayerZero Cross-Chain Bridge

![Quantum Engine](preview.svg)

---

## 📋 Overview

**Quantum Engine** is a fully on-chain SVG NFT collection deployed on **Monad Mainnet**. Every NFT is a living quantum engine rendered 100% on-chain — no IPFS, no servers. Each token has a **quantum state** that changes its color palette, and can be **bridged cross-chain** via LayerZero with its state intact.

- 🎨 **10,000 NFTs** with on-chain SVG artwork
- 🌈 **8 Quantum States** — each with a unique color palette
- ⛓️ **Cross-chain bridging** via LayerZero V2
- 💜 **Built on Monad** — ultra-fast EVM blockchain
- 🔒 **No IPFS** — fully on-chain metadata and artwork

---

## 🔗 Contract

| Network | Address |
|---------|---------|
| Monad Mainnet | [`0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B`](https://explorer.monad.xyz/address/0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B) |

- **Chain ID:** 143
- **LayerZero EID:** 30143
- **Standard:** ERC-721 + ONFT721 (LayerZero V2)

---

## 🌈 Quantum States

Each NFT has one of 8 quantum states, each with a distinct color palette:

| State | Name | Color |
|-------|------|-------|
| 0 | SUPERPOSITION | White / Lavender |
| 1 | ENTANGLED | Purple |
| 2 | COLLAPSE | Indigo / Blue |
| 3 | DECOHERENCE | Emerald Green |
| 4 | TUNNELING | Orange |
| 5 | INTERFERENCE | Pink / Magenta |
| 6 | SPIN_UP | Cyan |
| 7 | VOID | Gold |

---

## 💰 Fee Structure

| Action | Cost |
|--------|------|
| Mint | 0.005 MON |
| Mint Batch (up to 10) | 0.005 MON × n |
| Shift State | 0.001 MON |
| Random Collapse | 0.001 MON |
| Bridge Cross-Chain | 0.002 MON + LayerZero gas |

---

## 🚀 How to Use

### Mint an NFT
Visit the [frontend interface](https://YOUR-USERNAME.github.io/quantum-engine/) and connect your MetaMask wallet on Monad Mainnet.

Or use cast directly:
```bash
cast send 0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B \
  "mint()" \
  --value 0.005ether \
  --rpc-url https://rpc.monad.xyz
```

### Shift Quantum State
```bash
cast send 0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B \
  "shiftState(uint256,uint8)" \
  TOKEN_ID NEW_STATE \
  --value 0.001ether \
  --rpc-url https://rpc.monad.xyz
```

### Bridge Cross-Chain (Example: Monad → Polygon)
```bash
cast send 0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B \
  "bridgeNFT(uint32,uint256,address,bytes)" \
  30109 TOKEN_ID YOUR_ADDRESS \
  "0x00030100110100000000000000000000000000030d40" \
  --value 0.05ether \
  --rpc-url https://rpc.monad.xyz
```

---

## ⛓️ Supported Bridge Destinations

| Chain | LayerZero EID |
|-------|--------------|
| Polygon | 30109 |
| Ethereum | 30101 |
| Base | 30184 |
| Arbitrum | 30110 |
| BNB Chain | 30102 |

---

## 🛠️ Technical Stack

- **Solidity** `^0.8.22`
- **LayerZero V2** — ONFT721 cross-chain standard
- **OpenZeppelin** v5 — ERC-721, ReentrancyGuard, Ownable
- **Foundry** — build, test, deploy
- **On-chain SVG** — Base64 encoded, no external dependencies

### Contract Architecture

```
QuantumEngine.sol     ← Main contract (ERC-721 + ONFT721)
QERenderer.sol        ← On-chain SVG rendering library
QEOracle.sol          ← Price stamp oracle library
```

---

## 🖥️ Frontend

The frontend is a single HTML file with no build process required.

- Connect MetaMask
- Mint, shift states, bridge cross-chain
- View your NFTs rendered on-chain
- Live quantum state color preview

---

## 📦 Deploy Your Own

```bash
# Clone and install Foundry
git clone https://github.com/YOUR-USERNAME/quantum-engine
cd quantum-engine

# Install dependencies
forge install OpenZeppelin/openzeppelin-contracts@v5.0.2 --no-git
forge install LayerZero-Labs/LayerZero-v2 --no-git
forge install LayerZero-Labs/devtools --no-git

# Deploy
export PRIVATE_KEY=0xYOUR_KEY
export MONAD_RPC=https://rpc.monad.xyz

forge script script/Deploy.s.sol \
  --rpc-url $MONAD_RPC \
  --private-key $PRIVATE_KEY \
  --broadcast \
  --chain-id 143
```

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">
  <strong>Built on Monad · Powered by LayerZero</strong><br>
  <a href="https://explorer.monad.xyz/address/0x8b39AF593EcC183cdd30E660e5aE2141499E4C4B">Explorer</a> ·
  <a href="https://YOUR-USERNAME.github.io/quantum-engine/">Live App</a>
</div>
