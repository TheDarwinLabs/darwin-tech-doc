# AI Node

Users with computing resources can obtain $DNA rewards by providing their resources. The figure below describe how AI node connect into the system, and we will describe how user get $DNA as rewards with their nodes.

<figure><img src="../../.gitbook/assets/AI node miner.png" alt=""><figcaption><p>How AI Node interact</p></figcaption></figure>

### Score

Each AI node connected to the system will be scored according to the performance parameters, which includes:

Network bandwidth: Different network bandwidths correspond to different data throughputs. The system performs different calculation assignments based on node bandwidths. For requests with a large amount of data, nodes with a high bandwidth are preferentially used for corresponding calculations.

Computing resources: Computing resources are the core resources of AI nodes, which are related to the normal and efficient operation of the entire AI module. Nodes with higher computing power can generally obtain higher scheduling priority and income score in task allocation.

Network delay: Network delay is related to user experience, lower network delay means better user experience, the system will dynamically allocate the priority of nodes in the process of scheduling, and nodes with higher network delay not only mean that they will get a lower score, but also mean that they may not be able to allocate computing tasks and affect the income.

A complete scoring mechanism is set for indicators of each dimension of nodes, so as to ensure that normal nodes can obtain better scores and benefits, while nodes with lower scores will obtain lower benefits, and even be removed from the network due to the punishment mechanism.

### How Token mined

1. QueryMixer use VRF randomly challenges the connected nodes for security.
2. QueryMixer verified the return of the Challenge, and scored according to the network delay and various indicators of the node, such as CPU, GPU and bandwith.
3. QueryMixer signs the scored transaction and broadcasts it to the other QueryMixers.
   1. If is valid, sign and broadcast it
   2. If any information is invalid, the transaction is discarded
4. Any transaction received by the QueryMixer node containing more than 2/3 signatures is submitted to the Validator
5. The Validator verifies the validity of the signature and rewards mining nodes with tokens based on the scored information
6. The reward of the whole token is settled with 1024 blocks as epoch. All node transactions are processed by QM within one epoch, and rolled up at the end of one epoch. The final calculation is will be stored on the chain.
