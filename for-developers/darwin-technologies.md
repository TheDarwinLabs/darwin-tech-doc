# Darwin Technologies

Explore Darwin Technologies through three main areas: our modern architecture, blockchain system with clear tokenomics, and verifiable AI inference technology.

Dive into each section to understand how we combine these elements to drive innovation and deliver powerful solutions.



### Architecture

### Overview

The Darwin platform is a state-of-the-art L1 blockchain that integrates distributed AI inference capabilities, fostering a robust, scalable, and secure environment for AI development and deployment. Built on an EVM-compatible blockchain, it allows seamless integration with Ethereum-based tools and infrastructures.

### **Key Components of the Darwin System**

<figure><img src="../.gitbook/assets/Asset 38@300x (1).png" alt=""><figcaption><p>Darwin Technical Architecture</p></figcaption></figure>

1. **Darwin Chain:**
   * **Tokenomics and $DNA Production:** $DNA tokens are minted with each block, driving the ecosystem's incentives and governance.
   * **Stake Pool and Quota System:** Users stake $DNA tokens to access AI inference quotas, securing the network and enabling decentralized governance.
   * **Darwin Contracts:** Smart contracts facilitate AI transaction submissions and validations, ensuring secure and rule-compliant operations.
2. **User Interface and Relayer Mechanism:**
   * **Rich Frontend:** An intuitive user interface supports wallet integrations and advanced features like homomorphic encryption for enhanced privacy and security.
   * **Relayer:** Enables [gasless transaction mechanism](tokenomics.md), managing the complexities of transaction submission and execution on behalf of the user.&#x20;
3. [**Query Mixer**](broken-reference) **and Orchestrator:**
   * **Query Mixer:** Optimizes and anonymizes AI task processing, ensuring transparency and unbiased operation of distributed AI nodes.
   * **Orchestrator:** Efficiently allocates AI resources across the network, balancing load and optimizing performance.
4. [**Distributed AI Inference**](broken-reference)**:**
   * **AI Nodes:** Form the backbone of the AI inference system, processing complex AI tasks efficiently.
   * [**SPECTER**](broken-reference)**:** Darwin’s zk-proof engine enhances privacy and security by generating zero-knowledge proofs for AI inferences.
5. **Data Availability (DA) Providers:**
   * **Model Data and User-Encrypted Data:** Manage storage and availability of essential data for secure AI model execution.
   * **Storage Solutions:** Utilize decentralized storage solutions like IPFS and Swarm to ensure data reliability and accessibility.

### System Roles and Interaction Flow

<figure><img src="../.gitbook/assets/Asset 39@300x (2).png" alt=""><figcaption><p>System Roles and Interaction Flow</p></figcaption></figure>

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





### Game-Theoretic Mixer

The Query Mixer is a key part of the Darwin AI blockchain platform, designed to ensure the authenticity and integrity of AI inferences across distributed networks. It tackles inference validation with Probabilistic Query Mixing, blending real user queries with special challenge queries to ensure nodes process requests honestly. Using our proprietary LLM instructional fingerprint, the system outputs consistent results for specific queries, leveraging a game-theoretic approach to prevent cheating and guarantee honest behavior by inference nodes.

### Key Features

* **Collusion Prevention**: The system prevents cheating and collusion by rerouting queries through multiple nodes and adding mixing layers. Each step is transparently recorded on-chain, deterring nodes from dishonest behavior because they risk losing their staked crypto assets.
* **Enhanced Security**: The combined mechanisms of mixing and slashing ensure that inference nodes perform correctly, as challenge query responses are checked against expected answers.
* **Efficiency and Reliability**: The Query Mixer operates swiftly and reliably, maintaining the accuracy and honesty of AI inferences.



### Game-Theoretic Mixer Validation Protocol

<figure><img src="../.gitbook/assets/Asset 32@300x (4).png" alt=""><figcaption><p>Game-Theoretic Mixer Flow</p></figcaption></figure>

1. **Pre-computation**: Special challenge queries are created using known responses to form a deterministic model fingerprint.
2. **Query Submission**: Users send their queries to the Mixer, which initiates the mixing process.
3. **Query Distribution**:&#x20;
   * Queries, including user and challenge queries, circulate within the Mixer network for node signatures.
   * Challenge queries are crafted using instructional fingerprinting, which involves fine-tuning a Language Model (LLM) on a meticulously curated dataset of instruction pairs $$(x_i, y_i)$$.
   * The model is engineered to respond to a query $$x_i$$ with a predefined answer $$y_i$$, creating a set of query-answer pairs that serve as the model’s fingerprints.
   * These fingerprints are used as challenges within the query batches sent to inference nodes, serving as benchmarks to validate the node's output.
