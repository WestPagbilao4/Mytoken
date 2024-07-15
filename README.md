MyToken Smart Contract

A straightforward token created with Solidity

Description
This program is a simple smart contract written in Solidity, the programming language for creating smart contracts on the Ethereum blockchain. The MyToken contract establishes a basic token with capabilities to mint and burn tokens. It keeps track of the total supply of tokens and the balances of individual addresses. This contract serves as an introductory example of token creation and management in Solidity, laying the groundwork for more advanced token-based projects.

Getting Started
Running the Program
To execute this program, you can use Remix, an online Solidity IDE. Start by visiting the Remix website at Remix Ethereum.

Once on the Remix site, create a new file by clicking the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyToken {

    // Public variables to store token details
    string public name = "West";
    string public symbol = "WST";
    uint256 public totalSupply = 0;

    // Mapping from address to balance
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint256 _amount) public {
        totalSupply += _amount;
        balances[_to] += _amount;
    }

    // Burn function to destroy tokens
    function burn(address _from, uint256 _amount) public {
        require(balances[_from] >= _amount, "Insufficient balance to burn");
        totalSupply -= _amount;
        balances[_from] -= _amount;
    }
}

To compile the code, navigate to the "Solidity Compiler" tab in the left-hand sidebar. Ensure the "Compiler" option is set to "0.8.0" (or another compatible version), and click the "Compile MyToken.sol" button.

After compiling the code, deploy the contract by going to the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu and click the "Deploy" button.

Once deployed, you can interact with the contract. You can check the token balances of specific addresses using the balances function. Verify the token abbreviation by accessing the symbol variable, which contains "WST". Confirm the token's name by retrieving the name variable, which holds "West". You can also query the total supply of tokens through the totalSupply variable. Additionally, you can mint new tokens to an address using the mint function, providing the target address and the number of tokens to be created. Conversely, you can burn tokens from an address using the burn function, specifying the address and the number of tokens to be destroyed. These features provide a comprehensive set of tools for managing and interacting with the MyToken contract on the Ethereum blockchain.

Authors
West Pagbilao @Westpagbilao4
