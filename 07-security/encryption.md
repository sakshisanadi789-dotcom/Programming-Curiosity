# Encryption

## WHY?
Encryption protects information from being understood by parties who do not have the required key. It is used to protect network traffic, stored files, backups, and other sensitive data.

## WHAT?
Encryption transforms plaintext into ciphertext using an algorithm and key; decryption reverses the transformation for an authorized key holder. Encryption differs from hashing, which is designed to be one-way.

## HOW?
Modern systems commonly use public-key cryptography to authenticate parties or establish a shared secret, then symmetric encryption for data. TLS uses this pattern to protect HTTPS traffic and also provides integrity checks. Secure protocols and vetted libraries should be used instead of designing custom cryptography.

## WHERE?
Encryption can protect data in transit between endpoints and data at rest on disks or backups. Protection ends where data is decrypted; applications must also secure memory, access, logs, and keys.

## WHEN?
Encrypt sensitive data when it crosses networks or is stored where unauthorized access is a concern. Choose the protection based on the threat model and applicable requirements; encryption does not replace authorization or backups.

## WHO?
Protocol implementations encrypt and decrypt data; system owners manage keys and certificates; users rely on the endpoints and their configuration. Key management is as important as choosing an algorithm.

## WHAT IF?
If a key is lost, encrypted data may become unrecoverable; if it is stolen, an attacker may decrypt or forge protected data depending on the scheme. Plan key rotation, backups, revocation, and recovery before relying on encryption.