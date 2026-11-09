# Security of Minima Bay

As of 9 November 2026.

**Not ready for real funds.** Every asset in Minima Bay today is a test asset and is worth nothing. There has been no
independent audit yet.

## Where your assets sit

| Where | What holds them | Who can move them today |
|---|---|---|
| Your wallet | Your keys, in your node, on your device | Only you |
| An order on The Pool | The order itself, under The Pool's contract | A taker, paying your price, or you, cancelling it back to yourself |
| A balance in The Rapids | A shared vault on chain | The matchers: any two of the three can move the whole vault. You, through them, or by the exit that needs no matcher |
| The Faucet | Four contracts with no owner and no key | Anyone, a fixed amount per pour |
| The Bridge (lab) | A vault on the Ethereum side and a contract on Minima | Five of the seven validators together |

## Your keys

- **On Android,** your keys stay in your node, on your device. You allow Minima Bay in your node app, with Admin to sign.
- **On Windows** (coming), Minima Bay carries its own node on your computer, and your keys stay in it.
- **No server holds your keys.** No Minima Bay server can sign for you.

## What you trust today

**On The Pool, you trust:**

- Minima itself, and your own node.
- The contract at its address, which you can read and compare with the published source.
- Minima Bay, while it builds your transaction.

**On The Rapids, you also trust the development team,** which today runs all three matchers and the server they are
reached through. A limit on what the matchers can move, watched by independent guardians, is designed and not built.
Until it exists, the way out without the matchers protects you if they stop, and does not protect you if they cheat.

**On The Bridge, you also trust the development team,** which today runs all seven validators in one place.

**Across the apps:** the six apps run together inside Minima Bay, so you trust all of them as one.

## What has been tested

**The Pool's contract.** Attacks on the live contract are listed with their results in
[its security document](https://github.com/minima-bay/the-minima-pool/blob/main/contracts/design/SECURITY.md). Most were
run against the contract's script without posting a transaction. Two are only partly shown that way, and one, filling an
order one atom at a time, is accepted and cannot be closed on chain: it is a nuisance and takes nothing.

**The Rapids.** The dispute and the exit, pressed in the app with every matcher stopped, paid the trader's whole signed
balance, on Minima's main network with test assets. That test ran on an earlier deployment, and no exit has yet been
taken on the current one.

**The Bridge.** A release signed by fewer than five validators was tried on chain and refused.

## Check it yourself

These are read-only commands for your own Minima node, typed in its Terminal.

| Question | Command |
|---|---|
| Every order resting on The Pool | `coins address:0xF139672988BA32DBC5BA85A5A1BA969C4864DD1BCFAB090F40DA5FAE9540641A` |
| What a faucet still holds | `coins address:<the faucet's address>` |

An empty answer means your node is not yet watching that address, which is different from the address being empty.

To compare the contracts on chain with the published source, run `tools/verify-contracts.mjs` from
[the-minima-pool](https://github.com/minima-bay/the-minima-pool). It is a Node.js script that talks to your node.

## What is public

The Pool's code and The Bridge's research are public on [GitHub](https://github.com/minima-bay), and every other app's
code goes up as each is made available. The public copy of The Pool is older than the current app. The order contract
is the same.

## What real funds require

Before any asset with value is invited into Minima Bay:

1. An independent review of every contract and of the app's signing paths.
2. A stated worst-case loss for each app.
3. A limit on what The Rapids' matchers can move.
4. Bonded matchers for The Rapids, and independent, bonded validators for The Bridge.
5. Every write path verified the way placing an order on The Pool already is.
6. A test period measured in months, not days.
7. Every action run on a fresh node that has never touched the project.

## Report a problem

Found something that rests on a person instead of a rule? That is a bug worth reporting. Tell the community on
[Telegram](https://t.me/MinimaBay), or open an issue on [GitHub](https://github.com/minima-bay/the-bay/issues).

## See also

[How it works](HOW-IT-WORKS.md) · [Governance](GOVERNANCE.md) · [The Bridge](BRIDGE.md) · [Privacy](../PRIVACY.md)
