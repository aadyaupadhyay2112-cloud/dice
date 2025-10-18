🎮 OnChainPuzzle Smart Contract

A simple on-chain puzzle/game logic smart contract that allows players to submit and track their move sequences directly on the blockchain.
Each player's moves are stored persistently using Solidity mappings and dynamic arrays, making it a great example of on-chain state tracking.

📜 Contract Information

Contract Name: OnChainPuzzle

Network: (Specify your network — e.g., Ethereum Sepolia / Polygon Testnet / Remix VM)

Deployed Address: [0x68f52d94595a9272948f95114A06cD35e92C9CAB]

License: MIT


🧠 What This Contract Does

The OnChainPuzzle contract stores each player's game moves on-chain.
Players interact by submitting moves (as text), retrieving their history, and resetting their progress.

Key Features:

🕹️ Submit Moves: Players can send moves such as "UP", "LEFT", "RIGHT", etc.

📜 View Moves: Anyone can view the full move history of any player.

🔄 Reset Moves: Players can clear their move history to start a new round.

🔔 Events: Every move triggers an event so off-chain apps or explorers can track gameplay actions.

⚙️ How to Use
1. Deploy or Connect

You can interact with the deployed contract directly at:
0x68f52d94595a9272948f95114A06cD35e92C9CAB

Alternatively, deploy your own copy using Remix IDE
.

2. Interact with Functions
Function	Description	Example Input	Example Output
submitMove(string _move)	Records a new move for the caller.	"UP"	Emits MoveSubmitted(player, "UP")
getMoves(address _player)	Returns all moves made by a player.	0xYourAddress	["UP", "LEFT", "DOWN"]
resetMoves()	Clears all moves for the sender.	—	Moves deleted
🧩 Example Gameplay

Call submitMove("UP")

Call submitMove("LEFT")

Call getMoves(your_address) → ["UP", "LEFT"]

Call resetMoves() → getMoves() returns []

🔍 Concepts Demonstrated
Solidity Concept	Description
Mapping	Links player addresses to their personal move list.
Dynamic Arrays	Store an expandable sequence of moves per player.
Events	Notify off-chain systems (like UIs or explorers) when actions happen.
State Management	Keeps persistent player data on the blockchain.
🚀 Future Enhancements

You can extend this contract with:

Enums for predefined moves (UP, DOWN, LEFT, RIGHT).

Game logic that checks if a player completes a correct move sequence.

Scoring system that rewards correct gameplay.

Leaderboards or time-based challenges.

🪪 License

This project is licensed under the MIT License — free to use, modify, and distribute