4.  **Probabilistic Mixing**: Real user queries are mixed with challenge queries, creating batches where the origin of each query (user or challenge) is indiscernible to the inference nodes.

    Mixer nodes combine user and challenge queries and forward the batch to the Inference Node.
5. **Model Execution**: The Inference Node processes all queries in the batch, treating them as indistinguishable.
6. **Verification**: Mixers verify responses to challenge queries, recording the query paths on the blockchain for transparency and ensuring nodes' honest performance.

### Test Passing Probability Calculation

This section explains calculating the probability of a node passing a series of challenges within an epoch using a Poisson distribution. Given a fixed challenge emission rate, it factors in challenge difficulty and the threshold for node slashing.

#### Poisson Distribution

The number of challenges a node receives in an epoch is modeled using a Poisson distribution:

$$
Pois(\lambda, k) = \frac{\lambda^k e^{-\lambda}}{k!}
$$

Where:

* $$\lambda$$ is the fixed challenge emission rate, representing the average number of challenges a node receives in an epoch.
* $$k$$ is the number of challenges.

#### Single Challenge Pass Probability

The probability that a cheating node passes a single challenge is denoted by $$\tau$$. For example, for fingerprinting, this probability will be close to 0.

#### Threshold for Slashing

The threshold $$\alpha$$ is the number of failed challenges after which a node will be slashed.

#### Test Passing Probability Calculation

The probability $$P$$ that a node passes the challenges is computed using the following formula:

$$
P = \sum_{k < \alpha} \frac{\lambda^k e^{-\lambda}}{k!} + \sum_{k \geq \alpha} \sum_{j < \alpha} \frac{\lambda^k e^{-\lambda}}{k!} \binom{k}{j} (1-\tau)^j \tau^{k-j}
$$

Where:

* $$\sum_{k < \alpha} \frac{\lambda^k e^{-\lambda}}{k!}$$ is the probability that the node receives fewer than $$\alpha$$ challenges.
* $$\sum_{k \geq \alpha} \sum_{j < \alpha} \frac{\lambda^k e^{-\lambda}}{k!} \binom{k}{j} (1-\tau)^j \tau^{k-j}$$ is the probability that the node receives $$\alpha$$ or more challenges but passes enough of them to avoid being slashed.

#### Variables

| Variable    | Description                                                                           |
| ----------- | ------------------------------------------------------------------------------------- |
| $$\lambda$$ | The fixed challenge emission rate.                                                    |
| $$\tau$$    | The probability that a cheating node passes a single challenge.                       |
| $$\alpha$$  | The threshold number of failed challenges after which a node will be slashed.         |
| $$k$$       | The number of challenges received.                                                    |
| $$j$$       | The number of failed challenges.                                                      |
| $$P$$       | The overall probability that a node passes the series of challenges within the epoch. |

#### Example Calculation

For a given $$\lambda = 5$$, $$\tau = 0.1$$, and $$\alpha = 3$$:

$$
P = \sum_{k < 3} \frac{5^k e^{-5}}{k!} + \sum_{k \geq 3} \sum_{j < 3} \frac{5^k e^{-5}}{k!} \binom{k}{j} (1-0.1)^j 0.1^{k-j}
$$

This formula can be implemented in a programming environment to compute the exact probability $$P$$.

{% hint style="info" %}
**Note**:

* This calculation is essential for determining the reliability and trustworthiness of nodes in a decentralized network.
* Accurate computation of $$P$$ helps in setting appropriate thresholds and emission rates to maintain network integrity.
{% endhint %}

#### Graphic illustrations



<div data-full-width="true">

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim30 (1).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>



<div data-full-width="true">

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim30.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>



<div data-full-width="true">

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim30 (1).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim90 (1).svg" alt=""><figcaption></figcaption></figure>

</div>



### Darwin SPECTER

In the evolving field of AI, using large Transformer models in decentralized networks is challenging, especially in maintaining the integrity of data and computations across untrusted environments. Traditional methods often fail to ensure computational efficiency and verify data integrity, both crucial for sensitive applications.&#x20;

SPECTER (Succinct zero-knowledge Proofs for EffiCient TransformER) tackles these issues by combining zero-knowledge proofs (ZKPs) with Transformer models. SPECTER converts popular open-source Transformer architectures into succinct ZKP variants, known as SPECTER models. This enables verifiable inference computations on untrusted decentralized networks, ensuring the correctness of computations without revealing sensitive information about the data or the model, thus addressing privacy and integrity concerns.

### Architecture of SPECTER

<figure><img src="../.gitbook/assets/Asset 36@300x (2).png" alt=""><figcaption><p>SPECTER Transformer Architecture</p></figcaption></figure>

