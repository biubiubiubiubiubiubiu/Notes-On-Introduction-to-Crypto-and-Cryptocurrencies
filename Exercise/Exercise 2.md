## Exercise 2
1. Why do miners run “full nodes” that keep track of the entire block chain. whereas Bob the merchant can get away with a “lite node” that implements “simplified payment verification,” needing to examine only the last few blocks?
	* **Answer**: Because full node needs to verify the validation of every transactions and there is no guarantee that those blocks indicated in input reside in last few blocks. Therefore, they need to keep track of the entire block chain.

		As for Bob the merchant, because he only needs to see enough confirmations arise in the network to comfirm that the buyer has really paid him the indicated money. And the confirmations reside in the extension of current block chain. Therefore, he only needs to examine last few blocks that contain the information of his related transaction to confidently proceed customers' purchase.
	
2. If a malicious ISP completely controls a user’s connections, can it launch a double‐spend attack against the user? How much computational effort would this take?
	* **Answer**: Though malicious ISP can make the user only hears ISP has paid him money, his double-spent attack may not succeed because his double-spent transaction may become orphan block by other honest nodes. Yes if he controls 51% to make sure his double-spend is proceeded in the longer block-chain

3. Consider Bob the merchant deciding whether or not to accept the C\_A → B transaction. What Bob is really interested in is whether or not the other chain will catch up. Why, then, does he simply check how many confirmations C\_A → B has received, instead of computing the difference in length between the two chains?
	* **Answer**: Because the more times the comfirmation he receives on C\_A -> B, the better chance for this transaction to be proceeded in the long term. And the probability for C\_A -> A being included into the block-chain will drop expotentiallly.

4. Even when all nodes are honest, blocks will occasionally get orphaned: if two miners Minnie and Mynie discover blocks nearly simultaneously, neither will have time to hear about the other’s block before broadcasting hers.  	* What determines whose block will end up on the consensus branch?
		* **Answer**: the longer chain means this block is confirmed by more nodes in the network. In the long term, the block resides in the longer chain will become consensus branch because the probability for finding this chain increases expotentially in the long run.
	* What factors affect the rate of orphan blocks? Can you derive a formula for the rate based on these parameters?
		* **Answer**: by average propagation time for a block and mean block time
		* **Formular**: rate = 1 - e^(-t/T)
	* Try to empirically measure this rate on the Bitcoin network
		* **Answer**: rate = 1 - e^(t / 600)
	* If Mynie hears about Minnie’s block just before she’s about to discover 	hers, does that mean she wasted her effort? 
		* **Answer**: For the current guess, yes. 
	* Do all miners have their blocks orphaned at the same rate, or are some miners affected disproportionately?	
		* **Answer**: For miners controlling higher proportion of computation power, it is more likely for their block to be comfirmed in the long run.

5. How can a miner establish an identity in a way that’s hard to fake? (i.e., anyone can tell which blocks were mined by her.)  
	* **Answer**: Computation power is hard to fake because it is expensive and no meaning for expanding computation power and copy a new identity for new computation power. Therefore, it is hard and meaningless for faking identity based on computation power. Also by use signature, identity is hard to fake on cryptographic level.

6. If a miner misbehaves, can other miners “boycott” her by refusing to build on her blocks on an ongoing basis? 	
	* **Answer**: Yes. Because identities are hard to fake.

7. Assuming that the total hash power of the network stays constant, what is the probability that a block will be found in the next 10 minutes?
	* **Answer**: rate = 1 - (e^-1) = 0.63 		  	 	
8. Suppose Bob the merchant wants to have a policy that orders will ship within x minutes after receipt of payment. What value of x should Bob choose so that with 99% confidence 6 blocks will be found within x minutes?
	* **Answer**: 10 * 6 = 60 min
	
