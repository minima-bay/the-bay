# How Minima Bay works

As of 9 November 2026. Minima Bay is in development, and every asset in it today is a test asset worth nothing.

Minima Bay is six decentralised finance apps for the Minima blockchain, in one install, with one Minima node and one
wallet.

## Two ideas

**What you hold is a set of separate objects on chain.** Your balance is simply the ones you hold right now, like notes
in a wallet rather than a figure on a statement.

**Each one can carry a rule.** Every node on the network checks that rule, and a transaction that breaks it is refused,
whoever sends it.

Together, these are why an order on The Pool can be an object with a rule attached, saying what it accepts in exchange.

## Your node

Every user runs a full Minima node on their own device. On Android, Minima Bay works with a node app (Minima Core,
PandaBear or BlackBear) or its built-in node, chosen in Settings. You allow Minima Bay in your node app, with Admin to
sign. Windows, with its own Minima node, is coming.

Minima Bay passes every app's commands to the node one at a time, so two apps never spend the same asset against each
other.

## The Faucet

Free test assets to try every app. Each asset sits in its own contract, with no owner and no key. The only way anything
leaves is a pour of a fixed amount, read from the contract itself.

| Faucet | Address | Pour |
|---|---|---|
| Winiwa | `0x5E08C5DCD965B9460C4734DC6113AE747C98DFEC31B13FEADF5805D464F49930` | 1,000 |
| USDx | `0xB0FA881A9733AF69EA8CC939EE76F794E6E27C1823813682E57AA2485FF88D5E` | 10 |
| ETHx | `0x9003F5AAE2DFBD7116C5715084C80A39B70AFB155846C3E1E20C6B5C2DCE3000` | 0.01 |
| Sand | `0xC536BC816AC61D74C5C2139F888AA5AF25DCB857ACC6AF0829B000F2C5391184` | 1 |

- One button sends four transactions, one per asset. Getting some but not all is reported as exactly that.
- A pour spends the faucet's own on-chain object, which can happen once per block, so two people claiming at the same
  moment means one retries. A block is about 46 seconds.
- The hour between pours is kept by the app. It is not a rule of the contract.

Winiwa, USDx, ETHx and Sand are worth nothing and redeem for nothing. USDx is unrelated to any real stablecoin, and ETHx
is not ether. Today The Faucet's ETHx and The Bridge's ETHx are two different tokens.

Test ETH for The Bridge is poured from The Bridge itself: 0.01 Sepolia ETH at a time, up to once an hour.

## The Pool

Swap straight from your wallet, with no deposit and no withdrawal.

Every order is its own object on chain, holding what you offer and the terms you accept, under one contract:
`0xF139672988BA32DBC5BA85A5A1BA969C4864DD1BCFAB090F40DA5FAE9540641A` (order contract v2.2). There is no vault, no shared
balance, no admin key, no upgrade key and no pause button.

- **Cancel:** only the maker's key can cancel, and the whole amount returns to the maker's refund address.
- **Fill:** each maker is paid their own limit price, inside the same transaction that takes the order. A part-filled
  order rests again at the same address.
- **No matching engine:** a taker spends the orders it crosses directly, so there is no operator in between.

A node only keeps records for contracts it was already watching, so the book is published on chain for new nodes to
import. Until then, the app says the book is unknown rather than showing an empty market.

More detail: [the-minima-pool](https://github.com/minima-bay/the-minima-pool).

## The Rapids

A fast order book, with four tabs: Graph, Order book, Trade and Market making.

You deposit into a shared vault on chain, then place, cancel and fill orders off chain, at once. Three matchers run the
book, and two of the three are needed to act. Orders are matched in batches of a second or less, and a fingerprint of
every balance goes on chain at least every 5 blocks.

**Withdrawing without the matchers.** If the matchers go quiet for 12 blocks, a trader's own node can exit from the
chain, after a 6-block window for disputes. The exit needs the balance data your device has kept. These timings are
test values.

Fees today are test values: 0.1% per fill, and 1 USDx per withdrawal.

Today, The Rapids rests on its matchers more than The Pool rests on anyone: see [Security](SECURITY.md).

## The Bridge

Between Ethereum and Minima. It is a lab today, and bridging is closed in the app until its next version is deployed.
See [The Bridge](BRIDGE.md).

## The Land and The Springboard

Lending and borrowing, and perpetual futures. Both are simulations inside Minima Bay today: nothing in them touches your
wallet or your node.

## If the app is wrong, or gone

**It can be wrong about what happened.** Minima Bay builds transactions and reports back. Where the app and the chain
disagree, the chain is the answer, and your own node can be asked directly.

**If it disappears:** orders on The Pool go on resting on chain, and each maker can cancel with their own key. Balances
in The Rapids can be withdrawn from the vault as described above, with the data your device has kept.

## See also

[Security](SECURITY.md) · [Governance](GOVERNANCE.md) · [The Bridge](BRIDGE.md) · [Privacy](../PRIVACY.md)
