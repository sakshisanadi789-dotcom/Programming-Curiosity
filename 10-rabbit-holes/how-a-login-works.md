# How a Login Works

## WHY?
Login lets a service associate later actions with an account and apply that account's permissions. A password is one possible proof of identity, not the identity itself.

## WHAT?
A login flow collects an account identifier and proof, verifies them, then establishes an authenticated session. The service should store a password hash rather than the plaintext password and should issue a protected session credential after successful verification.

## HOW?
1. The client sends the login request over HTTPS, which protects credentials in transit between TLS endpoints.
2. The server finds the account record and verifies the submitted password using the stored salt and password-hashing parameters.
3. If verification succeeds, the server creates a session or signs a short-lived token. A browser commonly receives a session cookie with security attributes such as `Secure`, `HttpOnly`, and an appropriate `SameSite` setting.
4. The browser sends the session credential with later requests. The server validates it, identifies the account, and separately checks authorization for the requested action.
5. The server returns a response; the client displays success or a useful error without exposing secrets.

## WHERE?
The password is transmitted from the client to the authentication endpoint over TLS and verified by trusted server code. The server stores a salted password hash in a protected database; session state or signing keys are held in server-side storage. The exact design depends on the identity system.

## WHEN?
Authentication happens at login and session validation happens on later protected requests. Sessions expire or are revoked according to policy; sensitive actions may require a fresh login or additional verification.

## WHO?
The user supplies the credential; the browser protects and transmits it; the authentication service verifies it; the session system maintains continuity; and authorization logic decides which actions the account may perform.

## WHAT IF?
Wrong credentials should produce a safe failure without revealing whether an account exists. If a password database leaks, strong salted password hashing raises the cost of guessing but cannot make weak passwords safe. If a session token is stolen, an attacker may reuse it, so protect cookies, avoid logging tokens, and provide expiry and revocation. HTTPS does not protect a compromised endpoint or a maliciously modified application.