# OneStable Bot FAQ

### **1. Identifying and Executing Arbitrage Opportunities with the OneStable Bot**
- **Question:** How does the OneStable Bot identify and execute arbitrage opportunities?
- **Answer:** The bot searches for arbitrage opportunities between DEXes. When it finds an opportunity, the bot submits a transaction to the Fast Lane contract, which takes a flashloan and subsequently executes trades that close the arbitrage opportunity.

### **2. Using a Private Node or Infura with the OneStable Bot**
- **Question:** Can a private node or Infura be used with the OneStable Bot?
- **Answer:** Yes. The bot can use any RPC. This can be edited in the fastlane_bot/config/providers file - search for: self.RPC_URL. Note that some functions require an Alchemy API key, making it necessary unless the functions themselves are modified. These functions are in fastlane_bot/helpers/txhelpers, and include get_access_list, submit_private_transaction, and get_max_priority_fee_per_gas_alchemy.

### **3. Arbitraging Specific Tokens using the OneStable Bot**
- **Question:** How can I search for arbitrage for specific tokens using the OneStable Bot?
- **Answer:** The bot includes two Click Options - flashloan_tokens & target_tokens - that enable searching only pools that include specific tokens. 

### **4. Tax Token Handling in the OneStable Bot**
- **Question:** Can the bot trade tax tokens?
- **Answer:** No. The bot currently does not support tax tokens.

### **5. OneStable Bot as a Web Application**
- **Question:** Can the OneStable Bot operate as a web application?
- **Answer:** The OneStable Bot is not designed as a web app. It functions as a backend framework for identifying and executing arbitrage trades using the Fast Lane smart contract on the blockchain.

### **6. Addressing 'Gas Required Exceeds Allowance' Error in the OneStable Bot**
- **Question:** What steps should be taken if the bot displays a 'gas required exceeds allowance' error during transaction building?
- **Answer:** This error can have several causes, the most common of which is simply that the transaction is expected to revert. Another cause of this can be not having enough ETH on the address used by the bot to execute transactions. 

### **7. Addressing 'Reverted SafeMath: subtraction overflow' Error in the OneStable Bot**
- **Question:** I see the error: "Reverted SafeMath: subtraction overflow" when my bot tries to build a transaction, what's wrong?
- **Answer:** This typically happens due to the a tax token being included in the arbitrage route. Tax tokens are not supported by the bot and transactions that include them will typically fail.  