**Key Adaptations:**

1. **Linearization of Operations**:
   * Nonlinear operations in standard Transformer models (like ReLU or softmax) are replaced with linear or piecewise-linear alternatives for ZKP compatibility.
   * Using SofterMax, an approximation of softmax, simplifies proof generation while maintaining model dynamics.
2. **Simplification of Attention Mechanisms**:
   * Traditional self-attention mechanisms are redesigned to reduce computational intensity in a ZKP setting.
   * Methods include segmenting the attention process or using deterministic sparse patterns to lower the computational load.
3. **Efficient Data Representation**:
   * Data input and intermediate data in the Transformer model are represented in a ZKP-compatible form.
   * This often involves using lower precision or smaller field sizes, reducing the size and complexity of proofs.

**Key Innovations for ZKP Applications:**

1. **Custom ZKP-friendly Layers**:
   * Transformer layers are redesigned to reduce complexity and enhance proof generation efficiency.
   * Includes custom linear layers, optimized normalization layers, and ZKP-aligned activation layers.
2. **Batching Techniques**:
   * Batching multiple data processing instances or layers together reduces overhead in proof generation.
   * This is done without compromising model accuracy or data security.
3. **Streamlined Proof Systems**:
   * Proof systems are optimized for AI operations, with faster setup times, quicker proof generation, verification, and lower memory requirements.
4. **Dynamic Proof Scalability**:
   * Proof complexity can be dynamically adjusted based on security needs and available computational resources.
   * Allows reduced proof workload for less sensitive tasks while maintaining rigor for critical tasks.

### **Key Challenges Addressed by SPECTER**

1. **Security in Decentralized Environments**: SPECTER enhances the security of AI operations in decentralized settings where multiple untrusted parties are involved. By utilizing ZKPs, it ensures that all computations are performed correctly without revealing any underlying data or proprietary information, even to the computation nodes themselves.
2. **Privacy Preservation**: Privacy concerns are paramount, especially when sensitive data is processed across various nodes in a network. SPECTER addresses this by ensuring that data used in computations remains confidential, whether for training or inference. Zero-knowledge proofs provide a robust mechanism to verify computations without exposing the actual data.
3. **Computational Efficiency**: High computational demands have hindered traditional ZKP applications in AI, making them impractical for large models like Transformers. SPECTER introduces optimizations specific to Transformer architectures that significantly reduce the computational overhead of generating and verifying proofs. This makes the system feasible for real-world applications requiring scale and speed.

### **Innovations Introduced by SPECTER**

SPECTER isn't just a theoretical construct but a practical solution enhanced with specific innovations aimed at making zero-knowledge proofs workable and efficient for AI computations:

#### **Transformation of Transformer Models**

Adapting Transformer models to be ZKP-friendly involves altering certain operations within the models to ensure they can be efficiently executed within the ZKP framework. This includes modifications to activation functions and attention mechanisms to suit non-interactive zero-knowledge proofs.

#### **Optimized Proof Mechanisms**

The system utilizes cutting-edge cryptographic techniques to streamline the proof generation and verification processes. This incorporates several optimizations:

1. **SofterMax Function**: SPECTER introduces the SofterMax function, a ZKP-friendly alternative to softmax, which simplifies calculations in normalization layers, reducing computational complexity and enhancing speed without compromising effectiveness.
2. **Smaller Finite Fields**: Using smaller finite fields in cryptographic operations minimizes data load and reduces the complexity of calculations, speeding up proof generation and improving overall efficiency.
3. **Custom Cryptographic Primitives**: SPECTER employs tailored cryptographic primitives optimized for Transformer operations like matrix multiplications and vector additions, reducing overhead and enhancing the efficiency of cryptographic processes.

#### **Ultra-Fast Verification Techniques**

One of SPECTER's key contributions is the development of ultra-fast verification techniques for Transformer-based models, essential for real-time applications. This includes several strategic enhancements:

1. **Optimized Proof Structures**: SPECTER streamlines and simplifies proof structures, reducing the computational load and allowing faster computation verification compared to traditional methods.
2. **Parallel Verification Processes**: SPECTER uses parallel computing to enable simultaneous proof verifications, speeding up the overall process and increasing AI task throughput in decentralized environments.
3. **Incremental Verification**: SPECTER allows verifications to be updated incrementally with each computation step, saving time and resources, particularly for long sequence operations in Transformer models.

Through these innovations, SPECTER paves the way for a new era in AI, enabling the secure and efficient deployment of advanced models in decentralized environments. This creates numerous opportunities for businesses and researchers to use powerful AI tools securely and while preserving privacy.
