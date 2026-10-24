# Authentication

## WHY?
Services need a way to distinguish one account from another so they can provide personalized data and apply account-specific permissions. Authentication answers “who is making this request?”

## WHAT?
Authentication verifies a claimed identity using evidence such as a password, a passkey, a one-time code, or a device credential. A token is a credential that can represent a successful authentication for later requests; it should be protected like a password.

## HOW?
During login, a server checks the submitted proof, usually against a password hash or a public key. On success it may issue a session identifier in a protected cookie or an access token. Later requests present that credential, and the server validates it before associating the request with an account.

## WHERE?
Credentials travel from a client to a service and are verified by an authentication component. Use HTTPS in transit; store session data or token-signing keys in protected server-side systems, not in public source code.

## WHEN?
Authenticate when a feature needs to identify an account. Re-authentication or multifactor authentication may be appropriate for sensitive actions, but authentication alone does not grant permission to every resource.

## WHO?
The user proves control of an account credential; the identity provider or application verifies it; the server validates the resulting session on each relevant request. Account recovery processes must also be designed securely.

## WHAT IF?
If a token is stolen, an attacker may act as its holder until it expires or is revoked. Use short-lived credentials where appropriate, secure cookie settings, rotation and revocation strategies, and never put secrets in URLs or logs.