# How We Achieve Cross-border Capability

<figure><img src="../.gitbook/assets/Desktop - 1.png" alt=""><figcaption><p>NusaPay Cross-border Diagram Flow</p></figcaption></figure>

We achieve seamless cross-border capability by intelligently managing the movement of value from the user's Web3 wallet to various blockchains up to the final settlement in local fiat currency. This is a multi-stage process that is fully transparent and optimized for efficiency. Our robust cross-chain infrastructure leverages technologies like Chainlink CCIP for specific high-assurance transfers (as illustrated by the automated payroll flow), and integrates the LI.FI SDK/API for broader asset bridging and routing across diverse networks.

### Initiating Cross-Chain Payment (from Employer via Arbitrum):

* The process begins when an Employer sends USDC (along with payroll data) from their Web3 wallet to the Payroll Smart Contract (SC) deployed on Arbitrum.
* The Payroll SC (Arbitrum) then initiates the transfer of this USDC to the Base chain using Chainlink CCIP (Cross-Chain Interoperability Protocol).

### Secure Cross-Chain Transfer via Chainlink CCIP to Base:

* Chainlink CCIP plays a crucial role in facilitating the secure and trustless transfer of USDC from Arbitrum to the IDRX Smart Contract (SC) deployed on Base. This ensures data and value integrity during cross-chain transit.
* Upon completion of the transfer, USDC enters the IDRX SC on Base.

### On-Chain Activity Detection & Fiat Payout Orchestration:

* As soon as USDC enters the IDRX SC (Base), this smart contract automatically emits a deposit event. This event is an on-chain signal indicating the receipt of funds.
* The IDRX Backend actively listens for the deposit event emitted by the IDRX SC on Base. When the event is detected, it triggers the subsequent off-chain process.

### Internal Conversion & Fiat Transfer to Employee's Account:

* Based on the event from the IDRX SC, the IDRX Backend then converts the received USDC value into the local fiat currency (IDR).
* Subsequently, the IDRX Backend transfers the IDR directly to the Employee's bank account, with Bank Indonesia (or the relevant local bank) facilitating the final deposit. This results in the salary entering the employee's account.

### Verification & Transparency:

* Every key step of this flow—from initiation on Arbitrum, cross-chain transfer via CCIP, to receipt on IDRX SC Base, and event triggering—is recorded and verified on the blockchain. This ensures a transparent and immutable audit trail, allowing real-time monitoring of transaction status.
