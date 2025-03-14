---
**title:** Initial Coin Offering (ICO) and Fund Allocation for Fushuma Treasury DAO  
**description:** Defines the Initial Coin Offering (ICO) structure for the Fushuma Network’s token sale and the allocation of raised funds into the Treasury DAO mechanism.  
**author:** "@Dr-ZS"  
**type:** Review  
**created:** 2025-03-14  
---

## Abstract

Fushuma Improvement Proposal 3 (FIP-3) outlines the Initial Coin Offering (ICO) structure for the Fushuma Network’s token sale and specifies the allocation of raised funds into the Treasury DAO mechanism established in FIP-1. The ICO will raise capital through a tiered sale of FUMA tokens, with funds split into two pools: (i) 65% to the Liquidity Reserve Pool and (ii) 35% to the Development Pool. The completion of this offline phase will define the parameters for launching the eXponential Bonding Curve (XBC) mechanism described in FIP-1.

## Motivation

The Fushuma Network aims to establish a decentralized, self-sustaining ecosystem through its Treasury DAO mechanism, as introduced in FIP-1. The ICO phase is critical to (i) bootstrap initial liquidity, (ii) build trust among early investors, and (iii) provide the financial stability for the ecosystem. This proposal formalizes the ICO process, integrates the raised funds into the eXponential Bonding Curve (XBC) mechanism, and ensures transparent allocation to support liquidity and ecosystem growth. The 65%/35% split between the Liquidity Reserve Pool and Development Pool balances long-term stability with continuous development, while the XBC parameters, set post-ICO, reflect real financial conditions.

## Specification

### ICO Structure

The ICO will occur during an offline phase to gather initial liquidity for the Fushuma Network. It consists of two tiered sale rounds with fixed token prices and amounts, as follows:

| Phase       | Amount (FUMA) | Price (USD) | USD Raised |
|-------------|---------------|-------------|------------|
| ICO Round 1 | 75,000,000    | 0.0015      | 112,500    |
| ICO Round 2 | 60,000,000    | 0.0020      | 120,000    |
| **Total**   | **135,000,000** |             | **232,500** |

- **Total Tokens Sold:** 135,000,000 FUMA  
- **Total Funds Raised:** $232,500 USD (maximum target)  
- **Token Distribution:** Tokens will be minted and distributed to buyers at the specified prices per round.

### Transition to XBC Mechanism

Upon completion of the ICO, the offline phase will conclude, and the Fushuma Network will transition to the online phase. The XBC mechanism, an evolution of the Quadratic Bonding Curve (QBC) described in FIP-1, will be initialized with parameters derived from the ICO’s total funds raised and token supply, ensuring accurate price discovery and liquidity management.

### Fund Allocation

The funds raised (denoted as `Total_USD_raised`), targeting a maximum of $232,500 USD, will be allocated to the two Treasury DAO pools based on the total amount collected:

1. **Liquidity Reserve Pool:**  
   - **Amount:** 65% of `Total_USD_raised`  
     - Formula: `0.65 * Total_USD_raised`  
     - Example: If $232,500 is raised, `0.65 * 232,500 = $151,125`  
   - **Purpose:** Provides a reserve for token liquidity withdrawals, ensuring continuous liquidity in the online phase and supporting investor confidence and market stability.

2. **Development Pool:**  
   - **Amount:** 35% of `Total_USD_raised`  
     - Formula: `0.35 * Total_USD_raised`  
     - Example: If $232,500 is raised, `0.35 * 232,500 = $81,375`  
   - **Purpose:** Finances ecosystem growth through grants for projects, approved via DAO governance, fostering innovation and sustainability.

The exact amounts will scale proportionally based on the total funds raised, ensuring flexibility if the maximum target is not met.

### Implementation Details

#### Smart Contracts

The ICO will utilize smart contracts to manage token distribution during the offline phase. The following functions will be implemented:

1. **`Buy(amount_to_pay)`**  
   - **Description:** Allows users to pay USDT and receive locked FUMA tokens.  
   - **Formula:** `amountOfFuma = amount_to_pay / price_per_round` (where `price_per_round` is 0.0015 USD for Round 1 or 0.0020 USD for Round 2).  
   - **Fee:** No buy fee applied unless specified in future FIPs.  
   - **Locking:** Tokens are locked until the online phase begins.

2. **`Sell(amountOfFuma)`**  
   - **Description:** Allows users to sell locked FUMA tokens for USDT during the online phase (post-ICO).  
   - **Formula:** To be defined by the XBC mechanism in subsequent FIPs.  
   - **Fee:** No sales fee applied unless specified in future FIPs.

3. **`Claim(amountOfFuma)`**  
   - **Description:** Allows users to claim locked FUMA tokens after the transition to the online phase.  
   - **Fee:** No claim fee applied unless specified in future FIPs.

## Rationale

The ICO structure and fund allocation provide a transparent and efficient method to bootstrap the Fushuma Network. The tiered sale incentivizes early participation, while the 65%/35% split ensures liquidity for investors and sustained funding for ecosystem growth. The transition to the XBC mechanism post-ICO builds on FIP-1’s vision, enhancing price stability and scalability through dynamic token pricing.

## Exact Mathematical Model, Parameter Selection, and Implementation

The precise XBC parameters, including curve steepness and initial reserve ratios, will be defined in subsequent FIPs based on the ICO’s outcome. Technical specifications for smart contract deployment will also follow.

## Conclusion

FIP-3 establishes the foundation for the Fushuma Network by formalizing the ICO process and integrating raised funds into the Treasury DAO mechanism. This proposal enhances the long-term growth and success of the Fushuma ecosystem.
