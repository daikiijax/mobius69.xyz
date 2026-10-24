# MOBIUS69

**Recover a compromised or drained wallet.**

## The problem

Your wallet is compromised. A sweeper bot watches it around the clock. The moment anything valuable appears, or the moment gas arrives to move it, the bot takes it first.

That is why the obvious fix fails. Sending gas to the drained wallet just feeds the bot. The gas gets drained before your rescue transaction ever runs.

## The idea

Do not fund the drained wallet. Fund a separate wallet instead.

MOBIUS69 uses a Sponsor Wallet: a fresh wallet that pays the gas. You never send gas to the drained wallet, so the bot has nothing to steal, and it never gets the window it needs.

On EVM chains, the rescue runs as a single atomic transaction using EIP-7702. The drained wallet authorizes the rescue contract, and the rescue itself executes in the same transaction. Either everything moves at once, or nothing moves. There is no gap in between for the bot to slip into.

On Solana, you simulate first. You see exactly what will be swept before anything moves, then you execute.

## The flow

### EVM rescue

1. **Pick the chain.** Choose the network where the compromised wallet lives.
2. **Generate a Sponsor Wallet.** A fresh wallet is created in your browser. Fund it with a small amount of native gas. This is the only wallet that ever receives gas.
3. **Set up the rescue.** Enter the drained wallet's private key, the Safe Receiver that will receive your assets, and what you want to rescue: claim an airdrop, transfer or withdraw tokens, withdraw native, unstake, mint or transfer an NFT, run a custom call, or revoke.
4. **Execute.** The drained wallet authorizes the rescue contract, and the assets move to your Safe Receiver in one atomic transaction, paid for by the sponsor.

### Solana rescue

1. **Generate a Sponsor Wallet.** A fresh keypair is created in your browser. Fund it with a small amount of SOL for fees and rent.
2. **Set up the sweep.** Enter the drained wallet's private key and the safe wallet that will receive your assets.
3. **Simulate.** The tool shows you exactly what will be swept, batch by batch, before anything moves.
4. **Execute.** SOL, tokens, and NFTs move to your safe wallet. Core NFTs have their own dedicated sweep.

## Why you can trust it

**Your keys never leave your device.** Everything runs in your browser. Your keys sign locally and are never sent to a server.

**The drained wallet never receives gas.** The sponsor pays. The bot cannot eat your gas money, and on EVM chains the atomic transaction gives it no window to front-run you.

**You pay only if it works.** There is no upfront payment. A 20% fee is taken from rescued assets only when the rescue succeeds. NFT rescues are free.

**You see it before it happens.** On Solana, simulation shows the full sweep before execution. On EVM chains, the transaction is atomic: it either completes fully or not at all.

**No account, no custody.** There is no signup and no server holding your assets. You bring your own wallets, and the assets go straight to your Safe Receiver.

## Coverage

- 26+ EVM chains, plus Solana.
- Interface in Indonesian and English.
- Fee: 20% of rescued tokens or native, only on success. NFT rescues: 0%.

## Links

- Website: https://mobius69.xyz
- Docs: https://mobius69.xyz/docs
- Partner program: https://mobius69.xyz/partner
- Telegram: https://t.me/mobius699
- X: https://x.com/mobius69xyz
