# Privacy Hack - Ephemeral Network

Welcome to the **Privacy Hack** ephemeral Solana cluster! This network is dedicated to participants of the [Privacy Hack](https://solana.com/privacyhack) hackathon.

## Cluster URLs

**RPC Endpoint:**
```
https://zk-edge.surfnet.dev:8899
```

**WebSocket Endpoint:**
```
wss://zk-edge.surfnet.dev:8900
```

## Quick Start

### Using @solana/web3.js

```javascript
import { Connection } from '@solana/web3.js';

const connection = new Connection('https://zk-edge.surfnet.dev:8899');
```

### Using @solana/kit

```javascript
import { createSolanaRpc } from '@solana/kit';

const rpc = createSolanaRpc('https://zk-edge.surfnet.dev:8899');
```

### Solana CLI

```bash
solana config set --url https://zk-edge.surfnet.dev:8899
```

## About Privacy Hack

Privacy Hack is a global developer competition focused on building privacy-preserving applications on Solana. The event runs from **January 12-30, 2026** with a **$100,000+ prize pool**.

### Competition Tracks

- **Private Payments** - Build solutions for confidential transfers
- **Privacy Tooling** - Develop infrastructure making privacy easier
- **Open Track** - Build any privacy application on Solana

## Resources

- [Privacy Hack Official Page](https://solana.com/privacyhack)
- [Solana Explorer (Custom Cluster)](https://explorer.solana.com/?cluster=custom&customUrl=https%3A%2F%2Fzk-edge.surfnet.dev%3A8899)
- [Solana Documentation](https://docs.solana.com/)

## Support

Need help? Use the faucet on this page to get test SOL, or reach out to the Solana community on [Discord](https://discord.gg/solana).
