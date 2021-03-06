# Funds

Funds.sol is a smart contract that aims to present some features of the Solidity language in the context of a university exercise. The current implementation is partial and does not fully reflect the requirements defined below, but it is enough to reach the learning objectives.

### Definition of the contract in English

A group of friends wants to deposit funds in a safe place and guarantee that the funds cannot be withdrawn until at least 2 of the friends authorise the transaction.
When at least 2 of the friends have signed a designated contract, the funds can be withdrawn by any of the friends.

How can we solve this problem using traditional techniques?

### Solving the problem with a Solidity smart contract

1. Open [Remix IDE](https://remix.ethereum.org/);
2. Create a new file Funds.sol and paste into it the script contained in this repository;
3. Compile Funds.sol;
4. Deploy Funds.sol;
5. Deposit funds (for example, 1 Ether) into the smart contract by invoking the fallback function;
6. Try to withdraw (withdrawFunds ()) the smart contract funds. It will not be possible since nobody signed the contract;
7. Sign (writeSignature()) the contract at least 2 times using distinct addresses and by providing names;
8. Withdraw (withdrawFunds()) the funds from the smart contract using one of the addresses used for signatures;

Now try using the Ropsten public test network (team up with someone else)!

9. Install [Metamask](https://metamask.io/) and follow the wizard;
10. Connect to the Ropsten network;
11. Withdraw funds for free from the Ropsten faucet;
12. As a Remix IDE environment select Injected Web3, so as to interact with Ropsten;
13. (Only one of you) deploy Funds.sol;
14. (The other person) invoke (at address) Funds.sol from the other instance of Remix IDE using the smart contract address;
15. Deposit funds (for example, 1 Ether) into the smart contract by invoking the fallback function;
16. Sign (writeSignature()) the contract at least 2 times using distinct addresses and by providing names;
17. Withdraw (withdrawFunds()) the funds from the smart contract using one of the addresses used for signatures;

Note that in this case the signatures and the names will be written **permanently** on the Ropsten public test network.
Students may use also [Etherscan](https://ropsten.etherscan.io/) to interact with the the smart contract.

### Optional part (working on your own)

18. Modify the code to require sending a positive amount of Ether to the contract to sign it (replace line 24 of the code with the code below);

```solidity
 function writeSignature(string memory _name) public payable isOwner(false, "An address can be used only once to sign the contract.") {
  require(msg.value > 0, "A positive amount of Ether is required to sing the contract.");
```

19. Repeat the process from step 3, taking into consideration the new rule;
