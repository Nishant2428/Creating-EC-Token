# Educational Certificates Smart Contract

This smart contract is designed to manage educational certificates as tokens on the Ethereum blockchain. The contract allows issuing and revoking certificates for students.

## Features

1. **Public Variables**:
   - `name`: The name of the token ("Educational Certificate Token").
   - `symbol`: The abbreviation of the token ("ECT").
   - `totalSupply`: The total supply of tokens (certificates).

2. **Balances Mapping**:
   - A mapping of addresses to balances, which keeps track of how many certificates each address (student) holds.

3. **Issue Certificate (Mint Function)**:
   - `issueCertificate(address student, uint256 certificateId, string memory courseName)`: This function issues a new certificate to a student. It increments the total supply and the student's balance by 1. It also emits a `CertificateIssued` event.

4. **Revoke Certificate (Burn Function)**:
   - `revokeCertificate(address student, uint256 certificateId)`: This function revokes a certificate from a student. It decrements the total supply and the student's balance by 1, provided the student has at least 1 certificate. It emits a `CertificateRevoked` event.

## Events

- `CertificateIssued(address indexed student, uint256 indexed certificateId, string courseName)`: Emitted when a new certificate is issued.
- `CertificateRevoked(address indexed student, uint256 indexed certificateId)`: Emitted when a certificate is revoked.
