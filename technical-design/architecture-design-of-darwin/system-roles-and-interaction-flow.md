# 🤹‍♀️ System Roles and Interaction Flow

### System Roles and Interaction Flow

The Darwin AI blockchain platform orchestrates a complex system of interactions involving users, relayers, chain nodes, query mixers, and AI nodes. These interactions are organized into three distinct operational circles: Frontend on Chain, Backend on Chain, and Functioned AI. Each circle plays a critical role in ensuring the seamless execution of AI tasks within the Darwin ecosystem. Below, we provide a detailed explanation of the roles and interactions within each circle.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>System Roles and Interaction Flow</p></figcaption></figure>

#### Circle 1: Frontend on Chain

**Users and Wallet Interaction:**

* Users interact with the Darwin blockchain using EVM-compatible wallets.
* They stake $DNA tokens to claim inference quotas, which allow them to submit AI transactions without direct cost.
* Transactions can be submitted directly or through a relayer to minimize gas fees, enhancing user experience and reducing operational costs.

**Relayer Role:**

* Relayers facilitate the gasless submission of transactions by bundling multiple user requests and forwarding them to the chain nodes.
* This system not only improves transaction efficiency but also reduces the cost burden on individual users.

#### Circle 2: Backend on Chain

**Chain Nodes:**

* Chain nodes are responsible for processing transactions received from users or relayers.
* They perform essential functions such as transaction verification, execution of smart contracts, and maintaining the integrity and security of the blockchain.

**Staking and Resource Allocation:**

* Chain nodes manage the staking and allocation of resources, ensuring that the network remains secure and that resources are distributed according to the network's needs.
* Wallet addresses linked to chain nodes are crucial for tracking stakes and allocating resources effectively within the ecosystem.

#### Circle 3: Functioned AI

**Query Mixer Operations:**

* The Query Mixer monitors on-chain events to ensure that AI transactions are processed correctly and securely.
* It randomly generates additional queries to validate AI transaction outputs, maintaining the integrity and accuracy of the inference results.

**AI Nodes and Real-time Inference:**

* AI nodes receive tasks and challenges from the Query Mixer, which they process to generate real-time AI inferences.
* These nodes stream the AI results back to users, providing a dynamic and responsive AI service.

**Incentives and Verification:**

* AI nodes must stake $DNA tokens to participate in the network, ensuring their commitment and reliability.
* The Query Mixer also stakes tokens to ensure its operation within trusted parameters, enforced by the Darwin community and managed within a Trusted Execution Environment (TEE).
* Verifiable Random Functions (VRF) are used by the Query Mixer to perform random checks on AI nodes, assessing factors such as online status, model accuracy, and latency. Nodes that fail these checks may face penalties or removal from the network to maintain high operational standards.

#### Interaction Dynamics

* The staked quotas from users are partly allocated to AI nodes by the Query Mixer, rewarding nodes for their computational contributions.
* All participants, including Query Mixers and AI Nodes, undergo registration and must stake $DNA tokens. This staking is essential for participating in the network and for the allocation of computational tasks.
* Continuous online monitoring and the potential for penalties ensure that all nodes adhere to the network's operational standards, fostering a robust and reliable AI processing environment.

This section clarifies how each component of the Darwin ecosystem interacts within the broader architecture, ensuring a secure, efficient, and user-friendly AI blockchain platform. The structure supports a scalable and economically viable environment conducive to widespread AI and blockchain integration.
