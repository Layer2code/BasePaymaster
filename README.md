# BasePaymaster: A Comprehensive Guide Introduction BasePaymaster 

BasePaymaster emerges as an ERC-4337 Paymaster contract crafted by Build-On-Base. This distinctive creation offers the ability to cover gas fees with ERC20 tokens. Impressively, if the actual gas cost is less than the pre-estimated amount, the contract ensures the return of the overpaid tokens. In addition, the contract provides functionality to adjust its pricing strategy and grants the contract's owner the permission to withdraw tokens. Using an Oracle, it consistently retrieves the most recent token values.

Core Features
ERC20 token-based gas fee payments.
Automated return of extra tokens based on actual gas usage.
Ability to modify the pricing framework.
Specialized token withdrawal functionality for the contract owner.
Real-time token price updates through Oracle integration.
Contract Structure
BasePaymaster builds upon the foundation laid by BasePaymaster.

Main Functions
constructor: Sets up the BasePaymaster contract using the provided parameters.
updateConfig: Adjusts configurations related to price markup and the threshold for price revisions.
withdrawToken: Enables the contract's owner to take out a specified amount of tokens.
updatePrice: Refreshes token value by drawing the newest price from the Oracle.
_validatePaymasterUserOp: Checks the legitimacy of a paymaster user action and gauges the necessary token amount for the transaction.
_postOp: Conducts post-transaction activities, such as updating token prices and returning surplus tokens.
Key Events
ConfigUpdated: Activated whenever changes are made to the price markup and threshold settings.
Deployment & Utilization
Activate the BasePaymaster contract by inputting essential parameters, which include the addresses of the ERC20 token, EntryPoint contract, and Oracle.
As needed, utilize the updateConfig function to adjust the pricing structure and update configurations.
The contract's owner is vested with the authority to extract tokens via the withdrawToken function.
To refresh the token's price, use the updatePrice function.
For a deeper dive, the embedded comments in the contract's source code serve as a valuable resource.

Setting Up Your Development Environment
Prerequisites
The developmental structure efficiently accommodates both Hardhat and Foundry. This guide assumes prior installations of the said platforms.

Hardhat Configuration

Hardhat is renowned for its capabilities in gas metering and SDK development.

Dependency Installation


Copy code
npm install
Test Execution

npx hardhat test
This action provides a detailed breakdown of gas costs across various situations, such as refunds, token payment limits, and price adjustments.

Note: The inaugural transaction may incur a higher cost due to the nonce increasing from 0 to 1.

Foundry Configuration
Foundry is celebrated for its prowess in unit testing.

Dependency Installation

forge install
Test Implementation

forge test
Coverage Assessment

forge coverage

Licensing
The project is safeguarded under the GNU General Public License v3.0.

