# Game Theoretic Mixer

The Query Mixer is a key part of the Darwin AI blockchain platform, designed to ensure the authenticity and integrity of AI inferences across distributed networks. It tackles inference validation with Probabilistic Query Mixing, blending real user queries with special challenge queries to ensure nodes process requests honestly. Using our proprietary LLM instructional fingerprint, the system outputs consistent results for specific queries, leveraging a game-theoretic approach to prevent cheating and guarantee honest behavior by inference nodes.

### Key Features

* **Collusion Prevention**: The system prevents cheating and collusion by rerouting queries through multiple nodes and adding mixing layers. Each step is transparently recorded on-chain, deterring nodes from dishonest behavior because they risk losing their staked crypto assets.
* **Enhanced Security**: The combined mechanisms of mixing and slashing ensure that inference nodes perform correctly, as challenge query responses are checked against expected answers.
* **Efficiency and Reliability**: The Query Mixer operates swiftly and reliably, maintaining the accuracy and honesty of AI inferences.



### Game-Theoretic Mixer Validation Protocol

<figure><img src="../../.gitbook/assets/Asset 32@300x (4).png" alt=""><figcaption><p>Game theoretic mixer flow</p></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim30 (1).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>



<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim30.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>



<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim30 (1).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim90 (1).svg" alt=""><figcaption></figcaption></figure>

</div>
