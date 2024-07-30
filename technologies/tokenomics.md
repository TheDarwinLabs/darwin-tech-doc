# Tokenomics

Darwin Chain's blockchain ecosystem is designed with an innovative tokenomics model and a gasless transaction approach to create a robust, decentralized AI marketplace. This article will delve into the core components of Darwin Chain's tokenomics, the roles of different participants, and how the gasless model works to provide a seamless user experience.

<figure><img src="../.gitbook/assets/Asset 23@300x (7).png" alt=""><figcaption><p>Darwin Tokenomics Principles</p></figcaption></figure>

### Tokenomics Model

#### Tokens and Their Functions

Darwin Chain utilizes three primary tokens: **$DNA**, **$sDNA**, and **$qDNA**, each serving specific purposes within the ecosystem:

1. **$DNA (Native Token):**
   * **Purpose:** Serves as the primary economic unit.
   * **Usage:** Staking, governance, and transactions.
   * **Rewards:** Users stake $DNA to participate in network governance, secure transaction quotas, and earn rewards.
2. **$sDNA (Stake DNA):**
   * **Obtained By:** Staking $DNA tokens.
   * **Utility:** Represents staking contribution, earning rewards from network fees and airdrops.
   * **Redemption:** Burned when corresponding $DNA is unstaked and reclaimed.
3. **$qDNA (Quota DNA):**
   * **Obtained By:** Staking $DNA with APY, purchasable on secondary markets, or through delegated staking.
   * **Utility:** Used to pay for AI transaction gas fees.&#x20;
   * **Burn Mechanism:** Burned when used for transaction fees, creating a deflationary pressure that adds value.

{% hint style="info" %}
**Note**:

Holding $qDNA enables users to submit AI transactions via Relayers effectively at no direct cost by consuming $qDNA instead of $DNA.
{% endhint %}

#### Incentive Structures

The tokenomics model ensures that various network participants are rewarded appropriately:

* **Developers and dApp creators:** Encouraged to build on Darwin by staking $DNA to receive computation quotas and deploy AI-native applications, fostering a diverse range of services and enhancing platform utility.
* **Compute Providers and Orchestrators:** Rewarded for hosting AI models and executing computations. Their earnings are tied to the computational resources provided, enhancing network capacity and reliability.
* **Model Providers:** Compensated for contributing AI models to the ecosystem. This incentivizes the continuous enhancement of available AI solutions and broadens the spectrum of applications.

### Gasless Model

<figure><img src="../.gitbook/assets/darwin flow 4.gif" alt=""><figcaption><p>Gasless Model</p></figcaption></figure>

The gasless model is designed to reduce barriers to entry by eliminating transaction costs for end-users.

**Process:**

1. **Staking and Token Conversion:**
   * Users stake $DNA to obtain $sDNA and earn $qDNA through APY.
   * $qDNA offsets traditional gas costs.
2. **AI Transaction Submission:**
   * Users initiate AI transactions signed with their credentials and send them to a Relayer.
   * The Relayer verifies the user's signature and $qDNA balance.
   * The Relayer submits the transaction if sufficient $qDNA is available, consuming $qDNA as gas.
3. **Reward Distribution:**
   * Consumed $DNA (converted from $qDNA) is distributed as rewards to Query Mixers and AI Oracles.

#### Token Dynamics

The following equations can represent the token dynamics within the Darwin ecosystem:

1. **$qDNA Generation Formula:**

The generation of $qDNA tokens from staked $DNA is determined by a predefined APY (Annual Percentage Yield), reflecting a continuous release model:

$$\text{Annual qDNA Generation} = \text{Staked DNA} \times \text{APY}_{\text{qDNA}}$$

{% hint style="info" %}
**Note**:

$$\text{APY}_{\text{qDNA}}$$ is the annual percentage yield for $qDNA generation based on the total staked $DNA.
{% endhint %}

2. **$sDNA Reward Distribution Formula:**

$sDNA holders receive rewards based on the proportion of their holdings relative to the total $sDNA in circulation. The rewards are derived from the network's collected fees and distributed proportionally:

$$\text{Reward}_{\text{sDNA}} = \left( \frac{\text{sDNA held by User}}{\text{Total sDNA in Circulation}} \right) \times \text{Total Collected Fees}$$

{% hint style="info" %}
**Note**:

This formula ensures that the rewards are equitably distributed among $sDNA holders based on their stake in the network.
{% endhint %}

3. **$qDNA Consumption (Burn Rate) for Transactions:**

The rate at which $qDNA is consumed (or burned) is tied directly to its use in transaction fee payments, creating a deflationary mechanism that adds to the token's value:

$$\text{Burn Rate}_{\text{qDNA}} = \text{Number of AI Transactions} \times \text{qDNA per Transaction}$$

{% hint style="info" %}
**Note**:

Each AI transaction uses a certain amount of $qDNA as a fee, permanently removing it from circulation and increasing the remaining tokens' scarcity and potential value.
{% endhint %}

### Feedback Loops

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p>Tokenomics Feedback Loops</p></figcaption></figure>

Darwin Chain's tokenomics and gasless transaction model enable wider model coverage, more AI-native dApps, and ecosystem growth with additional models and improved governance. Increased support from developers, orchestrators, and compute nodes boosts the value of staked tokens, enhancing AI inference usage and raising the demand for $DNA.
