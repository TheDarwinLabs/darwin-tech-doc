# 🪙 Darwin Tokenomics and Gasless Model

The Darwin AI blockchain system employs a sophisticated tokenomics model centered around three primary tokens: $DNA, $sDNA, and $qDNA. Each token plays a crucial role in incentivizing network participation, aligning the interests of different stakeholders, and facilitating a robust, decentralized AI marketplace. Our model ensures sustainable network activity, stimulates ecosystem growth, and increases the intrinsic value of staked tokens through positive feedback loops.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>Darwin Tokenomics Principles</p></figcaption></figure>

#### Token Descriptions

1. **$DNA (Native Token):**
   * Serves as the primary economic unit within the Darwin ecosystem, used for staking, governance, and transactions. Users stake $DNA to participate in network governance, secure transaction quotas, and earn rewards.
2. **$sDNA (Stake DNA):**
   * **Obtained By:** Staking $DNA tokens. For every $DNA staked, an equivalent amount of $sDNA is issued to the staker.
   * **Utility:** Represents the staking contribution of users. $sDNA holders earn proportional rewards from network fees and airdrops.
   * **Redemption and Burn:** $sDNA is burned when its corresponding $DNA is unstaked and reclaimed.
3. **$qDNA (Quota DNA):**
   * **Obtained By:** Staking $DNA with an annual percentage yield (APY) generating a steady release of $qDNA over time. Also purchasable on secondary markets or obtainable through delegated staking.
   * **Utility:** Used to pay for AI transaction gas fees on the network. Holding $qDNA enables users to submit AI transactions via Relayers effectively at no direct cost by consuming $qDNA instead of $DNA.
   * **Burn Mechanism:** $qDNA is burned when used to pay for AI transaction gas fees, ensuring a deflationary pressure that adds value to the token.

#### Incentive Structures

* **Developers and dApp creators:** Encouraged to build on Darwin by staking $DNA to receive computation quotas and deploy AI-native applications, fostering a diverse range of services and enhancing platform utility.
* **Compute Providers and Orchestrators:** Rewarded for hosting AI models and executing computations. Their earnings are tied to the computational resources provided, enhancing network capacity and reliability.
* **Model Providers:** Compensated for contributing AI models to the ecosystem. This incentivizes the continuous enhancement of available AI solutions and broadens the spectrum of applications.

#### Gasless Model

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>Gasless Model</p></figcaption></figure>

The Gasless model aims to reduce the barrier to entry for using AI services on the blockchain by mitigating transaction costs for end-users.

**Process:**

1. **Staking and Token Conversion:**
   * Users stake $DNA to obtain $sDNA and earn $qDNA through a defined APY. The $qDNA serves as a specific token to offset the gas costs traditionally associated with blockchain transactions.
2. **AI Transaction Submission:**
   * Users initiate AI transactions signed with their credentials and send them to a Relayer.
   * The Relayer verifies the user's signature and $qDNA balance.
   * If the user has sufficient $qDNA, the Relayer submits the AI transaction to the network, consuming $qDNA as gas.
3. **Reward Distribution:**
   * The consumed $DNA (converted from $qDNA used as gas) is distributed as rewards to the Query Mixers and AI Oracles, incentivizing them to process and validate AI tasks efficiently.

#### Token Dynamics

The token dynamics within the Darwin ecosystem can be represented by the following equations:

1. **$qDNA Generation Formula:**

The generation of $qDNA tokens from staked $DNA is determined by a predefined APY (Annual Percentage Yield), reflecting a continuous release model:

$$\text{Annual qDNA Generation} = \text{Staked DNA} \times \text{APY}_{\text{qDNA}}$$

Where $$\text{APY}_{\text{qDNA}}$$ is the annual percentage yield for $qDNA generation based on the total staked $DNA.

2. **$sDNA Reward Distribution Formula:**

$sDNA holders receive rewards based on the proportion of their holdings relative to the total $sDNA in circulation. The rewards are derived from the network's collected fees and distributed proportionally:

$$\text{Reward}_{\text{sDNA}} = \left( \frac{\text{sDNA held by User}}{\text{Total sDNA in Circulation}} \right) \times \text{Total Collected Fees}$$

This formula ensures that the rewards are equitably distributed among $sDNA holders based on their stake in the network.

3. **$qDNA Consumption (Burn Rate) for Transactions:**

The rate at which $qDNA is consumed (or burned) is tied directly to its use in transaction fee payments, creating a deflationary mechanism that adds to the token's value:

$$\text{Burn Rate}_{\text{qDNA}} = \text{Number of AI Transactions} \times \text{qDNA per Transaction}$$

Each AI transaction consumes a certain amount of $qDNA as gas, and this consumption is permanently removed from the circulation, enhancing the scarcity and potential value of the remaining $qDNA tokens.



The Darwin AI blockchain's tokenomics and gasless model are designed to promote a thriving decentralized AI market. By reducing transaction costs and aligning incentives across various network participants, Darwin fosters widespread adoption and continuous innovation, ensuring the platform remains at the forefront of decentralized AI technology.
