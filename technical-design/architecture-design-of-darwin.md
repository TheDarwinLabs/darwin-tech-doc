# Architecture Design of Darwin

### Overview

The Darwin platform is a state-of-the-art L1 blockchain that integrates distributed AI inference capabilities, fostering a robust, scalable, and secure environment for AI development and deployment. Built on an EVM-compatible blockchain, it allows seamless integration with Ethereum-based tools and infrastructures.

### **Key Components of the Darwin System**

<figure><img src="../.gitbook/assets/darwin flow 2 (1).gif" alt=""><figcaption><p>Darwin Technical Architecture</p></figcaption></figure>

1. **Darwin Chain:**
   * **Tokenomics and $DNA Production:** $DNA tokens are minted with each block, driving the ecosystem's incentives and governance.
   * **Stake Pool and Quota System:** Users stake $DNA tokens to access AI inference quotas, securing the network and enabling decentralized governance.
   * **Darwin Contracts:** Smart contracts facilitate AI transaction submissions and validations, ensuring secure and rule-compliant operations.
2. **User Interface and Relayer Mechanism:**
   * **Rich Frontend:** An intuitive user interface supports wallet integrations and advanced features like homomorphic encryption for enhanced privacy and security.
   * **Relayer:** Enables [gasless transaction mechanism](darwin-tokenomics-and-gasless-model.md), managing the complexities of transaction submission and execution on behalf of the user.&#x20;
3. [**Query Mixer**](../key-technologies/query-mixer-lfg-gm.md) **and Orchestrator:**
   * **Query Mixer:** Optimizes and anonymizes AI task processing, ensuring transparency and unbiased operation of distributed AI nodes.
   * **Orchestrator:** Efficiently allocates AI resources across the network, balancing load and optimizing performance.
4. [**Distributed AI Inference**](../key-technologies/darwin-distributed-inference.md)**:**
   * **AI Nodes:** Form the backbone of the AI inference system, processing complex AI tasks efficiently.
   * [**SPECTER**](../key-technologies/darwin-specter/)**:** Darwin’s zk-proof engine enhances privacy and security by generating zero-knowledge proofs for AI inferences.
5. **Data Availability (DA) Providers:**
   * **Model Data and User-Encrypted Data:** Manage storage and availability of essential data for secure AI model execution.
   * **Storage Solutions:** Utilize decentralized storage solutions like IPFS and Swarm to ensure data reliability and accessibility.

### System Roles and Interaction Flow

<figure><img src="../.gitbook/assets/darwin flow 3 (2).gif" alt=""><figcaption></figcaption></figure>

The Darwin AI blockchain platform architecture integrates users, relayers, chain nodes, query mixers, and AI nodes into a cohesive system. These interactions are organized into three operational circles:&#x20;

* Frontend on Chain
* Backend on Chain
* Functioned AI

{% hint style="info" %}
**Note**:

Each circle plays a vital role in the platform's AI task execution.
{% endhint %}

#### Frontend on Chain

**Users and Wallet Interaction:**

* Users interact with the blockchain via EVM-compatible wallets.
* They stake $DNA tokens for inference quotas to submit AI transactions without direct cost.
* Transactions can be submitted directly or through relayers to reduce gas fees.

**Relayers:**

* Relayers is an API service that implements gasless functionality, allowing users to send AI transactions for free by paying with $DNA tokens.
* Relayers bundle multiple user requests and forward them to chain nodes, facilitating gasless transactions and reducing user costs.

#### Backend on Chain

**Chain Nodes:**

* Process transactions from users or relayers.
* Handle transaction verification, smart contract execution, and maintain blockchain security.

**Staking and Resource Allocation:**

* Manage staking and resource allocation to ensure network security and resource distribution.
* Wallet addresses linked to chain nodes track stakes and resource allocation.

#### Functioned AI

**Query Mixer Operations:**

* Monitors on-chain events to process AI transactions securely.
* Generates additional queries to validate AI transaction outputs.

**AI Nodes and Real-time Inference:**

* AI nodes process tasks from the Query Mixer to generate real-time AI inferences.
* Results are streamed back to users for a responsive AI service.

**Incentives and Verification:**

* AI nodes and the Query Mixer stake $DNA tokens to ensure commitment and reliability.
* Verifiable Random Functions (VRF) perform random checks on AI nodes for model accuracy and latency, enforcing high operational standards.

**Interaction Dynamics**

* Staked quotas from users are allocated to AI nodes by the Query Mixer as rewards.
* All participants must register and stake $DNA tokens to participate and receive tasks.
* Continuous monitoring and penalties ensure adherence to operational standards, maintaining a robust AI processing environment.

This structure ensures a secure, efficient, and user-friendly AI blockchain platform, supporting scalable and economically viable AI and blockchain integration.
