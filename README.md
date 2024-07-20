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

for more detailed guide refer : https://learn.microsoft.com/en-us/windows/wsl/install

## 🚀 Installation

1. Install Rust:
   enter this command in WSL
   `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

   restart WSL

2. Install Stylus CLI:
   `cargo install --force cargo-stylus cargo-stylus-check`

   If you are facing issue with installing with cc module then install
   `sudo apt update`
   `sudo apt install build-essential`

   check version
   `cc --version`

3. Add WASM target:
   `rustup target add wasm32-unknown-unknown`

4. Clone the repository:
   `git clone https://github.com/LamprosLabsDAO/NFT-stylus`

   `cd NFT-stylus`

5. To verify deployment readiness:
   `cargo stylus check`

   if you are getting error
   error: toolchain 'nightly-x86_64-unknown-linux-gnu' is not installed
   cargo build command failed

   run
   `rustup install nightly`

### 🔑 Setting up the private key

1. Create `pk.key` in the project root
2. Add your private key to this file

Need ARB Sepolia testnet tokens? Use this faucet: https://faucet.lamproslabs.io/

### Exporting ABI

`cargo stylus export-abi`

### 🚀 Deploying your program

1. Estimate deployment gas:
   `cargo stylus deploy --private-key-path=<PRIVKEY_FILE_PATH> --estimate-gas`

   Example:
   `cargo stylus deploy --private-key-path=./pk.key --estimate-gas`

2. Deploy the program:
   `cargo stylus deploy --private-key-path=<PRIVKEY_FILE_PATH>`

3. If it is not working then you can add the private key directly
   `cargo stylus deploy --private-key <PRIVKEY_KEY>`
   For more options:
   `cargo stylus deploy --help`

4. Once it is deployed you can paste you address on https://sepolia.arbiscan.io/ and check the status

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
