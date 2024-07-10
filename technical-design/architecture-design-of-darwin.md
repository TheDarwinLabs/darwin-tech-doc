# ⛪ Architecture Design of Darwin

The Darwin platform is a state-of-the-art L1 blockchain that integrates distributed AI inference capabilities, designed to foster a robust, scalable, and secure environment for AI development and deployment. This platform is built on an EVM-compatible blockchain, allowing seamless integration with existing Ethereum-based tools and infrastructures. Below, we explore the key components of the Darwin system and their functionalities.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Darwin Technical Architecture</p></figcaption></figure>

**Key Components of the Darwin System**

1. **Darwin Chain:**
   * **Tokenomics and $DNA Production:** At the heart of Darwin's economic model, $DNA tokens are minted with each block, driving the ecosystem's incentives and governance.
   * **Stake Pool and Quota System:** Users stake DNA tokens to access AI inference quotas, enabling them to utilize the platform's AI capabilities. This staking mechanism also plays a crucial role in securing the network and enabling decentralized governance.
   * **Darwin Contracts:** These smart contracts facilitate AI transaction submissions and validations, ensuring that operations on the blockchain adhere to predefined rules and are verifiably secure.
2. **User Interface and Relayer Mechanism:**
   * **Rich Frontend:** The user interface is designed to be intuitive and rich in features, facilitating seamless interaction with the blockchain and AI functionalities. It supports wallet integrations and includes advanced features like homomorphic encryption for enhanced privacy and security.
   * **Relayer:** This component is crucial for enabling a [gasless transaction mechanism](darwin-tokenomics-and-gasless-model.md), allowing users to execute AI transactions without incurring gas fees. The relayer handles the complexities of transaction submission and management on behalf of the user.
3. [**Query Mixer**](../key-technologies/query-mixer-lfg-gm.md) **and Orchestrator:**
   * **Query Mixer:** Beyond handling user queries, the Query Mixer generates additional queries to optimize and anonymize the processing of AI tasks. It ensures that the distributed AI nodes operate transparently and without bias.
   * **Orchestrator:** This component allocates AI resources efficiently across the network. It ensures that the right resources are used for the appropriate tasks, balancing load and optimizing performance.
4. [**Distributed AI Inference**](../key-technologies/darwin-distributed-inference.md)**:**
   * **AI Nodes:** These nodes form the backbone of the AI inference system, collaborating to process AI transactions. They run a specialized AI inference engine designed to handle complex AI tasks efficiently.
   * [**SPECTAR**](../key-technologies/darwin-specter/)**:** Darwin’s proprietary zk-proof engine, SPECTAR, enhances the system's privacy and security by generating zero-knowledge proofs for AI inferences, ensuring that operations are both private and verifiable.
5. **Data Availability (DA) Providers:**
   * **Model Data and User-Encrypted Data:** DA providers manage the storage and availability of both model data and user-encrypted data, essential for executing AI models securely and efficiently.
   * **Storage Solutions:** Solutions such as IPFS and Swarm are utilized to ensure that data is stored in a decentralized, reliable, and accessible manner, supporting the platform's overall robustness and scalability.

### Key Technologies

{% content-ref url="../key-technologies/query-mixer-lfg-gm.md" %}
[query-mixer-lfg-gm.md](../key-technologies/query-mixer-lfg-gm.md)
{% endcontent-ref %}

{% content-ref url="../key-technologies/darwin-specter/" %}
[darwin-specter](../key-technologies/darwin-specter/)
{% endcontent-ref %}

{% content-ref url="../key-technologies/darwin-distributed-inference.md" %}
[darwin-distributed-inference.md](../key-technologies/darwin-distributed-inference.md)
{% endcontent-ref %}
