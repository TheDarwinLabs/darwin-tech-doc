# 🦾 Query Mixer(LFG-GM)

#### Overview

The Query Mixer is an innovative component of the Darwin AI blockchain platform, designed to ensure the authenticity and integrity of AI inferences across distributed networks. This system addresses the critical challenge of inference validation by implementing a novel protocol known as Probabilistic Query Mixing. This protocol strategically blends real user queries with specially crafted challenge queries, ensuring that all nodes in the network process requests impartially and honestly.

<figure><img src="../.gitbook/assets/image.png" alt="" width="563"><figcaption><p>Query Mixer</p></figcaption></figure>

#### Probabilistic Query Mixing Protocol

**Generating Challenge Queries**

**Instructional Fingerprinting Technique:**

* Challenge queries are crafted using a method known as instructional fingerprinting. This involves fine-tuning a Language Model (LLM) on a meticulously curated dataset of instruction pairs $$(x_i, y_i)$$.
* The model is engineered to respond to a query $$x_i$$ with a predefined answer $$y_i$$, creating a set of query-answer pairs that serve as the model’s fingerprints.
* These fingerprints are used as challenges within the query batches sent to inference nodes, serving as benchmarks to validate the node's output.

**Query Mixer Mechanism**

**Mixing and Sending Queries:**

* Real user queries are mixed with challenge queries, creating batches where the origin of each query (user or challenge) is indiscernible to the inference nodes.
* This enforces a level of honesty in processing, as nodes must treat every query with equal fidelity, unaware of which queries are tests.

**Collusion Prevention**

**Query Rerouting Strategy:**

* To prevent potential collusion between orchestrators and inference nodes, queries are rerouted among several orchestrator nodes.
* Each node randomly selects another orchestrator to forward the query batch, further mixing in additional queries before the final dispatch to an inference node.
* The path taken by each query is meticulously recorded on the blockchain, ensuring transparency and the ability to audit the process for any signs of collusion.

#### Mathematical Validation

**Statistical Analysis Using Chi-Square Test:**

* The uniformity of query distribution among orchestrators is verified using a chi-square test. This test checks whether the distribution of passed queries aligns with a uniform distribution, indicating no preference or bias in the routing process.
* For a network of $$n$$ nodes $${V_{1}, V_{2}, ..., V_{n}}$$, if node $$i$$ participates in $$k$$ rounds of query passing, $$P_{j}(V_{i})$$ denotes the number of times node $$i$$ has passed a query to node $$j$$. The sum of passes from node $$i$$ to all nodes should equal $$k$$, i.e., $$\sum_{t = 1}^{n} P_{t}(V_{i}) = k$$.
*   The test statistic is calculated as:

    $$
    \chi = \sum{\frac{(P_{t} - E)^2}{E}}, \quad E = \frac{k}{n}
    $$

    with a significance level $$\alpha = 0.05$$ to determine the honesty of node distributions.

#### Probabilistic Inference Validation Protocol

**Operational Phases:**

1. **Query Submission:** Users send their queries to the Query Mixer.
2. **Query Rerouting:** Queries circulate within the network to gain signatures and undergo additional mixing.
3. **Probabilistic Query Mixing:** The final Query Mixer node combines the user’s query with a challenge and forwards the batch to an inference node.
4. **Model Execution:** The inference node processes the batch and returns results for all queries.
5. **Verification:** Challenge queries are verified against expected responses, and the path of the user’s query is audited for integrity.



The Query Mixer is a fundamental safeguard in Darwin's AI blockchain ecosystem, crucial for ensuring that all inferences are performed transparently and correctly. By leveraging cryptographic techniques and probabilistic methods, it effectively secures the network against fraud and collusion, fostering a trustworthy environment for distributed AI processing.
