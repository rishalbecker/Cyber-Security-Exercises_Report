# Lab05: Identifying MITM Attacks on GPG Keys (Web of Trust)

## Objective
Understand how key substitution can enable Man-in-the-Middle (MITM) attacks and how fingerprint verification and the Web of Trust help protect against them.

## Key Generation
Generated three GPG identities for the lab:
- Alice: alice@example.com
- Bob: bob@example.com
- Mallory: mallory@example.com

## Fingerprint Verification
Recorded and compared the fingerprints of Alice, Bob, and Mallory.
Bob's fingerprint was checked independently within the local lab.

Bob's fingerprint:
2030 5BDF 10EB 5056 C65D 71D0 4082 0D79 5137 DC95

Fingerprints uniquely identify public keys. If a received key's fingerprint differs from the one independently verified, the key should not be trusted.

## MITM Attack Concept
A Man-in-the-Middle attacker may attempt to replace a recipient's public key with their own while impersonating the recipient. If the sender does not verify the key fingerprint, messages may be encrypted to the attacker's key instead.

The key-substitution and interception steps were analyzed conceptually rather than executed.

## Web of Trust
The Web of Trust allows users to certify keys and establish trust through signatures and trusted relationships. It can help users assess whether a public key belongs to the claimed identity.

## Prevention
- Verify fingerprints through a separate trusted channel.
- Do not blindly trust public keys received through email or other unverified channels.
- Use key signatures and trust relationships appropriately.
- Protect private keys and their passphrases.

## Reflection
GPG encrypts messages using the selected public key, but encryption alone does not prove that the key belongs to the intended recipient. Fingerprint verification helps detect key substitution. The Web of Trust provides an additional mechanism for evaluating key authenticity.

## Conclusion
This lab demonstrated key generation and fingerprint comparison and explored the risks of public-key substitution. Independently verifying fingerprints is an important defense against MITM attacks.
