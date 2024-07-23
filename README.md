# StylusNFT

A basic NFT deployment project using Stylus in Rust.

## 📋 Prerequisites

- Windows Subsystem for Linux (WSL) if using Windows
- Rust programming language
- Stylus CLI tool
- WASM build target for Rust

### 🖥️ Setting up WSL on Windows

1. Open PowerShell as Administrator and run:

   ```sh
   wsl --install
   ```

2. Restart your computer
3. Launch Ubuntu and set up your username and password

For a more detailed guide, refer to the [Microsoft documentation](https://learn.microsoft.com/en-us/windows/wsl/install).

## 🚀 Installation

1. **Install Rust:**
   Enter this command in WSL:

   ```sh
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```

   Restart WSL.

2. **Install Stylus CLI:**

   ```sh
   cargo install --force cargo-stylus cargo-stylus-check
   ```

   If you are facing issues with the `cc` module, install:

   ```sh
   sudo apt update
   sudo apt install build-essential
   ```

   Check the version:

   ```sh
   cc --version
   ```

3. **Add WASM target:**

   ```sh
   rustup target add wasm32-unknown-unknown
   ```

4. **Clone the repository:**

   ```sh
   git clone https://github.com/LamprosLabsDAO/NFT-stylus
   cd NFT-stylus
   ```

   The `cargo stylus` command comes with useful commands such as `new`, `check`, `deploy`, and `export-abi` for developing and deploying Stylus programs to Arbitrum chains. Here's a common workflow:

   To verify deployment readiness:

   ```sh
   cargo stylus check
   ```

### Exporting ABI

    cargo stylus export-abi

### 🚀 Deploying your program

1. **Estimate deployment gas:**

   ```sh
   cargo stylus deploy --private-key <PRIVKEY> --estimate-gas
   ```

2. **Deploy the program:**

   ```sh
   cargo stylus deploy --private-key <PRIVKEY>
   ```

   For more options:

   ```sh
   cargo stylus deploy --help
   ```

3. Once it is deployed, you can paste your address on [Arbiscan](https://sepolia.arbiscan.io/) to check the status.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
