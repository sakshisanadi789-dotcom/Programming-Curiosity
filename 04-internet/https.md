# HTTPS

## WHY?
Plain HTTP does not protect traffic against eavesdropping or tampering on the network. HTTPS adds TLS security so clients can authenticate the service and protect data in transit.

## WHAT?
HTTPS is HTTP carried over a TLS-protected connection. TLS provides encryption and integrity, and usually authenticates the server using a certificate that chains to a trusted certificate authority.

## HOW?
During a TLS handshake, client and server agree on cryptographic parameters, verify the server certificate, and establish session keys. HTTP data is then encrypted and integrity-protected with those keys. Modern TLS uses public-key cryptography to authenticate and establish keys, then efficient symmetric cryptography for application data.

## WHERE?
Protection applies between the TLS endpoints. If TLS ends at a reverse proxy or load balancer, traffic from there to another internal service needs its own protection when that network path is not trusted.

## WHEN?
Use HTTPS for websites and APIs, especially whenever credentials, personal data, or session tokens are involved. HTTPS protects data in transit, not data after it is decrypted by the endpoint.

## WHO?
The browser validates the server certificate; the server proves possession of the corresponding private key. Certificate authorities help bind domain names to public keys, while users and operators must keep endpoint software and keys secure.

## WHAT IF?
If certificate validation fails, users should not bypass the warning; the connection may be intercepted or misconfigured. HTTPS cannot make a compromised client or server trustworthy, and it does not hide all metadata such as destination IP addresses.