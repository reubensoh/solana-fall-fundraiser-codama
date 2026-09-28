## Versions
anchor-cli 1.1.2 · node 24.20.0 · @codama/cli 1.6.3

## TODO 3
I still had to manually pass `mintToRaise`, `fundraiser`, and `vault`. Codama couldn't derive the `fundraiser` PDA automatically because its derivation seed relies on the `maker`'s pubkey (as seen in `initialize.rs`). Since the `maker` is not an account used in the `contribute` instruction, the client does not have the necessary seed data to calculate the address. Because it cannot calculate the `fundraiser` address, it also cannot calculate the `vault` address (which is an ATA derived from the `fundraiser` and the `mint`).

## Bonus
[attempted] and successfully passed all assertions!

## One thing that surprised me
I was surprised by how much extra manual work is required on the client side just because the Rust developer decided to omit a single account (the maker) to save space in the smart contract.