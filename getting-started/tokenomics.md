# Tokenomics

Darwin ecosystem is designed with an innovative tokenomics model and a gasless transaction approach to create a robust, decentralized AI marketplace. This article will delve into the core components of Darwin Chain's tokenomics, the roles of different participants, and how the gasless model works to provide a seamless user experience.

<figure><img src="../.gitbook/assets/Asset 2@300x (15).png" alt=""><figcaption><p>Darwin Tokenomics Principles</p></figcaption></figure>

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

### $ DNA Utility

There are three scenarios of **DNA** utility:&#x20;

#### 1. Consumption

* **Transaction Fee**
  * **Non-AI Transaction**: Gas fees paid in $DNA.
  * **AI Transaction**: Includes a Base Fee, which varies according to AI usage. The proposed protocol, similar to Ethereum's EIP-1559, defines an AI transaction as `Base Fee + Non-AI Transaction Fee + Priority Fee`.
* **Circulation of AI Computing Resources**
  * **Stake DNA for qDNA**: qDNA represents a daily or weekly quota for accessing AI resources, with a potential exchange ratio of 1 DNA to n qDNA.
  * **Stake to qDNA Swap**: Users can pay in USDT or DNA to acquire qDNA when they require additional computing resources. The swap acts as a market where qDNA has a price.
  * **Pay DNA for AI Usage**: Payment in DNA for AI usage follows a 1:m ratio. The DNA paid is burned. Typically, using qDNA is more cost-effective, but in extreme scenarios with high AI demand, users might prefer using DNA over qDNA.

{% hint style="info" %}
**Note**:

* qDNA is still TBD.
* The ratio of **Pay DNA for AI Usage** is subject to change, ideally lower than the qDNA ratio.
{% endhint %}

**2. Rewards**

* **AI Node Runner Rewards**
  * **32% of Total DNA**: This portion will be distributed to AI node runners over a specified number of years (TBD) .
* **Network Security Maintenance**
  * **Stake to Become a Validator**: Validators must stake at least 0.1‰ of the total DNA to maintain blockchain security. If 10% of the total DNA is staked, the APY is around 10%, keeping the inflation rate ideally between 1-1.5%. These proportions and APY are subject to change, but the inflation rate will remain within a narrow range.
  * **Stake to Become a Query Mixer**: To maintain AI node network security, a minimum stake of 1‰ is required. If 10% of the total DNA is staked, all 10 mixers will share 1% of the total DNA, resulting in a 10% APY.
  * **Support Decentralized Governance**: The amount of DNA required is TBD.

**3. Burn**

DNA will be burned in the following scenarios:

* **50% of Non-AI Transaction Fees**
* **100% of Base Fee in AI-related Transactions** (Priority fee is part of Validator rewards)
* **50% of qDNA Sold in the Swap**
* **100% of DNA Paid for AI Usage**

### Gasless Model

<figure><img src="../.gitbook/assets/Asset 21@300x (4).png" alt=""><figcaption><p>Gasless Model</p></figcaption></figure>

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
