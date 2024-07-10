# Step 1: Create and Submit a Stake Transaction

**Interacting with the Staking Contract**:

* **Contract Address**: `0x123...def` (Darwin Staking Contract)
*   Using ethers.js, connect to the contract and call the `stakeDNA` function:

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

####
