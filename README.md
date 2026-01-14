# Surfnet ZK Edge: Zero-Knowledge Primitives on Solana

Welcome to **Surfnet ZK Edge**, a dedicated Solana ephemeral network designed for the [Solana Privacy Hackathon](https://solana.com/privacyhack). This network provides developers with advanced zero-knowledge primitives and privacy-preserving capabilities, pulling real data from mainnet for realistic testing.

## Quick Start

Connect to Surfnet ZK Edge using your favorite Solana SDK:

### Using @solana/web3.js

```javascript
import { Connection, clusterApiUrl } from '@solana/web3.js';

const connection = new Connection('https://zk-edge.surfnet.dev:8899', 'confirmed');
```

### Using @solana/kit

```javascript
import { SolanaKit } from '@solana/kit';

const kit = new SolanaKit({
  rpcUrl: 'https://zk-edge.surfnet.dev:8899'
});
```

### Network Endpoints

**RPC URL:**
```
https://zk-edge.surfnet.dev:8899
```

**WebSocket URL:**
```
wss://zk-edge.surfnet.dev:8900
```

**Explorer:**
```
https://explorer.solana.com/?cluster=zkedge
```

## Overview

Surfnet ZK Edge is an ephemeral Solana network that enables developers to experiment with cutting-edge zero-knowledge proof technologies and privacy-preserving primitives. Built specifically for the Solana Privacy Hackathon, this network provides:

- **Mainnet Data Access**: Real-time data mirroring from Solana mainnet for realistic development
- **ZK Primitives**: Pre-deployed zero-knowledge proof libraries and tooling
- **Privacy Features**: Built-in support for confidential transactions and private state
- **Developer-Friendly**: Free SOL faucet and comprehensive documentation

## Zero-Knowledge Primitives

### Supported ZK Technologies

#### 1. **Groth16 Proofs**
Efficient zero-knowledge proofs perfect for privacy-preserving applications:
- Constant-size proofs (~200 bytes)
- Fast verification times
- Ideal for confidential transactions and private voting

#### 2. **PLONK/PlonKY2**
Universal and flexible ZK-SNARKs:
- Universal trusted setup
- Recursive proof composition
- Great for complex business logic privacy

#### 3. **Bulletproofs**
Range proofs and confidential transactions:
- No trusted setup required
- Compact proofs for ranges and values
- Perfect for confidential asset transfers

#### 4. **ZK-STARKs**
Post-quantum secure zero-knowledge proofs:
- No trusted setup
- Quantum-resistant
- Transparent and verifiable

### Privacy-Preserving Features

- **Confidential Transfers**: Send tokens without revealing amounts
- **Private State**: Store encrypted data on-chain with ZK verification
- **Anonymous Credentials**: Issue and verify credentials without identity disclosure
- **Private Voting**: Conduct governance votes with ballot privacy
- **Shielded Pools**: Mix and anonymize transaction histories

## Use Cases for the Hackathon

### 1. Privacy-Preserving DeFi
Build DeFi protocols that protect user privacy:
- Confidential lending and borrowing
- Private orderbooks for DEXs
- Anonymous yield farming
- Hidden portfolio balances

### 2. ZK-Based Identity
Create identity solutions without compromising privacy:
- Selective disclosure of credentials
- Age verification without revealing birthday
- Proof of solvency without balance disclosure
- Compliance checks with data privacy

### 3. Private Gaming
Implement gaming mechanics with hidden information:
- Fog of war implementations
- Private card games (poker, etc.)
- Hidden player stats and inventories
- Verifiable randomness with privacy

### 4. Confidential Governance
Enable private voting and proposals:
- Anonymous voting with result verification
- Private proposal submission
- Weighted voting without stake disclosure
- Quadratic voting with privacy

### 5. Supply Chain Privacy
Track goods while protecting business secrets:
- Private provenance verification
- Confidential pricing information
- Anonymous quality attestations
- Hidden supplier relationships

## Getting Started

### 1. Get Test SOL

Use the built-in faucet to get test tokens:

```bash
curl -X POST https://zk-edge.surfnet.dev:8899 \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc": "2.0",
    "id": 1,
    "method": "requestAirdrop",
    "params": ["YOUR_WALLET_ADDRESS", 1000000000]
  }'
```

### 2. Deploy a ZK Program

Example using Anchor framework:

```bash
anchor init my-zk-app
cd my-zk-app
anchor build
anchor deploy --provider.cluster https://zk-edge.surfnet.dev:8899
```

### 3. Verify ZK Proofs On-Chain

Use the built-in ZK verification programs:

```javascript
import { PublicKey, Transaction } from '@solana/web3.js';

// Groth16 verifier program
const GROTH16_VERIFIER = new PublicKey('Groth16Verifier111111111111111111111111111');

// Build proof verification transaction
const tx = new Transaction().add(
  // Your proof verification instruction
);
```

## Example Projects

### Confidential Token Transfer

```javascript
// Transfer tokens without revealing amount
const proof = await generateTransferProof({
  sender: wallet.publicKey,
  recipient: recipientPubkey,
  amount: 100, // Hidden from public
  senderBalance: 1000
});

await sendConfidentialTransfer(connection, wallet, proof);
```

### Private Voting

```javascript
// Cast a vote without revealing choice
const voteProof = await generateVoteProof({
  voter: wallet.publicKey,
  proposal: proposalId,
  vote: 'yes', // Hidden
  voterWeight: tokenBalance
});

await castPrivateVote(connection, wallet, voteProof);
```

## Resources

### Documentation
- [Zero-Knowledge Primitives Guide](https://docs.solana.com/zk)
- [Privacy Hackathon Details](https://solana.com/privacyhack)
- [ZK Proof Libraries](https://github.com/solana-labs/zk-libs)

### Tools & Libraries
- [Light Protocol](https://www.lightprotocol.com/) - Private smart contracts
- [Elusiv](https://elusiv.io/) - Privacy layer for Solana
- [ZK Compression](https://www.zkcompression.com/) - Compressed state with ZK proofs

### Examples
- [ZK Voting dApp](https://github.com/solana-labs/zk-voting)
- [Confidential Token Transfers](https://github.com/solana-labs/confidential-spl)
- [Private NFT Marketplace](https://github.com/solana-labs/private-nft)

## Hackathon Support

Building for the Solana Privacy Hackathon? We're here to help!

- **Discord**: [Solana Tech Discord](https://discord.gg/solana)
- **Stack Exchange**: [Solana Stack Exchange](https://solana.stackexchange.com/)
- **Office Hours**: Daily hackathon support sessions
- **Documentation**: [Comprehensive ZK guides](https://docs.solana.com/zk)

## Technical Specifications

- **Network Type**: Ephemeral testnet with mainnet data mirroring
- **Block Time**: ~400ms
- **Max Transaction Size**: 4096 bytes (SIMD-0296 enabled)
- **ZK Proof Verification**: On-chain native support
- **Faucet**: Available for all developers
- **Data Persistence**: Network resets after hackathon

## Contributing

Found an issue or have suggestions? Open an issue or submit a PR:
- [GitHub Repository](https://github.com/txtx/surfnet-zk-edge)

---

**Happy Hacking! Build the future of privacy on Solana. 🔒🚀**
