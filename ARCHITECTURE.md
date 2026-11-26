# CrediChain — System Architecture

## 1. Overview

CrediChain is designed as a decentralized academic credential issuance and verification system built on Algorand.

Its architecture separates institutional authorization, credential issuance, blockchain record storage, encryption, and credential verification.

The primary architectural objective is to allow authorized educational institutions to issue academic credentials directly on-chain while enabling independent verification without maintaining a centralized student-record database.

## 2. Architectural Components

The system consists of the following major components:

1. Institutional issuer wallets.
2. CrediChain frontend application.
3. Algorand blockchain.
4. ASA-based credential records.
5. Encrypted academic information.
6. Institution-specific credential configurations.
7. Credential verification interface.
8. Transaction history and indexing.

## 3. Institutional Issuer Model

Each participating university is associated with an institutional wallet.

This wallet acts as the institution's recognized blockchain identity within CrediChain.

The application maintains the association between institutional wallets and their corresponding university configurations.

When a wallet connects:

- The application checks whether the address is registered.
- A recognized address is permitted to access issuance functionality.
- An unrecognized address cannot mint credentials.

The registered university directory provides public visibility into participating institutions and their associated wallet addresses.

The proposed institutional onboarding process involves official communication and authorization through the relevant national higher-education authority.

## 4. Credential Representation

Academic credentials are represented as Algorand Standard Assets.

Each semester result is represented by a separate asset.

This approach provides a modular credential structure in which individual semester records can be independently retrieved and verified.

The final degree credential is designed to reference the relevant semester credentials.

### Example

A student completing an eight-semester degree may have:

- Eight individual semester-result assets.
- One final degree credential.

The Asset ID provides a unique reference to the corresponding on-chain asset.

## 5. On-Chain Architecture

The blockchain layer is responsible for maintaining the credential records and their associated transaction history.

The design separates the following information:

### ASA Metadata

The asset metadata contains the credential information intended to remain immutable under the project's asset configuration.

### Transaction Note

The transaction note is associated with an individual Algorand transaction.

The note is not editable after confirmation.

For the planned credential-versioning model, an updated credential would be represented through a new transaction associated with the asset, containing the new credential information.

The original transaction and its note remain part of the historical record.

## 6. Off-Chain Application Architecture

The CrediChain application provides the interface through which institutions issue credentials and verifiers retrieve them.

The application is designed without a centralized backend database storing student academic records.

Institution-specific credential configurations are maintained separately in the application.

These configurations contain the relevant information required to generate the appropriate semester marksheet and degree formats for each institution.

When an Asset ID is submitted, the application identifies the issuing wallet and selects the associated institutional configuration.

## 7. Batch Issuance Architecture

CrediChain uses Algorand transaction grouping and rekeyed accounts to support batch issuance.

Algorand atomic transaction groups support up to 16 transactions per group.

The rekeying mechanism is incorporated into the project's batch issuance design to facilitate transaction authorization.

This approach allows institutional administrators to process large groups of student credentials more efficiently.

The design aims to:

- Reduce repetitive signing operations.
- Coordinate issuance of semester results.
- Improve institutional issuance efficiency.
- Reduce transaction overhead.

## 8. Encryption Architecture

Student academic information is encrypted using AES-256 before being included in the credential data.

The student's seat number is currently used as the decryption input.

The encrypted information is associated with the blockchain credential.

During verification, the application retrieves the encrypted record and processes it using the supplied seat number.

The design avoids storing personal academic information in plaintext on the blockchain.

## 9. Verification Architecture

The verification application accepts an Asset ID and student seat number.

The verification process follows this sequence:

1. Receive the Asset ID.
2. Retrieve the associated asset and transaction information.
3. Identify the issuing wallet.
4. Match the wallet to the institution.
5. Load the institution-specific credential configuration.
6. Retrieve the encrypted academic information.
7. Process the information using the supplied seat number.
8. Display or generate the corresponding academic document.

The verifier does not need to connect a blockchain wallet.

## 10. Institutional Configuration Mapping

Each registered university can have its own credential structure.

The application maintains separate configurations for different institutional formats.

These configurations may include:

- University identity.
- Department.
- Academic program.
- Semester information.
- Subject names.
- Marks and grading details.
- Degree and marksheet layouts.

The issuing wallet provides the association used to select the relevant institutional configuration.

## 11. Architectural Design Principles

The architecture is based on the following principles:

- Authorized institutional issuance.
- Blockchain-based credential records.
- Encrypted personal information.
- Independent credential verification.
- No centralized student-record database.
- Modular semester-level credentials.
- Institution-specific document structures.
- Historical transaction traceability.

## 12. Current Limitations and Future Extensions

The current implementation primarily supports the university academic credential module.

The following architectural extensions remain planned:

- Government-level institutional authorization.
- HEC verification portal integration.
- Credential editing and version selection.
- Credential revocation.
- Expanded institutional modules.
- Post-quantum cryptography integration.
