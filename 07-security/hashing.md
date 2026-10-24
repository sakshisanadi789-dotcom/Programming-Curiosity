# Hashing

## WHY?
Services need to verify passwords without keeping a directly reusable copy of each password. Hashing also supports integrity checks and data structures, though these uses need different algorithms and assumptions.

## WHAT?
A cryptographic hash maps input data to a fixed-size digest. It is designed to be one-way, but a fast general-purpose hash is not suitable by itself for password storage because attackers can test guesses quickly.

## HOW?
For passwords, store a unique random salt with the result of a deliberately slow, memory-hard password-hashing function such as Argon2id, scrypt, or bcrypt, using a suitable work factor. At login, hash the candidate with the stored parameters and compare safely. Never encrypt passwords when verification can use password hashing, and do not use plain SHA-256 alone for password storage.

## WHERE?
Password hashes and salts belong in a protected authentication database. Hashes are not plaintext, but a stolen hash database still gives attackers material for offline guessing, so it must be protected.

## WHEN?
Use a password-hashing function when storing passwords for later verification. Use other cryptographic hashes for tasks such as content identifiers or integrity checks only when their security properties match the task.

## WHO?
The application generates salts and hashes; the authentication service verifies login attempts; cryptographic libraries implement the algorithms. Security teams set parameters and update them as hardware and standards evolve.

## WHAT IF?
If an attacker obtains hashes, unique salts prevent precomputed tables from being reused across accounts, and slow hashing raises the cost of guessing. Weak passwords can still be guessed; multifactor authentication, rate limits, monitoring, and password resets provide additional defenses.