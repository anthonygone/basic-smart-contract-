<img width="1185" height="1505" alt="image" src="https://github.com/user-attachments/assets/be88f08c-93a8-401e-bd18-420f05c71acb" /># basic-smart-contract-
smart contract
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

// A basic smart contract example (Simple Storage)
// This contract lets anyone store a number on the blockchain and retrieve it later.

contract SimpleStorage {
    // State variable to store a number (saved permanently on-chain)
    uint256 private storedNumber;

    // Event that gets emitted when the number is updated (useful for front-ends)
    event NumberUpdated(uint256 newNumber);

    // Function to set/store a new number
    function store(uint256 _newNumber) public {
        storedNumber = _newNumber;
        emit NumberUpdated(_newNumber); // Notify anyone listening
    }

    // Function to retrieve the stored number (read-only, no gas cost for caller)
    function retrieve() public view returns (uint256) {
        return storedNumber;
    }
}
