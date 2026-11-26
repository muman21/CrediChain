# CrediChain — Development Roadmap

## Overview

CrediChain is a deployed prototype for blockchain-based academic credential issuance and verification on Algorand.

The university academic credential module is the primary implemented component.

The roadmap distinguishes between existing functionality, partially implemented areas, and proposed future development.

## 1. Implemented Functionality

### Core Platform

- React-based application.
- Vite-based frontend.
- Netlify deployment.
- Algorand blockchain integration.

### Institutional Issuance

- Institutional wallet connection.
- Registered institutional wallet recognition.
- Restriction of issuance functionality to recognized wallets.
- University academic credential issuance interface.

### Credential Architecture

- ASA-based academic credentials.
- Semester-level credential representation.
- Asset ID-based credential identification.
- Institution-specific credential configurations.

### Batch Issuance

- Algorand transaction grouping.
- Rekeyed-account-based batch issuance design.
- Coordinated issuance of multiple academic credentials.

### Privacy and Verification

- AES-256 encryption.
- Seat-number-based decryption input.
- Blockchain-based credential retrieval.
- Verification without requiring the verifier to connect a wallet.

### Institutional Records

- Excel export of issued credential records.
- Asset ID association with academic records.
- Institution-specific marksheet and degree formats.

## 2. Partially Implemented Functionality

### Multi-Sector Credential Platform

The application includes sections for:

- Universities.
- Schools.
- Skill-development institutes.
- Religious seminaries and madrasas.
- Corporate training and certification.

The university academic credential module is the primary implemented module.

The remaining sectors are currently presented as coming soon.

### Institutional Credential Lifecycle

The semester-level credential model is implemented as the primary academic record structure.

The complete degree aggregation and extended credential lifecycle functionality remain areas for further development.

## 3. Planned Development

### Government and HEC Integration

- Formal institutional onboarding framework.
- Authorization through the relevant national higher-education authority.
- HEC verification portal integration.
- Direct access to CrediChain verification from official government portals.

These integrations depend on formal institutional and government-level approval.

### Credential Versioning

- Subsequent transaction-based credential updates.
- Historical transaction indexing.
- Original credential viewing.
- Latest credential viewing.
- Historical version selection.

### Credential Revocation

- Credential revocation status.
- Revocation information in the verification portal.
- Clear indication of revoked credentials.
- Historical record accessibility.

### Additional Institutional Sectors

- School certificates.
- Technical and vocational qualifications.
- Skill-development certifications.
- Religious seminary qualifications.
- Corporate training and professional certifications.

### Cryptographic Development

- Research into post-quantum cryptography.
- Evaluation of post-quantum encryption approaches.
- Potential integration of PQC mechanisms.

## 4. Long-Term Vision

The long-term objective is to establish a common blockchain-based credential infrastructure that can serve multiple educational and professional sectors.

The platform aims to enable:

- Direct credential issuance by authorized institutions.
- Independent credential verification.
- Reduced dependence on centralized verification intermediaries.
- Greater transparency in institutional credential issuance.
- Portable academic and professional credentials.
- More efficient verification across organizational and geographical boundaries.

## 5. Project Status Statement

CrediChain is currently a deployed prototype with its university academic credential functionality as the primary implemented use case.

The broader multi-sector credential infrastructure, government-level integration, credential versioning, revocation, and post-quantum cryptography remain future development objectives.
