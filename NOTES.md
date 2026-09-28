# Checkpoint 03 / TODO 3 Notes

I still had to manually pass `mintToRaise`, `fundraiser`, and `vault`.

Codama couldn't derive the `fundraiser` PDA automatically because its derivation seed relies on the `maker`'s pubkey (as seen in `initialize.rs`). Since the `maker` is not an account used in the `contribute` instruction, Codama does not have the necessary seed data to calculate the address.

Because it cannot calculate the `fundraiser` address, it also cannot calculate the `vault` address (which is an ATA derived from the `fundraiser` and the `mint`).