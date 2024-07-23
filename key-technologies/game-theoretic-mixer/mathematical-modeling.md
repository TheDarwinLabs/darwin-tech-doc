---
cover: ../../.gitbook/assets/颜色=黑底紫色.png
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Mathematical Modeling

## Test Passing Probability Calculation

### Overview

This section details the calculation of the probability that a node will pass a series of challenges within an epoch, given a fixed challenge emission rate. The probability is modeled using a Poisson distribution and incorporates parameters for challenge difficulty and the threshold for node slashing.

### Calculation Details

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

* $$\lambda$$: The fixed challenge emission rate.
* $$\tau$$: The probability that a cheating node passes a single challenge.
* $$\alpha$$: The threshold number of failed challenges after which a node will be slashed.
* $$k$$: The number of challenges received.
* $$j$$: The number of failed challenges.
* $$P$$: The overall probability that a node passes the series of challenges within the epoch.

#### Example Calculation

For a given $$\lambda = 5$$, $$\tau = 0.1$$, and $$\alpha = 3$$:

$$
P = \sum_{k < 3} \frac{5^k e^{-5}}{k!} + \sum_{k \geq 3} \sum_{j < 3} \frac{5^k e^{-5}}{k!} \binom{k}{j} (1-0.1)^j 0.1^{k-j}
$$

This formula can be implemented in a programming environment to compute the exact probability $$P$$.

### Additional Information

* This calculation is essential for determining the reliability and trustworthiness of nodes in a decentralized network.
* Accurate computation of $$P$$ helps in setting appropriate thresholds and emission rates to maintain network integrity.

#### Graphic illustrations



<div>

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim30 (3).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim60 (1).svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 30_azim90 (1).svg" alt=""><figcaption></figcaption></figure>

</div>



<div>

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim30.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim60.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 60_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>



<div>

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim30.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim60.svg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Game Theoretic Mixer Validity Hyperplane 90_azim90.svg" alt=""><figcaption></figcaption></figure>

</div>
