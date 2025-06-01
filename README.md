# Document Certification System using Blockchain

A blockchain-based solution for document certification that ensures authenticity, integrity, and traceability of critical documents.

## Features

- Document hash submission and verification using SHA-256
- Client-side hash computation using Web Crypto API
- Immutable document history with blockchain backing
- Decentralized verification through peer nodes
- Proof of Work consensus mechanism
- Modern web interface with real-time updates
- Support for multiple document types (diplomas, contracts, certificates)

## Technical Architecture

### Backend Components

#### Block Structure
- Index: Sequential block number
- Transactions: List of document certification records
- Timestamp: Block creation time
- Previous Hash: Hash of the previous block
- Nonce: Value used for Proof of Work
- Hash: Current block's hash

#### Blockchain Class
- Implements the core blockchain functionality
- Manages chain of blocks and unconfirmed transactions
- Implements Proof of Work with configurable difficulty
- Provides chain validation and consensus mechanisms

#### API Layer
- Built with Flask framework
- RESTful endpoints for blockchain operations
- Supports peer-to-peer node communication
- Implements consensus algorithm for chain synchronization

### Frontend Components

#### Document Processing
- Client-side SHA-256 hashing using Web Crypto API
- Asynchronous file handling
- Real-time transaction status updates

#### User Interface
- Bootstrap 5.1.3 for responsive design
- Dynamic blockchain visualization
- Real-time transaction monitoring
- Interactive document verification

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the application:
   ```bash
   python app.py
   ```
4. Access the web interface at http://localhost:5000

## API Endpoints

### Document Operations
- `POST /new_transaction`
  - Submit a new document hash
  - Body: `{"document_hash": "<sha256>", "doc_type": "<type>", "timestamp": <unix_time>}`

- `GET /verify_document/<hash>`
  - Verify a document's existence
  - Returns: Document details if found

### Blockchain Operations
- `GET /chain`
  - View the entire blockchain
  - Returns: Chain length and all blocks

- `GET /mine`
  - Mine pending transactions into a new block
  - Implements Proof of Work

### Node Operations
- `POST /register_node`
  - Register a new peer node
  - Body: `{"node_address": "<url>"}`

- `GET /pending_tx`
  - View pending transactions
  - Returns: List of unconfirmed transactions

## Security Features

### Cryptographic Security
- SHA-256 hashing for documents and blocks
- Client-side hash computation for data privacy
- RSA public/private key authentication
- Immutable blockchain structure

### Consensus Mechanism
- Proof of Work with configurable difficulty
- Distributed verification across nodes
- Longest chain consensus rule
- Automatic chain synchronization

### Data Integrity
- Cryptographic linking of blocks
- Transaction verification
- Chain validation on block addition
- Peer node verification

## Limitations

- Only stores document hashes, not actual files
- Basic PoW consensus (may be slow for large-scale use)
- No permanent storage (in-memory blockchain)
- Limited node discovery mechanism

## Future Improvements

### Short-term
- Implement persistent storage using SQLite/PostgreSQL
- Add user authentication and access control
- Enhance error handling and validation
- Improve UI/UX with more interactive features

### Long-term
- Implement Proof of Stake consensus
- Add IPFS integration for document storage
- Develop smart contract functionality
- Create mobile application
- Implement advanced node discovery

## Development

### Requirements
- Python 3.7+
- Flask
- cryptography
- requests

### Testing
Run tests using:
```bash
python -m pytest tests/
```

### Contributing
1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Push to the branch
5. Create a Pull Request

## License

MIT License - See LICENSE file for details
