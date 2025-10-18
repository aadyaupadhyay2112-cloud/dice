# counter.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Counter {
    // State variable to store the count
    uint256 public count;

    // Function to increment the count by 1
    function increment() public {
        count += 1;
    }

    // Function to decrement the count by 1
    function decrement() public {
        // Prevents underflow (count going below 0)
        if (count > 0) {
            count -= 1;
        }
    }

    // Function to get the current count (optional since 'count' is public)
    function getCount() public view returns (uint256) {
        return count;
    }
}
