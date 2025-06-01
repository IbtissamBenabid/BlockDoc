# Document Certification System using Blockchain

A blockchain-based solution for document certification that ensures authenticity, integrity, and traceability of critical documents.
following this tutorial : https://www.google.com/url?q=https://web.archive.org/web/20201222142511/https:/developer.ibm.com/technologies/blockchain/tutorials/develop-a-blockchain-application-from-scratch-in-python/%234-implement-a-proof-of-work-algorithm&sa=D&source=apps-viewer-frontend&ust=1748880770513987&usg=AOvVaw03rujBc9TtyltAfaJ3HgsW&hl=fr

## Features

- Document hash submission and verification
- Cryptographic user authentication
- Immutable document history
- Decentralized verification
- Web interface for easy interaction

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

- POST /new_transaction - Submit a new document hash
- GET /chain - View the entire blockchain
- GET /mine - Mine pending transactions
- POST /register_node - Register a new node
- GET /verify_document - Verify a document's existence
- GET /pending_tx - View pending transactions

## Security

- Uses SHA-256 for document and block hashing
- Public/private key authentication
- Proof of Work consensus mechanism
- Distributed verification across nodes

## Limitations

- Only stores document hashes, not actual files
- Basic PoW consensus (may be slow for large-scale use)
- Simple user interface

## Future Improvements

- Implement Proof of Stake consensus
- Add persistent storage
- Enhanced user interface
- File storage integration (IPFS)
