# 🏇 Darwin Quickstart

This guide provides a step-by-step guide for quickly interacting with the Darwin AI blockchain platform.&#x20;

{% hint style="info" %}
**Note**:

This guide ensures that system integrity and user identity are maintained throughout the transaction process.
{% endhint %}

### **Prerequisites**

1. **Prepare Your EVM-Compatible Wallet**: Ensure your wallet supports EVM standards and can interact with Ethereum-based smart contracts. We recommend using MetaMask.
2. **Add Darwin Chain Network**:
   * Visit the [Darwin Chain website](https://explorer.darwinchain.ai/).
   * Scroll down -> click the **Add Darwin chain** button.
3. **Acquire $DNA Tokens**:
   * Visit the Darwin Faucet at `https://darwin-faucet.example.com` You can participate in staking and transactions to obtain initial $DNA tokens.

### Quickstart

#### Step 1: Create and Submit a Stake Transaction

Use the `ether.js` to connect to the contract and call the `stakeDNA` function:

```javascript
import { ethers } from 'ethers';

// Connect to the provider (e.g., MetaMask)
const provider = new ethers.providers.Web3Provider(window.ethereum);

// Signer derived from the provider
const signer = provider.getSigner();

// Connect to the contract
const contract = new ethers.Contract('0x123...def', abi, signer);
const stakeAmount = ethers.utils.parseEther('100'); // Staking 100 $DNA

// Send the stake transaction
async function stakeDNA() {
  const txResponse = await contract.stakeDNA(stakeAmount);
  console.log('Transaction Response:', txResponse);
}
stakeDNA();
```

{% hint style="info" %}
**Note**:

The Darwin Staking Contract Address is `0x123...def` .&#x20;
{% endhint %}

#### Step 2: Sign and Submit AI Transactions with EIP-712

This step details how to securely structure, sign, and submit an AI transaction using the EIP-712 standard with ethers.js.

{% hint style="info" %}
**Note**:

To ensure security and clarity, the **EIP-712** typed data structure includes detailed parameters explicitly declared and signed by the user. This structure verifies the authenticity of transaction data sent to the blockchain.
{% endhint %}

1. Define the Domain and Types:

```javascript
const domain = {
  name: 'DarwinAI',
  version: '1',
  chainId: 1,  // Specify the correct chain ID for your deployment
  verifyingContract: '0x123...def'  // Contract address that will verify the signature
};

const types = {
  AIRequest: [
    { name: 'requestId', type: 'uint256' },
    { name: 'conversation', type: 'Prompt[]' }
  ],
  Prompt: [
    { name: 'role', type: 'string' },
    { name: 'input', type: 'string' }
  ]
};
```

2. Prepare the Data to be Signed:

```javascript
const value = {
  requestId: 1,
  conversation: [
    { role: 'user', input: 'What are the benefits of blockchain?' },
    { role: 'system', input: 'Exploring decentralized solutions.' },
    { role: 'assistant', input: 'Blockchain provides security and transparency.' }
  ]
};
```

3. Signing the Transaction:

```javascript
async function signTransaction() {
   const signer = provider.getSigner();  // Assumes provider is already set up
   const signature = await signer._signTypedData(domain, types, value);
   console.log('Signature:', signature);
   return signature;
}
const signedData = await signTransaction();
```

4. Submitting the Signed Transaction to the Relayer:

After obtaining the signature, the signed transaction is securely sent to the relayer, which acts as an intermediary to interact with the blockchain on the user's behalf.

```bash
curl -X POST https://relayer.darwin.example.com/api/submit -H 'Content-Type: application/json' -d '{"signedData": "'"$signedData"'"}'
```

#### Step 3: Retrieve Streaming AI Results from the Query Mixer

After signing and submitting your AI transaction, retrieve the AI-generated results from the Query Mixer using your unique `requestId.`&#x20;

{% hint style="info" %}
**Note**:

This ID, generated during transaction submission, is essential for fetching the corresponding real-time streaming responses from AI nodes.
{% endhint %}

```bash
curl -X GET "https://query-mixer.darwin.example.com/results?requestId=1" -H "Accept: text/event-stream"
```

{% hint style="info" %}
**Note**:

The header `"Accept: text/event-stream"`; this is crucial for establishing a streaming connection. It tells the server that the client can handle streaming data as it becomes available.
{% endhint %}

When requesting streaming data, the server keeps the connection open, sending real-time updates as AI nodes process them. Each data packet contains a portion of the AI's response, allowing the client to process or display the information incrementally.
