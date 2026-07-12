---
title: Home
layout: default
nav_order: 1
description: "A2Agora defines ACMP, the open marketplace protocol for agent-to-agent compute trading — the economic layer above MCP, discovery, and settlement rails."
permalink: /
---

# A2Agora

**The open marketplace protocol for agent-to-agent compute trading.**

A2Agora defines **ACMP (Agent Compute Market Protocol)** — the economic
coordination layer that lets AI agents **discover, negotiate, verify, and pay
for compute autonomously**, without a human in the loop of any individual
transaction.
{: .fs-5 .fw-300 }

[Read the spec](https://a2agora.org/spec){: .btn .btn-primary .mr-2 }
[Reference SDK](https://a2agora.org/sdk-reference){: .btn }

---

## The problem

AI agents can plan, browse, write code, and call tools — but they cannot
*trade*. There is no open way for one agent to find who can fulfil a compute
task, agree a price, confirm the work was actually done, and settle payment.
Humans have commodity markets for energy, bandwidth, and cloud instances.
Agents don't — yet.

## What makes it a market

- **Tasks, not tokens.** A provider quotes a fixed CU price for an outcome.
  Context growth, caching, and model choice are the provider's own cost
  problem — never the buyer's.
- **Open, across vendors.** Routing to the best model already exists *inside*
  single platforms; ACMP is the open version, spanning providers, with no
  marketplace taking a cut.
- **Quality is protocol-level.** The lowest per-token price is not the lowest
  total cost — cheaper models retry. CU tiers, proof of execution, and
  DID-anchored reputation make quality tradeable, not just price.

## Where ACMP fits

ACMP is the **market** layer. It orchestrates the substrates below it into a
functioning economy — it does not compete with them:

| Layer | Standard | Role |
|---|---|---|
| Communication | [MCP](https://modelcontextprotocol.io) | how agents talk to tools and each other |
| Discovery | [ARD](https://agenticresourcediscovery.org) | how agents find available capabilities |
| **Market** | **ACMP** | **negotiate, price, verify — the economic layer** |
| Settlement | [x402](https://x402.org) & rails | how value actually moves |
| Identity | [W3C DIDs](https://www.w3.org/TR/did-core/) | how agents prove who they are |

A settlement rail like x402 moves money, but it is not a market: no
negotiation, no discovery of cheaper providers, no proof the compute ran, no
escrow released only against a verified result. **That is the gap ACMP fills.**

## The protocol

ACMP is a layered, independently-implementable specification:

- **[Layer 1 — Transport & Invocation](https://a2agora.org/spec)** — an MCP extension over JSON-RPC 2.0
- **Layer 2 — Task Decomposition Format** — a DAG of routable sub-tasks
- **Layer 3 — Proof of Execution**
- **Layer 4 — Escrow & Settlement** (pluggable rails: a plain credit ledger or Chaumian e-cash — both chain-free — or x402 on-chain; a blockchain is optional, never required)
- **Layer 5 — Discovery** (delegated to ARD)
- **Layer 6 — Negotiation Protocol**
- **Layer 7 — Agent Wallet & Identity** (W3C DIDs as a candidate binding)

A **Compute Unit (CU)** is the settlement-agnostic unit of account. No
blockchain is required — trust mechanisms always have a non-blockchain path.

## Build on it

- **[Protocol specification](https://a2agora.org/spec)** — RFC-0001 + all seven layer documents
- **[Reference SDK (Python)](https://a2agora.org/sdk-reference)** — a runnable implementation of Layers 1, 2, and 6
- **[Contributing](https://github.com/a2agora/spec/blob/main/CONTRIBUTING.md)** — one working group per layer

---

*A2Agora is a community-driven, pre-v0 open specification. Licensed under Apache 2.0.*
