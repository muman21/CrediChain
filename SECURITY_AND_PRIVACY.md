# CrediChain — Security and Privacy Architecture

## 1. Security Objectives

CrediChain is designed around the following security objectives:

- Restrict credential issuance to recognized institutional wallets.
- Maintain tamper-evident academic credential records.
- Protect student information through encryption.
- Enable independent verification.
- Avoid maintaining a centralized database of student academic records.
- Preserve the relationship between credentials and their issuing institutions.

## 2. Institutional Issuer Authorization

The institutional wallet is the primary identity used by the application to recognize an authorized issuer.

When a wallet connects, the application checks whether its address belongs to a registered institution.

Only recognized wallets are permitted to access the credential issuance functionality.

This establishes an issuer authorization layer at the application level.

The intended institutional onboarding model includes official institutional communication and authorization through the relevant national higher-education authority.

## 3. Blockchain-Based Record Integrity

Academic credentials are represented as Algorand Standard Assets.

The blockchain provides a publicly retrievable record of asset creation and associated transactions.

The project uses asset metadata configured to preserve the intended credential information.

The distinction between asset metadata and transaction notes is important:

- Asset metadata is configured as the immutable credential information.
- A transaction note belongs to a particular transaction and cannot be modified after confirmation.
- Future credential updates are designed to be represented by subsequent transactions.

The transaction history can therefore provide a historical record of credential-related operations.

## 4. Encryption of Student Information

Academic information contains personally identifiable and sensitive educational data.

CrediChain does not intend to store student academic information in plaintext on the blockchain.

The current implementation uses AES-256 encryption.

The student's seat number is used as the decryption input.

The encrypted information is associated with the relevant blockchain credential.

During verification, the application retrieves the encrypted information and processes it using the supplied seat number.

This design aims to prevent direct exposure of academic information through ordinary inspection of blockchain records.

## 5. No Centralized Student Database

CrediChain is designed without a centralized backend database storing student academic records.

The institution interacts with Algorand through the CrediChain application.

The credential data is maintained on-chain in encrypted form.

The application provides the interface for credential issuance and verification.

This reduces dependence on a centralized student-record repository and avoids creating a single CrediChain database containing the academic records of participating institutions.

## 6. Verification Access Control

The verification portal does not require a blockchain wallet.

However, access to the credential information requires both:

- The correct Asset ID.
- The corresponding student seat number.

The Asset ID identifies the blockchain credential.

The seat number is used as the decryption input.

If either value is missing or incorrect, the verification process cannot successfully display the academic information.

## 7. Institutional Schema Isolation

Different institutions can have different credential formats.

CrediChain associates institutional configurations with recognized issuer wallets.

During retrieval, the application identifies the issuing wallet and selects the corresponding institutional configuration.

This helps ensure that a credential is processed and displayed using the appropriate institutional structure.

## 8. Transaction History and Future Versioning

The current architecture distinguishes the original credential record from future updates.

The proposed versioning mechanism will use subsequent transactions associated with the same asset.

Each transaction can carry a new version of the credential information.

The historical transactions remain available as part of the blockchain record.

A future verification interface is intended to support original, latest, and historical version selection.

## 9. Future Cryptographic Development

The current implementation uses AES-256 encryption.

Post-quantum cryptography (PQC) is a planned area of further development.

The intention is to investigate cryptographic mechanisms that can provide stronger long-term protection against potential advances in quantum computing.

PQC integration has not yet been implemented.

## 10. Security Considerations and Production Readiness

CrediChain is a deployed prototype demonstrating its proposed credential issuance and verification architecture.

A production deployment involving real universities and large volumes of personal academic information would require further security work, including:

- Independent cryptographic review.
- Secure key derivation and key-management design.
- Institutional wallet governance.
- Issuer authorization procedures.
- Secure handling of institutional credentials.
- Privacy and regulatory compliance assessment.
- Operational monitoring and incident-response procedures.
- Independent smart-contract and application security assessment where applicable.

The current seat-number-based decryption design should be reviewed before production deployment, particularly regarding the predictability and entropy of student identifiers.

The architecture is intended to reduce centralized data exposure, not to claim that all security risks are eliminated.
