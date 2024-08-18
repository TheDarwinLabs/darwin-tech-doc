# Gasless

Gasless is a core innovation in Darwin, designed to reduce gas fees associated with AI services. The goal of Gasless is straightforward: to minimize gas fees as much as possible.

### System Design

In Darwin, there are two types of gas:&#x20;

* **Non-AI Gas**: This is used for standard transactions like on other blockchains
* **AI-related Gas**: This is required to access computing resources.&#x20;

To manage this, qDNA is introduced as a voucher that allows users to redeem these resources.

<figure><img src="../../.gitbook/assets/flow 1.png" alt=""><figcaption><p>Stake for Quota</p></figcaption></figure>

Here is how the Gasless design works:

1. **Generating qDNA**: There are two ways to acquire qDNA. Users can stake DNA in a qDNA pool to access AI resources exclusively for themselves or stake in the qDNASwap, a marketplace where others can purchase qDNA using USDT or DNA. A portion of the USDT profits from qDNASwap is distributed to stakers, while the rest is used to buy back and burn DNA.
2. **Redeeming AI Services**: Users redeem AI services by spending qDNA, which is then burned.
3. **Accumulation of qDNA**: When DNA is staked in the qDNA pool, qDNA accumulates in the user’s wallet at a fixed rate, taking 24 hours to reach its maximum limit. If the user consumes qDNA for AI services, the qDNA balance decreases, and the refill process begins again at the same rate. This also applies to qDNASwap, where the accumulated qDNA is available for others to purchase.
4. **qDNA Restrictions**: qDNA in a user’s wallet cannot be sold or transferred. It only functions as a voucher for AI services. If a wallet holds qDNA from both staking and purchases, the system will prioritize consuming qDNA obtained through staking first.
5. **Burn Mechanism**: When DNA is withdrawn from the qDNA pool, the corresponding qDNA is burned in proportion to the withdrawal.

### Approve-Once, Approach on Call

When AI services are invoked on-chain, they trigger an AI-related transaction that requires user authorization through their wallet. Frequent AI requests would require repeated authorizations, which can be inconvenient. The "Approve-Once, Approach on Call" solution is introduced to address this.

<figure><img src="../../.gitbook/assets/flow 2 (1).png" alt=""><figcaption><p>Runtime</p></figcaption></figure>

This feature allows a user’s approval to cover both their DNA and qDNA staked in the protocol, making the authorization valid for a set period. Users can cancel their approval at any time. Darwin compensates for the transaction gas involved in this gasless process.

### Non-AI Transaction Fees

Non-AI on-chain transaction fees in Darwin are relatively low but are not exempt from gas charges. A design plan for managing these fees will be implemented in the future.
