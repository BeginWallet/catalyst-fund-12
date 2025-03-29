# Begin Wallet - Milestone 1

## Voting (dApp Rating) Integration in Begin Wallet

**Author:** Francis Luz, CEO

---

## 1. Introduction

The Begin Wallet team has successfully integrated a decentralized application (dApp) rating system in version 1.21.2. This integration enables users to rate dApps within the wallet's ecosystem while ensuring transparency and integrity through an on-chain proof-of-record mechanism.

The key objectives of this implementation include:

- Providing a seamless mechanism for users to rate dApps.
- Storing and indexing ratings efficiently using both off-chain and on-chain components.
- Allowing any wallet or dApp to retrieve and display rating results from on-chain data.

---

## 2. Acceptance Criteria

This milestone is considered successfully achieved if a user of the Begin Wallet (Chrome) can:

1. **Register for Voting**: Register as a voter within the app.
2. **Cast Votes**: Participate in the voting process by casting votes on at least two items, with each vote being recorded.
3. **View Voting Results**: Access and view results of the votes.

---

## 3. Technical Solution

### 3.1 Off-chain Implementation

To ensure efficiency and ease of access, a set of APIs has been developed to:

- Store and index dApp ratings.
- Compute the average rating for each dApp.
- Ensure that each dApp receives only one rating per user, while allowing users to update their ratings over time.
- The basic dApp information is provided by Cardano Cube via API.

### 3.2 On-chain Implementation

To maintain transparency and allow for interoperability across wallets and dApps, the following on-chain mechanisms were implemented:

- **Metadata Label 1668**: Reserved to store proof of rating (vote) on-chain.
- **Batch Voting Support**: Users can rate multiple dApps within a single transaction to optimize network fees.
- **Interoperability**: The rating format enables any wallet or dApp to retrieve and display results from on-chain data.

### Sample On-chain Rating Data Structure

```json
{
    "type": "dapp-rating",
    "uuid": "e9a6237d-e9e6-4fa1-befe-989ac68843e5",
    "origin": "Begin Wallet",
    "ratings": [
        {
            "logo": "https://cdn.cardanocube.com/9592ckvwmp8jmbm3i6xacsrtmuxi",
            "name": "SingularityNET",
            "dappId": "singularitynet",
            "rating": 2,
            "category": "AI"
        },
        {
            "logo": "https://cdn.cardanocube.com/868hamwcp4kqlsfqlm7lgzg1euw3",
            "name": "Pavia",
            "dappId": "pavia",
            "rating": 3,
            "category": "Metaverse"
        }
    ],
    "voterId": "stake1u986aacj5hrl6suhv2zn06zk0pgp8zvjkt7tc38y4nu6fzcsg3cxt"
}
```

---

## 4. Results & Verification

The successful implementation of the dApp rating system was validated through the following:

- **Demo Video**: Demonstrating the rating process and on-chain recording.  
  [YouTube Demo](https://youtu.be/ePJs-wZ6Kjc?si=qVX4zaTbXxWXl9Fa)
- **On-chain Transaction**: Verifying recorded ratings on-chain.  
  [Cardano Explorer Transaction](https://cexplorer.io/tx/f9e94ed3b6cc0d7fa5680ff65944c5215f956a424ae6838c412135bc4822c4ae/metadata#data)
- **CIP-10 Compliance**: Reserved Metadata Label 1668 merged into [CIP-10](https://github.com/cardano-foundation/CIPs/pull/1012).
- **Open-source Repository**: Implementation details and source code available at [GitHub](https://github.com/BeginWallet/catalyst-fund-12).

---

## 5. Conclusion

The dApp rating system integration in Begin Wallet 1.21.2 successfully enhances the user experience by allowing transparent and verifiable ratings. With the combination of off-chain APIs for indexing and on-chain metadata for immutability, this implementation ensures efficiency, cost-effectiveness, and interoperability across the Cardano ecosystem.

Also included:

- Enhanced UI for rating visualization.
- Sort by ranking and filtering options based on category.
- Integration with broader ecosystem partners for increased adoption.

This milestone marks a significant step in decentralized governance and user-driven reputation systems in the Cardano ecosystem.

---

**End of Report**
