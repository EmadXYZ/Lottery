🎰 Smart Contract Lottery – Decentralized Raffle on Ethereum
A secure, autonomous, and transparent lottery smart contract built with Solidity, powered by Chainlink VRF v2.5 for provably fair randomness and Chainlink Automation for automated winner selection. Users can enter by paying an `entranceFee`, and the contract automatically picks and pays out a random winner after a set interval and when conditions are met.

🔐 Designed for fairness, automation, and reliable on-chain operations.

🌍 Overview
- **Language**: Solidity ^0.8.18
- **Framework**: Foundry – (Forge, Cast, Anvil)
- **Oracle Integration**: Chainlink VRF v2.5 & Chainlink Automation (Keepers)
- **Goal**: Create a fully decentralized, fair, and self-operating lottery system on EVM-compatible chains.

✨ Key Features
✅ **Verifiable Randomness**: Utilizes Chainlink VRF v2.5 to ensure winner selection is truly random and unbiasable.  
✅ **Automated Operations**: Integrates with Chainlink Automation to automatically check for eligible lottery conditions and trigger winner selection.  
✅ **Minimum Entrance Fee**: Requires participants to pay a defined `entranceFee` to enter the raffle.  
✅ **Time-Based Intervals**: Operates on a predefined time interval, ensuring regular winner draws.  
✅ **Robust Error Handling**: Employs custom errors for gas efficiency and clear feedback (`Raffle__SendMoreToEnterRaffle`, `Raffle__RaffleNotOpen`, `Raffle__UpkeepNotNeeded`, `Raffle__TransferFailed`).  
✅ **Transparent State Management**: Uses `RaffleState` enum (OPEN, CALCULATING) for clear visibility of the lottery’s current status.  

🧠 Contract Architecture
.
├── script/
│   ├── DeployRaffle.s.sol      # Script to deploy the Raffle contract
│   ├── HelperConfig.s.sol      # Manages network-specific configurations (VRF Coordinator, Link Token, etc.)
│   └── Interactions.s.sol      # Scripts for Chainlink VRF subscription management (create, fund, add consumer)
├── src/
│   └── Raffle.sol              # The core Smart Contract Lottery logic
├── test/
│   ├── mocks/
│   │   └── LinkToken.sol       # Mock ERC20 Link token for local testing
│   └── unit/
│       └── RaffleTest.t.sol    # Comprehensive unit tests for the Raffle contract
└── ...


📜 **Key Components**
- **src/Raffle.sol**: Handles player entry, Chainlink VRF requests, winner selection, and payouts.  
- **script/DeployRaffle.s.sol**: Automates deployment and VRF subscription setup.  
- **script/HelperConfig.s.sol**: Provides dynamic configuration for multiple networks (Sepolia, local Anvil).  
- **test/unit/RaffleTest.t.sol**: Extensive unit tests covering edge cases and Chainlink integrations.  

🛡️ Security Considerations
🔒 **Chainlink VRF**: Ensures cryptographically secure and tamper-proof randomness.  
⏰ **Chainlink Automation**: Prevents unnecessary gas consumption by checking conditions before performing upkeep.  
🚨 **Custom Errors**: Gas-optimized error handling for better efficiency.  
🚫 **Re-entrancy Protection**: Follows best practices during winner payouts to prevent attacks.  

📄 License
This project is licensed under the MIT License.  
Feel free to use, modify, or build upon it in your own decentralized applications.

🚀 Getting Started
Clone the repository:  
```bash
git clone https://github.com/YOUR_USERNAME/smart-contract-lottery.git
cd smart-contract-lottery
forge install
forge build
forge test
```
