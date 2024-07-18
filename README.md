# Project Name

Brief description of your project.

## Prerequisites

Before installing Rust, you need to set up Windows Subsystem for Linux (WSL) if you're using Windows.

### Installing WSL on Windows

1. Open PowerShell as Administrator and run:

   wsl --install

2. Restart your computer.

3. Open the Microsoft Store and install Ubuntu (or your preferred Linux distribution).

4. Launch Ubuntu and set up your username and password.

## Installation

1. Clone the repository:

   git clone https://github.com/LamprosLabsDAO/NFT-stylus
   cd NFT-stylus

2. Install Rust:

   Visit https://www.rust-lang.org/tools/install and follow the instructions for your operating system.

3. Install the Stylus CLI tool with Cargo:

   cargo install --force cargo-stylus cargo-stylus-check

4. Add WASM as a build target for your Rust compiler:

   rustup target add wasm32-unknown-unknown

## Usage

### Checking your program

To check whether your program will successfully deploy and activate onchain:

cargo stylus check

### Deploying your program

1. Estimate the gas required for deployment:

   cargo stylus deploy \
   --private-key-path=<PRIVKEY_FILE_PATH> \
   --estimate-gas-only

2. Deploy the program:

   cargo stylus deploy \
   --private-key-path=<PRIVKEY_FILE_PATH>

   This will send two transactions onchain.

For more deployment options, run:

cargo stylus deploy --help

## Setting up the private key

1. Create a file named pk.key in the project root.
2. Enter your private key in this file. Make sure to keep it secure and have sufficient funds in the associated address.

If you need ARB Sepolia testnet tokens, you can use this faucet: [https://faucet.lamproslabs.io/]

## Interacting with the NFT contract

1. Go to the Interact/erc721/scripts directory.

2. Install dependencies:

   yarn

3. Copy and fill the .env file:

   cp .env.example .env

4. Run the minting script:

   yarn mint

## Contributing

Instructions for how to contribute to your project.

## License

Specify your project's license here.
