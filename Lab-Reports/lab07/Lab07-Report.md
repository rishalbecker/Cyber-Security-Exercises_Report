# Lab07 – Verifying Software Integrity (SHA256 & GPG)

## Objective
Verify software file integrity using SHA256 checksums and GPG signatures, and detect modifications before execution.

## 1. Script Inspection
Inspected install.sh before execution. The script prints a message, creates a src directory, creates run.sh, writes an echo command into it, moves it into src, and runs it. It printed "Hello".

## 2. SHA256 Checksum
Generated a checksum using sha256sum and stored it in install.sh.sha256.

Initial SHA256:
e277935b53a8b2bec27536e89fdfd5e72e67b6b5034ce3d985fef89c70d438e

The checksum check returned:
install.sh: OK

## 3. GPG Signature
Used the existing GPG key to create a detached signature of the checksum file. Verification returned "Good signature", confirming the checksum file's signature matched the signing key.

## 4. Tampering Test
Appended a harmless comment to install.sh. The checksum verification returned FAILED, demonstrating that changes to the file are detected.

The script was restored, and a new checksum was generated. The restored file then returned install.sh: OK.

## 5. Questions
- Script inspection: The script creates and runs a simple demo shell script.
- SHA256: Detects changes to a file by comparing its hash with a recorded hash.
- GPG: Verifies a digital signature associated with a file.
- A checksum alone does not prove who created a file.
- Signing a checksum provides a way to verify the checksum's signature and signer key.
- Modification of the file caused the checksum verification to fail.

## Conclusion
SHA256 checksums help detect file modifications. GPG signatures add a mechanism for verifying the origin of signed data, provided the public key identity is trusted. Software integrity and authenticity should be checked before execution.
