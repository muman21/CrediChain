# CrediChain — Issuance and Verification Workflows

## 1. Institutional Registration

Every participating institution is associated with an authorized Algorand wallet.

The registration model establishes a relationship between the institution and its blockchain identity.

### Registration Process

1. The institution approaches CrediChain through official institutional communication.
2. The institution's identity and authorization are established through the intended onboarding framework.
3. An institutional wallet is associated with the university.
4. The wallet is registered in the CrediChain application.
5. The university appears in the registered-institution directory.
6. The wallet address can be publicly associated with the institution through its official channels.

The intended long-term model includes authorization through the relevant national higher-education authority.

Formal government-level authorization and HEC integration are future objectives.

## 2. Wallet Connection and Recognition

The institutional administrator connects the university's wallet through the application.

The application checks the connected address against its registered institutional wallets.

### Recognized Wallet

- The wallet is identified as belonging to a registered institution.
- Credential issuance functionality becomes available.
- The administrator can proceed with the academic credential workflow.

### Unrecognized Wallet

- The wallet is identified as unrecognized.
- Credential issuance remains disabled.
- The connected user cannot mint credentials through the application.

This prevents arbitrary wallet holders from using the institutional issuance interface.

## 3. Semester Result Issuance

The university administrator selects the academic credential issuance functionality.

The semester result information is prepared for issuance.

The information may include:

- Student name.
- Student seat number.
- Department.
- Academic program.
- Semester.
- Subject details.
- Marks and related academic information.

The credential information is encrypted before being associated with the blockchain asset.

Each semester result is represented by an individual ASA.

## 4. Batch Issuance

Instead of issuing every student credential through an independent operation, CrediChain supports batch issuance.

The implementation uses Algorand transaction grouping and rekeyed accounts.

Algorand supports atomic transaction groups of up to 16 transactions.

The batch architecture allows institutions to issue multiple student credentials together.

### Benefits

- More efficient issuance of large student batches.
- Reduced repetitive signing operations.
- Coordinated issuance of semester results.
- Easier identification of credentials belonging to the same issuance batch.
- Lower transaction overhead through grouped transactions.

The batch issuance design is particularly useful for universities processing an entire semester's results.

## 5. Issuance Record Export

After the issuance process, the institutional administrator can download an Excel record of the issued credentials.

The record includes relevant academic information and the corresponding Asset IDs.

The institution can retain this record in its own administrative environment.

The Asset IDs can be printed on physical marksheets and academic documents.

This provides a reference between the physical document and its blockchain credential.

## 6. Final Degree Credential

Semester results are issued separately.

When a student completes the academic program, the relevant semester Asset IDs can be supplied to the degree credential process.

The final degree credential is designed to reference the student's semester-level academic records.

This provides a relationship between the final qualification and its underlying academic history.

## 7. Credential Verification

Credential verification is designed to work without requiring the verifier to connect a blockchain wallet.

The verifier needs two pieces of information:

1. Credential Asset ID.
2. Student seat number.

### Verification Sequence

1. The verifier opens the CrediChain verification portal.
2. The Asset ID is entered.
3. The student's seat number is entered.
4. The application retrieves the corresponding blockchain information.
5. The issuing wallet is identified.
6. The application selects the corresponding institution-specific configuration.
7. The encrypted academic information is retrieved and processed.
8. The relevant credential is displayed for verification or printing.

If the Asset ID or seat number is incorrect or missing, the credential cannot be successfully retrieved and displayed through the verification process.

## 8. Institution-Specific Document Generation

Different universities may use different academic document formats.

CrediChain maintains separate institutional configurations within the application.

When an Asset ID is submitted:

1. The application identifies the issuing wallet.
2. The issuing wallet is mapped to its registered institution.
3. The institution-specific configuration is selected.
4. The relevant marksheet or degree structure is loaded.
5. The credential is displayed using the appropriate institutional format.

This allows different universities to use the same verification infrastructure without requiring identical document templates.

## 9. Multiple Semester Verification

Semester marksheets are represented by separate assets.

A verifier checking a complete academic history may therefore need the relevant Asset IDs for the individual semesters.

The final degree credential can be retrieved through its own Asset ID.

This provides separate verification paths for:

- Individual semester results.
- Complete academic history.
- Final degree credentials.

## 10. Planned Credential Versioning

Credential versioning is a planned enhancement.

The proposed model uses subsequent Algorand transactions associated with the credential asset.

The original transaction contains the original credential information.

If a correction is required, a new transaction can be created containing the updated information.

The original transaction is not modified.

Instead, the transaction history provides a record of successive versions.

The planned verification interface will allow users to:

- View the original credential.
- View the latest credential.
- Review available historical versions.

## 11. Planned Credential Revocation

Credential revocation is also a planned enhancement.

If a credential becomes invalid, the proposed system will provide a revocation status.

The verification interface will communicate the revoked status to the verifier or student.

Historical credential information will remain distinguishable from the current validity status.
