# Solana Escrow Program

Description: This GitHub repository contains a Solana escrow program that allows users to create and exchange tokens in a secure and decentralized manner. The escrow program utilizes the Solana blockchain and implements smart contract logic to facilitate token transfers between parties. The program supports various operations such as initializing an escrow, canceling an escrow, and exchanging tokens between the initializer and the taker. It also includes functionality for creating and managing token accounts, minting tokens, and performing token transfers using the SPL token standard. The repository provides a complete implementation of the escrow program, along with the following documentation and example scripts for testing and interacting with the program. It can serve as a valuable resource for developers interested in building decentralized applications (DApps) on the Solana blockchain and leveraging escrow functionality for secure token transfers between parties.

### Features

- **Escrow Initialization**: Users can create an escrow by specifying the amount of tokens to be deposited by the initializer and the taker.
- **Token Exchange**: The taker can exchange their tokens with the initializer's tokens, ensuring a fair and secure transaction.
- **Escrow Cancellation**: The escrow can be canceled, allowing the tokens to be returned to the respective parties.

#### Prerequisites

You should have the following tools installed:

- Yarn
- Rust
- Anchor

If you do not have them installed, you can follow the instructions posted here: [https://www.anchor-lang.com/docs/installation](https://www.anchor-lang.com/docs/installation)

### Getting started

1. Clone the repository:

   ```bash
   git clone https://github.com/xonoxitron/solana-escrow-program
   cd solana-escrow-program
   ```

2. Build the Rust program:

    ```bash
    anchor build
    ```

3. Install the TypeScript dependencies:

    ```bash
    yarn install
    ```

### Setup

- Get the actual `program_id`, which is the public key of the deploy key with the following command:

    ```bash
    anchor keys list
    ```

- In `program/src/lib.rs` replace the content in the following line:

    ```bash
    declare_id!("<YOUR_PROGRAM_ID>");
    ```

- In `Anchor.toml` replace the content in the following line:
  
    ```toml
    [programs.localnet]
    solana_escrow_program = "<YOUR_PROGRAM_ID>"
    ```

- In `tests/solana-escrow-program.ts` replace the content in the following line:

    ```typescript
    const programId = "<YOUR_PROGRAM_ID>";
    ```

### Testing

The Solana Escrow Program includes a comprehensive suite of tests located in the `tests` directory. These tests cover various scenarios, such as initializing an escrow, exchanging tokens, and canceling the escrow. The tests utilize the Anchor testing utilities and interact with a local Solana network.

To run the tests, use the following command:

```bash
anchor test
```

Sample output:

```bash
(base) matteo@Matteos-MacBook-Pro solana-escrow-program % anchor test
    Finished release [optimized] target(s) in 0.31s

Found a 'test' script in the Anchor.toml. Running it as a test suite!

Running test suite: "/Users/matteo/Desktop/Projects/solana-escrow-program/Anchor.toml"

yarn run v1.22.19
$ /Users/matteo/Desktop/Projects/solana-escrow-program/node_modules/.bin/ts-mocha -p ./tsconfig.json -t 1000000 'tests/**/*.ts'


  anchor-escrow
https://solana.fm/tx/hCEcMTcewqnyWfggKMySbSR3eTfGQDM7Gy4ABChU3vgbdxVMc6KWkBLM6RLUtYSmfSdZ4FbTfSX15Nq2NT1Jcik?cluster=http%253A%252F%252Flocalhost%253A8899%252F
    ✔ Initialize program state (3935ms)
https://solana.fm/tx/37DRej4XF984gfDfKQASEhAzt6J3nzehgYD45c7C3721uuKLvVTuoQvLqPTRWxQNEv4zT1cWwxZv5PKCSbxL5wAs?cluster=http%253A%252F%252Flocalhost%253A8899%252F
    ✔ Initialize escrow (468ms)
https://solana.fm/tx/HUfpKenAmuGKDJu35mgADijS2CENmDmvFZ8mJVVKH5YZTFXdZSHNTd5iupGjEytEeHSxogzh5KJcTJsHwLhtbid?cluster=http%253A%252F%252Flocalhost%253A8899%252F
    ✔ Exchange escrow state (463ms)
https://solana.fm/tx/2zU8Hgb8FLNUAbdrhoUD3qu9pfcyUKCVWWv1ZKMREa21MsVCCG3nnvBwB3PEi4HekSgKwccQRJhi3QdZPEh5fBrW?cluster=http%253A%252F%252Flocalhost%253A8899%252F
https://solana.fm/tx/ekmE5FipdWUa5dHeyut9ZzLWNPtCHZGF7qUbk2xpHMixbZpHqF9qQYSiFGGfd9ZMZtknwGVXUFMLBo4nSDwDjRk?cluster=http%253A%252F%252Flocalhost%253A8899%252F
    ✔ Initialize escrow and cancel escrow (10670ms)


  4 passing (16s)

✨  Done in 17.07s.
```

## Contributing

Contributions to the Solana Escrow Program are welcome. If you have any ideas, improvements, or bug fixes, please open an issue or submit a pull request. Make sure to follow the existing code style and conventions.

## License

The Solana Escrow Program is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code as permitted by the license.
