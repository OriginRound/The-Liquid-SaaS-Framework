# The Liquid SaaS Framework

The Liquid SaaS Framework is an open methodology and architectural standard for software distribution. It is designed to replace high-fee marketplace platforms and the traditional "Lifetime Deal" (LTD) model with a sustainable, 0% platform-fee, transferable asset system.

This framework was designed to give early-stage and scaling founders 100% control over their revenue, licensing mathematics, and user relationships.

## The Problem: The Broken Distribution Model
Currently, software founders seeking early traction are often forced into a mathematically parasitic trap:

**The "LTD Death Spiral" (Marketplaces):** Founders use heavy-discount marketplaces to gain early cash flow, giving up to 70% of their revenue to the platform. They receive a fraction of the capital but inherit a massive user base that demands permanent customer support and will never pay them another dime. You aren't building a sustainable business; you are building a liability.

## The Solution: Liquid Software Assets
The Liquid SaaS Framework solves this by treating software seats like physical inventory and utilizing a **Zero-Trust Entitlement Engine** rather than a traditional marketplace. 

By separating the billing layer from the access layer, founders can turn standard software licenses into secure, tradeable digital assets.

### Core Architecture & Rules

#### 1. Asset Typology
Every software seat generated under this framework belongs to one of two classes:
*   **Soulbound:** A strict 1-to-1 license. The millisecond it is claimed, it is permanently locked to that specific user identity.
*   **Transferable (Liquid SaaS):** The core innovation. An asset held in an "Unconsumed" state within a digital vault. Users pay the recurring subscription strictly to maintain ownership of the asset.

#### 2. Transferable Assets (SaaS "Domain Flipping")
Instead of offering rigid lifetime deals that drain support queues, founders issue standard subscriptions where the license is *transferable*. 
* Users can buy a subscription at an early-bird rate and hold it. 
* They pay the recurring subscription to maintain ownership. 
* If they no longer need it, they can resell or "flip" the active license to a new user. The new user assumes the billing directly. 
* This turns early deal hunters and influencers into a secondary sales network, keeping brand value premium.

#### 3. The Unconsumed Transfer Rule
To prevent license abuse, piracy, or unauthorized sharing of active seats, the framework dictates that an asset can only be flipped or transferred to a new owner if it remains strictly **unconsumed**. This breaks the cycle of multiple users trying to illegally share a single active license.

#### 4. Deal Continuity: Inheritance vs. Forfeit
When an unconsumed asset with an introductory discount is transferred on the secondary market, the framework applies strict continuity rules:
*   **Inheritance:** The new owner inherits the remaining time of the discount before the subscription auto-escalates to the market price. (Optimized for secondary market liquidity).
*   **Forfeit:** The early-bird discount is instantly stripped upon transfer. The new owner must assume the subscription at the full market rate. (Optimized for protecting founder MRR).

#### 5. B2B Sponsorship & Gifting
The architecture separates the billing entity from the consuming entity. One person (Owner A) can buy and pay for the plan, while someone else (Owner B) actually consumes the seat. This enables frictionless enterprise sales, agency handoffs, and influencer gifting. If a sponsor cancels, the asset remains liquid for the next user to take over billing.

#### 6. The Flat-Fee Inventory Model (0% Platform Tax)
Founders bypass marketplace taxes completely. By connecting a direct payment gateway, founders pay a tiny, flat upfront fee to "create" the secure license connection. From Month 2 to infinity, the founder keeps **100% of the recurring revenue**.

---

## Technical Implementation (The Logic Layer)

Implementing The Liquid SaaS Framework requires an access control layer that keeps developers compliant with their direct payment processors. 

### Zero-Trust Validation & JIT Cryptography
You do not rely on vulnerable local client checks. Cryptographic spoof-prevention happens entirely server-side. Claim codes are generated **Just-In-Time (JIT)** and remain completely hidden until the exact millisecond the buyer breaks the seal to claim the software.

### Dual Identifiers
To safely facilitate a secondary market, the framework requires two distinct identifiers for every asset:
1.  **The Public Reference (`ref`):** A safe, read-only ID used for background database syncs, CRON jobs, and public check-pages (allowing secondary buyers to mathematically verify an asset exists without exposing the key).
2.  **The Secret Code (`code`):** The cryptographic key used strictly for user consumption and unlocking access.

### Programmable Metadata & API Simplicity
The entire licensing infrastructure revolves around two primary master flags to dictate access:
* `is_valid`
* `already_in_use`

```json
{
  "is_valid": true,
  "already_in_use": false,
  "metadata": { "license_tier": "pro", "max_workspaces": 3 }
}
```
While 99% of pricing plans (subscriptions, one-time access, timed passes) are covered by this baseline, the framework achieves 100% coverage via **optional, programmable metadata** (`custom_metadata`). This allows founders to inject payloads that instantly assign Discord roles, SaaS tiers, or API credits upon claim-building bespoke distribution models that sell while they sleep.

---

## Reference Implementation
This methodology is open for the developer community to debate, use, and implement. 

The first technical validation engine and distribution hub built entirely on this framework is **OriginRound**. 

* **Main Engine:** [https://originround.com](https://originround.com)
* **Deal Architect Simulator:** [https://originround.com/dealarchitect](https://originround.com/dealarchitect)
* **Raw API & Framework Specs:** [https://originround.com/llms-full.txt](https://originround.com/llms-full.txt)

> ## Join the Standard
> We invite developers and founders to debate, refine, and build upon this framework. Open an Issue or start a Discussion in this repository to contribute to the future of liquid software assets.

***
*© 2026 OriginRound - The Liquid SaaS Framework is an open methodology for the developer community.*
