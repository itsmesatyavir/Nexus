# 🚀 Nexus Testnet III — Prover Setup Guide

A step-by-step guide to install and run the Nexus Prover on your server.

---

## 📦 Requirements

- Ubuntu/Debian-based system
- Git, curl, and build tools
- Node ID (from [Nexus Dashboard](https://app.nexus.xyz/nodes))

---

## 🛠️ Step-by-Step Installation

### ✅ 1. Update System

```bash
sudo apt update && sudo apt upgrade -y
```

### ✅ 2. Install Dependencies

```bash
sudo apt install screen curl build-essential pkg-config libssl-dev git-all -y
sudo apt install protobuf-compiler -y
sudo apt update
```

### ✅ 3. Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

🔹 Follow the prompts to complete the Rust installation.  
🔹 Then run:

```bash
source $HOME/.cargo/env
```

### ✅ 4. Add RISC-V Target

```bash
rustup target add riscv32i-unknown-none-elf
```

---

## 🚀 Run the Prover

### 🖥️ Start a Background Session

```bash
screen -S nexus
```

### 🔧 Install Nexus CLI

```bash
curl https://cli.nexus.xyz/ | sh
```

### ▶️ Start the Prover

```bash
source ~/.bashrc
nexus-network start --node-id YOUR_NODE_ID
```
>example 
```bash
source ~/.bashrc
nexus-network start --node-id 6756232
```
```bash
source ~/.bashrc
nexus-network start --node-id 7268428
```
> 🔁 Replace `YOUR_NODE_ID` with your actual node ID from the Nexus dashboard.

---

## 📌 Useful Screen Commands

- **Detach screen** (keep it running in background):  
  `Ctrl + A`, then `D`

- **Reattach screen session:**  
  ```bash
  screen -r nexus
  ```

---

## 📚 Resources

- 🌐 [Nexus Dashboard](https://app.nexus.xyz)
- 📄 [Nexus Docs](https://docs.nexus.xyz/layer-1/testnet/cli-node#quick-install)

---

## 🙌 Credits

Maintained by the Nexus community. Feel free to contribute!
