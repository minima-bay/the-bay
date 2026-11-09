# The Bridge

As of 9 November 2026.

The Bridge connects Ethereum and Minima: an asset locked on one side is carried 1:1 on the other. **Today it is a lab,
with the test asset ETHx, which has no value. Bridging is closed in the app until the next version is deployed.**

## How a transfer works

- **Ethereum to Minima:** you lock the asset in the vault on Ethereum. The validators check the deposit and sign, and
  the contract on Minima credits the same amount to your Minima wallet.
- **Minima to Ethereum:** you return the token on Minima. With enough validator signatures, the vault on Ethereum
  releases the same amount to your Ethereum address.

Every token on Minima is meant to be matched 1:1 by the asset in the vault. Minima cannot check Ethereum by itself, so
credits on the way in will always rest on the validators.

## Where it stands today

| | |
|---|---|
| Stage | Lab: the full round trip has run with the test asset ETHx |
| Validators | 7, of which 5 must sign each release |
| Who runs them | The development team, all seven in one place |
| Ethereum side of the lab | A private test chain standing in for Ethereum |
| Next test chain | Sepolia. The app can already reach it for test ETH, and no vault is deployed there yet |
| Guarded version | Built and run on a private test chain only |
| Bonds and fees | Designed, not live |

**Enforced on chain:** no release without five of the seven validators' signatures. A release signed by fewer was tried
and refused.

**Relies on the validators:** five of the seven, acting together, could release funds. That is why ETHx carries no
value.

ETHx has a fixed supply of 11, of which 10 were placed in The Bridge's contract on Minima. The Bridge's ETHx is not the
same token as the ETHx poured by The Faucet and traded on The Rapids today.

## The guarded version

In the guarded version, independent guardians watch both chains during a public wait before each release.

| Action | Guardians needed, of 9 |
|---|---|
| Stop one wrong release | 1 |
| Freeze all releases | 3 |
| Lift a freeze | 5 |
| Bring in a backup set of validators | 6 |

The validators cannot lift a freeze. These numbers, the waits and the limits are the values used in testing so far. In
this version, a stop or a freeze has no time limit, and only guardians can bring in a backup set.

## What must exist before an asset with value

In this order:

1. **Your own exit.** A proof on Ethereum that your asset was burned on Minima, needing nobody's permission, and a
   refund by the same kind of proof for a lock that was never credited.
2. **Every stop ends by itself.** A stop and a freeze each last a fixed time, and anyone can start bringing in the next
   validators once the current ones have been silent past a public deadline.
3. **Stake above what The Bridge holds.** Validators stake more than The Bridge holds, with the cap fixed in the contract.
   The stake is in Minima or an asset native to Minima, never USDT or ETH.
4. **Independent people.** Seven validators and nine guardians, on separate people, machines, places and providers,
   nobody in two roles.
5. **An outside audit.**

None of these exists yet.

## More detail

The research is public in [the-bridge](https://github.com/minima-bay/the-bridge). It dates from before the guarded
version.

## See also

[How it works](HOW-IT-WORKS.md) · [Security](SECURITY.md) · [Governance](GOVERNANCE.md)
