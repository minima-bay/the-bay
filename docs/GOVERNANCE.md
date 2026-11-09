# Governance of Minima Bay

As of 9 November 2026.

Minima Bay has no DAO of its own. It is governed by the [Stables Council](https://stablescouncil.org), which holds the
Stables card, Minima Bay and The Bridge as one structure.

**Nothing has been voted yet.** Who votes is the Council's first decision.

## Who holds what

- **The Council holds the mandate, never the keys.** It decides who operates each role, for how long and on what terms.
- **Operators hold the keys.** An operator is a person or an organisation, and each keeps its own key and runs its own
  program.
- **Today the development team operates every role.** Each will be decentralised, one at a time. A role is called
  independent only once it is.

The roles are approver, guardian, Bridge validator, matcher, and server and software maintenance.

## How operators are chosen, as designed

None of this is built yet.

- Terms are voted, last two years and are staggered, so that no single vote can reach a threshold.
- An operator stays until replaced. A missed or failed vote never stops payouts.
- Roles stay separate: approver and guardian seats have different operators.
- The Council votes the fee structure, and roles are awarded by bidding, open only to operators who meet a minimum
  quality. No operator may win enough seats to reach a threshold.
- Pay rises with quality measured from public facts, and comes from fees and the Treasury, never from customer money.
  It never counts stops or refusals, so nobody earns by stopping payouts.

## What there is to decide for Minima Bay

| Item | What a decision sets | State |
|---|---|---|
| Contract versions | Which version the apps use next | Designed, not built |
| Markets | Which pairs the apps list | Not built |
| Tick size and minimum order | Stamped into an order when it is placed, so a change applies to new orders only | Not built |
| Book publishing | How often The Pool's book is written on chain for new nodes | Running at every 50 blocks, never decided |
| Matchers and their fee | Who matches The Rapids' orders, their bond and the fee that pays them | Not built |
| Bridge validators and fees | Who sits on The Bridge's committee, their bond and the fee each way | Not built |

## What a decision reaches

A Council vote has no direct effect on the chain. No vote can change a deployed contract, an order or a balance. A
decision only reaches what comes next.

- **The Pool:** the contract has no admin key and no upgrade key, and its address is its code. A new version is a
  decision about which contract the apps point at next.
- **The Rapids:** the matcher keys are written into the contracts when they are deployed, so replacing a matcher today
  means a new deployment.
- **The Bridge:** no vote reaches the vault. Its validators change only through the rules in the vault itself.

## See also

[How it works](HOW-IT-WORKS.md) · [Security](SECURITY.md) · [The Bridge](BRIDGE.md)
