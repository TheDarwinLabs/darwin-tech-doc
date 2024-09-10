# AI Node

Users who contribute their computing resources to the network can earn **$DNA** rewards. The diagram below illustrates how AI nodes connect to the system, and this article explains how users can earn **$DNA** by participating with their nodes.

<figure><img src="../../../.gitbook/assets/Asset 43@300x (5).png" alt=""><figcaption><p>How AI Node interact</p></figcaption></figure>

### Token Mining Process

The process of earning **$DNA** tokens involves several steps:

1. **Security Challenges:** The QueryMixer uses a Game-theoretic approach to issue random security challenges to connected nodes.
2. **Node Verification:** Nodes respond to these challenges, and the QueryMixer evaluates their responses. The evaluation considers various factors, including network latency, computing resources, and bandwidth.
3. **Transaction Validation:** Once a node's response is verified, the QueryMixer signs the transaction and broadcasts it to other QueryMixers.
   * If the transaction is valid, it is signed and further broadcasted.
   * If any information is invalid, the transaction is discarded.
4. **Validator Submission:** Transactions that receive more than two-thirds of the QueryMixer signatures are submitted to the Validator.
5. **Token Rewards:** The Validator confirms the transaction's validity and awards tokens to the mining nodes based on their performance scores.

### Reward Distribution and Epoch Management

Token rewards, comprising 1024 blocks, are distributed at the end of each epoch. During an epoch, the QueryMixer processes all node transactions. After the epoch concludes, the transactions are aggregated (rolled up), and the final calculations are stored on the blockchain.

### Scoring Mechanism

Every AI node that joins the network is evaluated based on several key performance indicators. These indicators include:

* **Network Bandwidth**: Different network bandwidths correspond to different data throughputs. The system performs different calculation assignments based on node bandwidths. Nodes with higher bandwidth can handle larger data throughputs, making them more suitable for tasks that require substantial data processing. The system prioritizes nodes with higher bandwidth for these tasks.
* **Computing Resources**: Computing resources are the core resources of AI nodes related to the normal and efficient operation of the entire AI module. Nodes with superior computing power receive higher priority during task scheduling and a better income score. Computing resources include the GPU, CPU, and RAM of your hardware.
* **Network Latency**: Low latency is essential for providing a good user experience. Nodes with lower latency are prioritized in the scheduling process. Meanwhile, nodes with higher latency are penalized with a lower score, potentially missing out on task allocations and reducing their income.

The scoring system is designed to reward nodes that maintain strong performance across these dimensions. However, due to the punishment mechanism, those with weaker scores may face reduced benefits or even removal/banning from the network.
