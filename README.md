# FDRN Token Smart Contract
This is the smart contract for the FDRN token, a meme token created on the Ethereum blockchain.

## Token Information
Token Name: Fedron <br>
Token Symbol: FDRN <br>
Decimals: 0 <br>
Total Supply: 8,000,000

## Contract Overview
The contract is based on the ERC20 token standard and includes the following functions:

### ERC20Interface
- **totalSupply()** returns the total supply of the token.
- **balanceOf(address tokenOwner)** returns the balance of the specified address.
- **transfer(address to, uint tokens)** transfers tokens from the sender to the specified address.
- **allowance(address tokenOwner, address spender)** returns the amount of tokens that the spender is allowed to spend on behalf of the owner.
- **approve(address spender, uint tokens)** allows the spender to spend the specified amount of tokens on behalf of the owner.
- **transferFrom(address from, address to, uint tokens)** allows the spender to transfer tokens from the specified address.

### Fedron
This contract implements the ERC20Interface and adds the following functionality:

- **founder** is the address that created the token and holds the initial balance.
- **balances** is a mapping of addresses to their token balances.
- **allowed** is a mapping of addresses to the amount of tokens they are allowed to spend on behalf of the owner.
- **constructor()** initializes the token's total supply and assigns the entire supply to the founder.
- **balanceOf(address tokenOwner)** returns the balance of the specified address.
- **transfer(address to, uint tokens)** transfers tokens from the sender to the specified address.
- **allowance(address tokenOwner, address spender)** returns the amount of tokens that the spender is allowed to spend on behalf of the owner.
- **approve(address spender, uint tokens)** allows the spender to spend the specified amount of tokens on behalf of the owner.
- **transferFrom(address from, address to, uint tokens)** allows the spender to transfer tokens from the specified address.

### FedronICO
This contract extends the Fedron contract and adds an ICO functionality. The ICO allows investors to purchase FDRN tokens by sending Ether to the ICO contract.  It includes the following functions:

- **admin** is the address that manages the ICO.
- **deposit** is the address where the ICO funds will be deposited.
- **tokenPrice** is the price of one token in ether.
- **hardCap** is the maximum amount of ether that can be raised in the ICO.
- **raisedAmount** is the amount of ether that has been raised so far.
- **saleStart** is the timestamp of the start of the ICO.
- **saleEnd** is the timestamp of the end of the ICO.
- **tokenTradeStart** is the timestamp when the tokens become tradable.
- **maxInvestment** is the maximum amount of ether that an investor can invest.
- **minInvestment** is the minimum amount of ether that an investor can invest.
- **State** is an enumeration that defines the different states of the ICO.
- **icoState** is the current state of the ICO.
- **constructor(address payable _deposit)** initializes the ICO parameters.
- **onlyAdmin()** modifier that restricts access to the admin.
- **halt()** function that halts the ICO.
- **resume()** function that resumes the ICO.
- **changeDepositAddress(address payable newDeposit)** function that changes the deposit address.
- **getCurrentState()** function that returns the current state of the ICO.
- **invest()** payable function that allows an investor to invest in the ICO.
- **receive()** payable function that is called when someone sends ether to the contract's address.
- **burn()** function that burns the unsold tokens after the ICO
