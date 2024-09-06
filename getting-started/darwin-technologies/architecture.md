# Architecture

The Darwin platform is a state-of-the-art AI layer blockchain that integrates distributed AI inference capabilities, fostering a robust, scalable, and secure AI development and deployment environment. Built on an EVM-compatible blockchain, it allows seamless integration with Ethereum-based tools and infrastructures.

### **Key Components of the Darwin System**

<figure><img src="../../.gitbook/assets/Asset 1@300x (15).png" alt=""><figcaption><p>Darwin Technical Architecture</p></figcaption></figure>

Darwin's main architecture contains three different layers:

* [Data Layer](architecture.md#data-layer)
* [System Layer](architecture.md#system-layer)
* [Application Layer](architecture.md#application-layer)

#### Data Layer

The data layer is divided into two storage types:

* **Temporary Storage**: It is designed for high performance and utilized during training or inferencing phases.
* **Permanent Storage**: This is a more cost-effective solution for long-term data storage. Third-party services are employed for permanent storage to optimize costs.

#### System Layer

The main layer comprises of three key components: **Blockchain**, **Query Mixer**, and **AI Node**.

**a. Blockchain**

* **Stake Pool and Quota System**: Users stake $DNA tokens to gain access to AI inference quotas, which helps secure the network and enables decentralized governance.
* **Transaction Recording**: All transactions, whether AI-related or not, are permanently recorded on the blockchain.
* **Darwin Contracts**: These smart contracts facilitate the submission and validation of AI transactions, ensuring secure and compliant operations.
* **Gasless Transactions**: The system provides a gasless AI service using the "Approve-Once-Approaches-on-Call" method, delivering a smoother user experience.

**b. Query Mixer Network**

* **Optimization and Anonymization**: This component optimizes and anonymizes AI task processing, ensuring transparent and unbiased operations across distributed AI nodes.
* **Resource Allocation**: It efficiently allocates AI resources throughout the network, balancing the load and optimizing performance.

**c. Distributed AI Inference**

* **AI Nodes**: These form the backbone of the AI inference system, efficiently handling complex AI tasks.
* **SPECTER**: Darwin's zk-proof engine enhances privacy and security by generating zero-knowledge proofs for AI inferences.

#### Application Layer

The application layer includes the following components:

* **Token/Transaction Operations**: This covers operations related to tokens or transactions, including interactions through wallets and blockchain explorers.
* **DApps**: Decentralized applications like DeFi and AI-powered services.
* **AI Node Client**: Users can participate in the AI system through this client.

### System Roles and Interaction Flow

<figure><img src="../../.gitbook/assets/Asset 39@300x (2).png" alt=""><figcaption><p>System Roles and Interaction Flow</p></figcaption></figure>

The Darwin AI blockchain platform architecture integrates users, relayers, chain nodes, query mixers, and AI nodes into a cohesive system. These interactions are organized into three operational circles:&#x20;

* [Frontend on Chain](architecture.md#frontend-on-chain)
* [Backend on Chain](architecture.md#backend-on-chain)
* [Functioned AI](architecture.md#functioned-ai)

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

* Relayers is an API service that implements gasless functionality. It allows users to send AI transactions for free by paying with $DNA tokens.
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
