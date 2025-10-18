// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract OnChainPuzzle {
    // Define possible moves as strings (for simplicity)
    // In a more advanced version, you'd use enums for gas efficiency.

    // Mapping to store each player's move sequence
    mapping(address => string[]) public playerMoves;

    // Event to announce when a player submits a move
    event MoveSubmitted(address indexed player, string move);

    // Submit a single move
    function submitMove(string memory _move) public {
        playerMoves[msg.sender].push(_move);
        emit MoveSubmitted(msg.sender, _move);
    }

    // Get all moves a player has made
    function getMoves(address _player) public view returns (string[] memory) {
        return playerMoves[_player];
    }

    // Reset a player’s moves (for starting a new game)
    function resetMoves() public {
        delete playerMoves[msg.sender];
    }
}