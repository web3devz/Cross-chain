## Overview
Bonvo provides a decentralized platform for creating and managing unique experiences through NFTs. This system enables users to purchase, validate, and review experiences using blockchain technology.

## Experience Creation (Blue Flow)
1. The Bonvo Platform mints a new NFT with experience metadata into the Bonvo Experiences Collection.
2. This NFT is designed to receive Soulbound Reputation Badges from experience participants.
3. In parallel, the platform deploys an entirely new Collection using the Experience Deployer. This is required due to EVM chain size limitations.
4. The new contract serves as a collection of NFTs exclusively for that experience, where each NFT represents a ticket for a specific date.
5. Both the experience NFT and the ticket collection are owned by the experience creator.

## Ticket Purchase & Validation (Red Flow)
1. The platform keeps track of ticket contracts associated with each experience to facilitate buyer interactions.
2. When a user purchases N tickets, N NFTs are minted on the collection and assigned to the buyer.
3. The ticket owner must validate their ticket upon arrival at the experience location by providing a one-time memo.
4. The experience creator verifies the memo and grants access to the ticket holder.
5. The ticket is no longer usable after validation but remains as proof of attendance.

## Reputation Badges (Green Flow)
1. After using a ticket, the holder can issue a reputation badge to the linked experience NFT.
2. This badge serves as an indicator of the experience's quality (positive or negative).
3. The badge functionality and charging tokens for ticket purchases are pending implementation on the contract side. Other flows are complete.

## Relay Chain Calls
Bonvo integrates with the relay chain to allow interaction with the Bonvo Experiences contracts. Currently, two steps are implemented:
- Approving ERC20 tokens
- Registering a new user

### Process:
1. Build the EVM transaction data.
2. Construct an XCM message to withdraw DEV tokens, purchase execution, and run the EVM transaction.
3. Sign and send from the relay chain using Polkadot.js or Talisman. Additional wallets will be supported in the future.

### Future Enhancements
- Implementation of badge functionality and token-based ticket purchases.
- Expansion of relay chain operations to support all platform features.
- Full usability from both EVM and the Relay Chain.



