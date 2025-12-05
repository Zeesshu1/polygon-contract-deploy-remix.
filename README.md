# polygon-contract-deploy-remix.
Contract Code // SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

// OpenZeppelin imports for security
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyPolygonToken is ERC20, Ownable {
    
    // Constructor: Jab contract deploy hoga tab ye run karega
    constructor() ERC20("My Polygon Token", "MPT") Ownable(msg.sender) {
        // Deploy karne wale ko 10,000 Tokens milenge
        _mint(msg.sender, 10000 * 10 ** decimals());
    }

    // Aur tokens mint karne ka function (Sirf Owner kar sakta hai)
    function mintMore(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}
Instructions # Polygon (POL) Smart Contract Deployment

This repository contains a starter Smart Contract for the **Polygon PoS Network** (utilizing the POL token). It is designed to be easily deployed using Remix IDE.

## Features
- ERC-20 Token Standard
- Mintable (Owner only)
- Polygon Mainnet & Amoy Testnet compatible

## Deployment Steps (Remix)

1. **Copy Code:** Copy the content of `MyPolygonToken.sol`.
2. **Open Remix:** Go to [remix.ethereum.org](https://remix.ethereum.org/).
3. **Paste:** Create a new file and paste the code.
4. **Compile:** Hit the 'Compile' button (ensure version is 0.8.20 or higher).
5. **Connect Wallet:** - Go to the "Deploy & Run" tab.
   - Select **Injected Provider - MetaMask**.
   - Switch your MetaMask network to **Polygon PoS**.
6. **Deploy:** Click the orange "Deploy" button and confirm the transaction in MetaMask.

## Network Info
- **Network Name:** Polygon PoS
- **Currency Symbol:** POL (formerly MATIC)
