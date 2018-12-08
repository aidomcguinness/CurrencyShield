# CurrencyShield
Ethereum project CA DLT DBS Fintech 

B9FT103 Distributed Ledger Technologies
Smart Contract in Solidity (FX Option)
CA 2
Aidan McGuinness, Duaine Timmons, Ronan Bourke

Business background
CurrencyShield was founded in 2018 in Dublin and we are an agile, exponentially growing Fintech business providing our customers fee free fx transfers, as well as access to risk mitigating financial instruments like fx options. Our global client base consists exclusively of individuals, so we are exclusively a retail financial institution. Data security and integrity are central pillars to the future success of this firm as we build and maintain trust in this emerging industry.
We have opted to record all options contracts on the Ethereum blockchain. Below is an outline of the inner workings of our options smart contract as defined on the blockchain, where a buyer is purchasing GBP option with their EUR currency from CurrencyShield, maturity date is 3 months in the future.

Components of the smart contract:
•	Buyer (Individual)
•	Seller (CurrencyShield)
•	Buyer’s EUR account
•	Buyer’s GBP account
•	CurrencyShield EUR account
•	CurrencyShield GBP account
•	Call option contract 
•	Cost of carry
•	Maturity date
•	Base Currency amount
•	Traded Currency amount
•	Market fx rate feed
Our initial challenge was to determine the live fx rates in order to correctly ascertain the rates to be built into the smart contract. This is performed outside of Ethereum via a forex feed that generates the live rates into our API. Preset algorithms determine the cost of carry based on maturity date and currency volatility. Our interface allows users to input this data and get an instant calculation. Once the option is agreed, the details are plugged into the smart contract.
In order for the transfer of funds to occur and record on the blockchain, a proxy must exist to represent both party’s accounts. Once created, the smart contract can interact with both accounts as per the terms outlined in the agreed contract. The buyer in this case is obligated to pay the cost of carry under any and all circumstances, however the decision to execute the call option is entirely at the discretion of the buyer at maturity date. 
The user interface allows the user to interact with the contract at any time between agreement and maturity date to purchase the call option or terminate their option to do so. This is observed by the existence of an ancillary smart contract on the blockchain that can interact with the main smart contract. Once this has been input into the smart contract, there is no recourse.
The market data feed to the smart contract is triggered once the smart contract is interacted with. This feed ultimately determines the intrinsic value of the option at a given point in time, i.e. the contract receives a record of the fx rate on maturity date.
Once maturity date is achieved and all conditions of the contract are met, the smart contract defines whether or not the option has intrinsic value based on the cost of carry plus strike price representing better value than the current market value of GBP.the buyer may now choose to exercise the option, purchasing the underlier at the strike price. This is performed by accepting or rejecting via the user interface. Exercising the option executes the transaction flows between the buyer and CurrencyShield. 

Option exercised:
•	Buyer’s EUR account debited for cost of carry.
•	CurrencyShield’s EUR account credited cost of carry.
•	CurrencyShield’s GBP account debited agreed strike price.
•	Buyer’s GBP account credited agreed strike price.

Option not exercised:
•	Buyer’s EUR account debited for cost of carry.
•	CurrencyShield’s EUR account credited cost of carry.

CurrencyShield hold Ether to ensure gas is paid for the duration of the contract.


