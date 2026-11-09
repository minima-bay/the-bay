# Privacy

Every service reached over the internet sees the IP address that reaches it. This page says which services Minima Bay
and its apps reach, and who sees your address. As of 9 November 2026.

It says who can see your address, not what each service keeps. You cannot check that from outside.

## The MEXC price

Inside Minima Bay, no app reads MEXC yet. When this arrives, you will be able to use MEXC's MINIMA/USDT price as a
market-making reference on The Pool and The Rapids. Nothing contacts MEXC unless you choose it.

| Route | Who sees your IP address | Who the price relies on |
|---|---|---|
| **Direct to MEXC** (the default) | MEXC, because your own device asks it. | MEXC. |
| **Through Minima Bay** (an option you choose) | Minima Bay's server, which asks MEXC for you. MEXC does not see your address. | MEXC, and Minima Bay's server to pass the price on unchanged. |

Neither route replaces the other without being asked. If the route you chose cannot be read, automatic rebalancing
pauses and says so.

The Pool's separate MiniDapp, run on your own Minima node, can already read MEXC if you choose MEXC as your reference.
Your node asks MEXC, so MEXC sees your node's address.

## Your own price feed

Where The Pool's market making is able to reach an outside address, it can read a price from one you give it. Whoever
runs that address sees yours.

## Other services

| Service | Who sees your address |
|---|---|
| **The website** | GitHub, which hosts it. The page asks GitHub for the newest release, and downloads come from GitHub. |
| **The Rapids** | The servers of The Rapids' matchers, which the app reaches over the network. |
| **Test ETH** | The server that pours test ETH, which uses your address to limit how often one person can ask. |
| **The Bridge** | The public services through which it reads Ethereum. |
| **The Minima network** | Other Minima nodes, which your node connects to. |
| **The built-in node, on the phone** | Also a public Minima service that gives it its list of peers, and the Minima server it can fetch the chain from. |
| **Links** | Telegram, X, GitHub, block explorers, a public test-ETH faucet and any other site linked from an app, once you open them. |
