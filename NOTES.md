cat << 'EOF' > NOTES.md
## Versions
anchor-cli 1.1.2 · node 24.20.0 · @codama/cli 1.6.3 · @codama/renderers-js 1.6.3 · @solana/kit (latest)

## TODO 3
I still had to manually pass `mintToRaise`, `fundraiser`, and `vault`. Codama couldn't derive the `fundraiser` PDA automatically because its derivation seed relies on the `maker`'s pubkey, which is not an account used in the `contribute` instruction. Because it lacked the `fundraiser` address, it also could not calculate the `vault` ATA. However, `contributorAccount` and `contributorAta` did NOT need to be passed because all their required seeds (the contributor signer, the mint, and the program ID) were already provided or known to the client.

## Bonus
[attempted] and successfully passed all assertions!

## One thing that surprised me
I was surprised by how much extra manual work is required on the client side just because the Rust developer decided to omit a single account (the maker) to save space in the smart contract.
EOF