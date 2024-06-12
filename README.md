# Project Title

The provided Solidity contract, `MyToken`, implements a simple cryptocurrency token with the name "META" and abbreviation "MTA". It defines three public variables to store the token's name, abbreviation, and total supply. A mapping associates addresses with their corresponding balances. The contract includes a `mint` function that increases both the total supply and the balance of a specified address by a given value, and a `burn` function that decreases both the total supply and the balance of a specified address by a given value, provided the address has a sufficient balance.

## Description

The `MyToken` Solidity contract is a fundamental implementation of a cryptocurrency token system designed for use on the Ethereum blockchain. The contract establishes a token named "META" with the abbreviation "MTA" and maintains a public ledger of the total supply and individual balances through state variables and mappings. The `mint` function allows authorized users to increase the total supply of tokens and allocate new tokens to specific addresses, facilitating the distribution and circulation of the cryptocurrency. Conversely, the `burn` function enables the reduction of the total supply by destroying a specified number of tokens from a given address, ensuring that tokens can be effectively removed from circulation when necessary. This function includes a safeguard to prevent burning more tokens than an address holds, maintaining the integrity of the token supply. Such a contract can be utilized in various applications, including initial coin offerings (ICOs), decentralized finance (DeFi) platforms, and loyalty programs, providing a versatile and secure means of managing digital assets.

## Getting Started

### Installing

1. **Download the Program:**
   - Clone the repository from GitHub using the command:
     ```bash
     git clone https://github.com/your-repo/MyToken.git
     ```
   - Navigate to the project directory:
     ```bash
     cd MyToken
     ```

2. **Modifications:**
   - No specific modifications are needed for basic usage. Ensure you have the required environment set up (Node.js, npm, and Truffle or Hardhat).

### Executing Program

1. **Setup Environment:**
   - Install the required dependencies:
     ```bash
     npm install
     ```

2. **Compile the Contract:**
   - Use Truffle to compile the contract:
     ```bash
     truffle compile
     ```
   - Alternatively, use Hardhat:
     ```bash
     npx hardhat compile
     ```

3. **Deploy the Contract:**
   - Use Truffle to deploy the contract to a local blockchain (e.g., Ganache):
     ```bash
     truffle migrate
     ```
   - Or deploy using Hardhat:
     ```bash
     npx hardhat run scripts/deploy.js --network localhost
     ```

4. **Interact with the Contract:**
   - Open the Truffle console:
     ```bash
     truffle console
     ```
   - Alternatively, use Hardhat's console:
     ```bash
     npx hardhat console
     ```

5. **Mint Tokens:**
   - In the console, execute the mint function:
     ```javascript
     const instance = await MyToken.deployed();
     instance.mint('0xYourAddress', 100);
     ```

6. **Burn Tokens:**
   - In the console, execute the burn function:
     ```javascript
     const instance = await MyToken.deployed();
     instance.burn('0xYourAddress', 50);
     ```

7. **Check Balances and Total Supply:**
   - Get the balance of an address:
     ```javascript
     const balance = await instance.balances('0xYourAddress');
     console.log(balance.toString());
     ```
   - Get the total supply of the token:
     ```javascript
     const totalSupply = await instance.totalSupply();
     console.log(totalSupply.toString());
     ```

This guide provides a basic setup and execution process for deploying and interacting with the `MyToken` contract. Make sure to adjust the commands according to your specific development environment and tools.

## Help

### Common Problems and Solutions

1. **Solidity Version Mismatch:**
   - Ensure the Solidity version in your contract (`pragma solidity 0.8.18;`) matches your development environment.
   - Update the compiler version in `truffle-config.js` or `hardhat.config.js`:
     ```javascript
     // Truffle config
     compilers: {
       solc: {
         version: "0.8.18"
       }
     }
     ```

     ```javascript
     // Hardhat config
     module.exports = {
       solidity: "0.8.18"
     };
     ```

2. **Insufficient Gas:**
   - Increase the gas limit if you encounter "out of gas" errors:
     ```javascript
     // Truffle deployment
     deployer.deploy(MyToken, { gas: 5000000 });
     ```

     ```javascript
     // Hardhat deployment
     await deploy('MyToken', { gasLimit: 5000000 });
     ```

3. **Incorrect Address Format:**
   - Ensure addresses are correctly formatted (e.g., `0xYourAddress`).

4. **Failed Transactions:**
   - Check transaction details on a blockchain explorer and ensure enough ETH for fees.

5. **Contract Not Deployed:**
   - Verify deployment success and correct network connection.

### Helper Command

- Use Truffle or Hardhat console for interactive help:
  ```bash
  truffle console
  ```
  ```bash
  npx hardhat console
  ```

## Authors

Metacrafter Anurag Nayak
@anur6567

## License

This project is licensed under the [Anurag Nayak] License - see the https://github.com/anuraghub004
