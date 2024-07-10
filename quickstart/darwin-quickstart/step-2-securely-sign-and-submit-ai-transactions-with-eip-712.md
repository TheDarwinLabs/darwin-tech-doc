# Step 2: Securely Sign and Submit AI Transactions with EIP-712

In this step, we'll detail how to securely structure, sign, and submit an AI transaction using the EIP-712 standard with ethers.js. The aim is to ensure that the transaction is not only secure but also clearly verified as originating from the authentic user, preventing any potential impersonation or fraudulent requests.

**Structuring the EIP-712 Typed Data**

For enhanced security and clarity, the EIP-712 typed data structure will include detailed parameters, ensuring that each part of the transaction is explicitly declared and signed by the user. This structure helps in verifying the authenticity of the transaction data sent to the blockchain.

1.  **Define the Domain and Types**:

    * The domain specifies the contract and network to which this transaction is intended, enhancing the security by binding the signature to a specific environment.
    * The types define the structure of the data to be signed, ensuring all necessary elements of an AI transaction are included and clear.

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
2.  **Prepare the Data to be Signed**:

    * Define the conversation in a structured format where each entry specifies the role (user, system, assistant) and the corresponding input, encapsulating the dialogue or interaction sequence.

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

**Signing the Transaction**

Using ethers.js, the transaction is signed by the user's private key, ensuring that the signature can be verified by the contract to confirm the identity of the sender.

```javascript
async function signTransaction() {
   const signer = provider.getSigner();  // Assumes provider is already set up
   const signature = await signer._signTypedData(domain, types, value);
   console.log('Signature:', signature);
   return signature;
}
const signedData = await signTransaction();
```

**Submitting the Signed Transaction to the Relayer**

After obtaining the signature, the signed transaction is securely sent to the relayer, which acts as an intermediary to interact with the blockchain on the user's behalf. This process ensures that the user's wallet does not directly expose sensitive operations but can still interact with the blockchain securely.

```bash
curl -X POST https://relayer.darwin.example.com/api/submit -H 'Content-Type: application/json' -d '{"signedData": "'"$signedData"'"}'
```

This enhanced step ensures the AI transaction is securely signed and submitted, with clear definitions for each part of the user's input, making the process transparent and secure against potential fraud.
