# Reanimated Dead × Reactive Network

This repository is the planned public home for the Reactive Network integration components proposed for **Reanimated Dead**, a live browser-based trading card game.

**Project:** Reanimated Dead  
**Live game:** https://reanimateddead.com  
**Network:** Reactive Network  
**Status:** Proposed / pre-development

## About Reanimated Dead

Reanimated Dead is a free-to-play browser trading card game built around gameplay first and optional digital ownership.

Players can play without cryptocurrency, a wallet, or an NFT.

The live game currently includes:

- Solo and multiplayer gameplay
- Ethereum NFT utility
- Solana NFT utility
- Stripe and Ethereum commerce
- Player profile badges

Additional cosmetics, owner-driven lore, tournaments, spectator functionality and other player features are in development or testing.

## Why Reactive Network?

Reanimated Dead already recognizes blockchain ownership inside the game.

As supported assets, chains and player features expand, applications traditionally need to poll blockchain infrastructure to discover ownership or transaction changes and then determine whether something should happen inside the game.

The proposed Reactive integration tests a different model:

**relevant blockchain event → Reactive workflow → defined game/blockchain action**

Reactive Contracts will be used as an event-driven automation layer for selected ownership and competitive-reward workflows.

The goal is not to move Reanimated Dead's gameplay on-chain.

The goal is to use Reactive where event-driven blockchain automation provides a practical benefit.

## Proposed Integration

The initial scope includes three primary use cases.

### 1. Ownership Reconciliation

Reactive workflows will observe approved ownership-related events for selected supported assets.

When relevant ownership changes occur, the integration can initiate a predefined reconciliation workflow so Reanimated Dead can refresh or invalidate ownership-dependent benefits.

### 2. Competitive Rewards

Reanimated Dead remains authoritative for match and tournament results.

After the game establishes that a player is eligible for a supported competitive reward, the integration can initiate a bounded Reactive workflow associated with the corresponding blockchain action.

Reactive does not determine match winners.

### 3. Cross-Chain Event Coordination

The project will demonstrate an approved event originating from a supported EVM environment triggering a defined Reactive workflow used by Reanimated Dead.

This provides a practical gaming example of event-driven cross-chain automation.

## Proposed Architecture

At a high level:

Blockchain Event
      |
      v
Reactive Contract
      |
      v
Approved Reactive Workflow
      |
      v
Reanimated Dead Integration Adapter
      |
      v
Validation / Durable Job
      |
      v
Game or Blockchain Result

Reanimated Dead remains responsible for:

- Gameplay rules
- Competitive eligibility
- Player authentication
- Moderation
- Private player data
- Game entitlements
- Final player-facing behavior

Reactive handles the agreed event-driven blockchain automation.

## Reliability

Blockchain events and callbacks must not accidentally create duplicate game benefits or rewards.

The integration is therefore planned around:

- Explicit chain and contract allowlists
- Event identity tracking
- Durable workflow/action identifiers
- Idempotent processing
- Duplicate-event protection
- Retry-safe execution
- Delayed-event handling
- Failure reconciliation
- Bounded permissions
- Production instrumentation

A repeated observation or callback must not issue the same reward twice.

## Security Boundary

Reactive workflows will be intentionally narrow.

The integration will not allow arbitrary blockchain events to execute arbitrary game behavior.

Only approved:

- Networks
- Contracts
- Event types
- Workflow destinations
- Reward actions

will be recognized.

Signing and issuer permissions will use least-privilege roles.

The project will never request player seed phrases or private keys.

## Competitive Integration

Reanimated Dead is actively developing and testing tournament and spectator functionality.

The proposed Reactive integration will be demonstrated through a public competitive activation.

The game will determine competition results and eligibility.

Reactive will automate the agreed blockchain workflow after the authoritative game result has been established.

## Measurement

The production pilot will measure:

- Qualifying source events observed
- Reactive workflows initiated
- Successful resulting actions
- Duplicate/retry events
- Failed or pending workflows
- Recovery outcomes
- Event-to-action timing
- Ownership reconciliation behavior
- Competitive reward completion
- Relevant operating costs

Internal testing and retries will be separated from genuine player activity.

Existing Reanimated Dead user and engagement metrics will also remain separate from Reactive-specific adoption.

## Planned Public Components

Subject to final grant scope and technical review, this repository is intended to contain the separable Reactive components created through the proposed integration, including:

- Reactive Contracts
- Event subscription/filtering examples
- Reference integration adapter
- Workflow and entitlement interfaces
- Configuration examples
- Automated tests
- Failure/recovery examples
- Deployment documentation
- Technical implementation notes
- Production case-study findings

The goal is to give other developers a practical example of integrating Reactive's event-driven architecture with a conventional game backend.

## Open-Source Boundary

This repository is intended for the **separable Reactive-specific integration components** developed through the proposed project.

It is **not** the source repository for Reanimated Dead.

The following remain proprietary:

- Reanimated Dead core game source
- Characters and artwork
- Card designs and game content
- Proprietary gameplay systems
- Private backend systems
- Player/account data
- Commercial infrastructure
- Reanimated Dead brand and other commercial IP

The final public-source scope and license will follow the applicable grant agreement and third-party license requirements.

## Current Status

This repository was created in preparation for the proposed Reactive Network integration.

**No Reactive production deployment, partnership, endorsement or grant award is claimed at this time.**

Development artifacts, contracts, tests and documentation will be added if and as the proposed work proceeds.

## Team

### Joshua Kassabian
**Founder / Technical Lead**

Software architecture, game development, blockchain/payment integrations, production systems and technical delivery.

### Jeff Vongore
**Co-Founder / Creative & Product Lead**

Game/product development, art, collectibles, physical-product direction and distribution.

Joshua and Jeff have worked together for approximately four years across cryptocurrency, NFTs, digital products and Reanimated Dead.

## Links

**Play Reanimated Dead:**  
https://reanimateddead.com

**Reactive Network:**  
https://reactive.network

---

Reanimated Dead is an independent project. References to Reactive Network describe a proposed integration and should not be interpreted as an endorsement, partnership or grant award unless explicitly announced by the relevant parties.