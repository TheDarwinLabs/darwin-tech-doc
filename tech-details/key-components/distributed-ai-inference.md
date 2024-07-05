# Distributed AI Inference

**Model Selection and Execution**

The AI Model Hub facilitates the selection of appropriate models for specific tasks requested by users. Once a model is selected, the distributed inference nodes execute the model using the data provided, adhering to privacy and efficiency protocols.

**Zero-Knowledge Proof Generation**

As part of the execution process, each node generates a zero-knowledge proof to verify the correctness of its computations without revealing the underlying data. This ensures that even though the computation is distributed, the privacy and security of the data are never compromised.

**Validation by Orchestrators**

After AI tasks are executed and zero-knowledge proofs are generated, the Orchestrator Network steps in to validate the results. It schedules and oversees the execution of tasks across various nodes, ensuring that the outputs meet the required standards before they are accepted onto the blockchain.
