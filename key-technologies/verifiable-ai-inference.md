# Verifiable AI inference

Darwin offers a verifiable AI inference system that uses a client-server model to distribute large language model layers across multiple servers. Each server processes specific layers sequentially, leveraging collaborative computing resources for complex inferences without requiring powerful hardware from each participant.

### **Technical Architecture**

<figure><img src="../.gitbook/assets/Asset 30@300x (5).png" alt=""><figcaption><p>Verifiable Distributed AI Inference</p></figcaption></figure>

The system's architecture is designed to support multiple clients and servers simultaneously, contributing to various stages of the inference process. The following points detail the core components and functionalities:

#### **Layered Processing**

The architecture is designed to partition the model into different layers. Each server within the network is responsible for processing one or more of these layers. This division allows for optimized processing time and resource utilization by parallelizing the workload across multiple servers. The diagram above illustrates this by the data flow through various components such as Embeddings, LayerNorm, Self Attention, RMS Norm, FeedForward, Linear, and Softmax, each server handling specific parts of the model.

#### **Client-Server Interaction**

Clients initiate the inference process by sending input data to the initial set of servers. Each server processes the data through its assigned model layers, as shown in the diagram by the sequence of operations starting from embedding and moving through layer norm, Self-attention, and so forth. After processing, each server forwards the intermediate outputs to the next server in the sequence. This process continues until the final output is generated, ensuring that each layer's computation is completed in order.

#### **Dynamic Load Balancing and Quantization**

The system utilizes dynamic quantization techniques to reduce computational overhead and latency, ensuring efficient data handling and faster response times. The architecture incorporates load-balancing mechanisms that distribute the workload evenly among servers, as indicated by the connections between LayerSharding and Distributed AIVM computation nodes. This prevents bottlenecks and optimizes overall system performance, ensuring no single server is overwhelmed while others are underutilized.

<figure><img src="../.gitbook/assets/Asset 31@300x (4).png" alt=""><figcaption><p>Distributed Inference Flow</p></figcaption></figure>

**Load Balancing Flow:**

1. **Client to Server 1:**
   * The client sends data for inference to Server 1.
2. **Server 1 Processing:**
   * **Process Data with Layer 1:** Server 1 processes the received data using Layer 1 of the model.
   * **Pass Data to Next Server:** Server 1 passes the intermediate output to Server 2 after processing.
3. **Server 2 Processing:**
   * **Process Data with Layer 2:** Server 2 processes the data it received from Server 1 using Layer 2 of the model.
   * **Pass Data to Next Server:** Server 2 passes the intermediate output to Server 3 after processing.
4. **Server 3 Processing:**
   * **Process Data with Layer 3:** Server 3 processes the data it received from Server 2 using Layer 3 of the model.
   * **Pass Data Back:** Server 3 sends the final output back to Server 1 after processing.
5. **Server 1 to Client:**
   * **Return Final Output:** Server 1 returns the final output to the client.

### Advanced Features

This distributed AI inference system represents a significant leap in making large-scale AI models more accessible and usable across diverse computing environments. By distributing the computational load among multiple servers and allowing for collaborative model development, the system:

* **Security and Integrity**: Robust security measures prevent unauthorized access and ensure the integrity of the data as it moves through the system. These measures are crucial for maintaining the confidentiality and reliability of the inference results.
* **Collaborative Extensions**: The system supports the development and integration of model extensions. Contributed by different collaborators, these extensions can be shared and utilized across the network, fostering a rich ecosystem of shared AI tools and models.
* **Enhances Accessibility:** Users no longer need high-end hardware to run complex models, democratizing AI for a broader audience.
* **Optimizes Performance:** Dynamic load balancing and quantization techniques ensure efficient data handling and faster response times.
* **Fosters Collaboration:** The ability to share and integrate model extensions supports a collaborative AI community, driving continuous improvement and innovation.
