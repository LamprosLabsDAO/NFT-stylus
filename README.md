# StylusNFT

A basic NFT deployment project using Stylus in Rust.

## 📋 Prerequisites

- Windows Subsystem for Linux (WSL) if using Windows
- Rust programming language
- Stylus CLI tool
- WASM build target for Rust

### 🖥️ Setting up WSL on Windows

1. Open PowerShell as Administrator and run:
   `wsl --install`
2. Restart your computer
3. Install Ubuntu from the Microsoft Store
4. Launch Ubuntu and set up your username and password

## 🚀 Installation

1. Install Rust:
   Visit https://www.rust-lang.org/tools/install and follow the instructions.

2. Install Stylus CLI:
   `cargo install --force cargo-stylus cargo-stylus-check`

3. Add WASM target:
   `rustup target add wasm32-unknown-unknown`

4. Clone the repository:
   `git clone https://github.com/LamprosLabsDAO/NFT-stylus`
   `cd NFT-stylus`

5. To verify deployment readiness:
   `cargo stylus check`

### 🔑 Setting up the private key

1. Create `pk.key` in the project root
2. Add your private key to this file

Need ARB Sepolia testnet tokens? Use this faucet: https://faucet.lamproslabs.io/

### 🚀 Deploying your program

1. Estimate deployment gas:
   `cargo stylus deploy --private-key-path=<PRIVKEY_FILE_PATH> --estimate-gas`

   Example:
   `cargo stylus deploy --private-key-path=./pk.key --estimate-gas`

2. Deploy the program:
   `cargo stylus deploy --private-key-path=<PRIVKEY_FILE_PATH>`

For more options:
`cargo stylus deploy --help`

## 🎨 Interacting with the NFT contract

1. Navigate to `Interact/erc721/scripts`

2. Install dependencies:
   `yarn`

3. Set up environment variables:
   `cp .env.example .env`

4. Run the minting script:
   `yarn mint`

## 📄 License

This project is licensed under the [MIT License](LICENSE).
