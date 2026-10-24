# Authorization

## WHY?
Knowing an account's identity is not enough; the service must decide what that account may do. Authorization protects data and actions from users who lack permission.

## WHAT?
Authorization is the process of checking whether an authenticated identity may perform a specific action on a specific resource. Roles, attributes, ownership, and policies can all contribute to a decision.

## HOW?
The server checks permissions on every protected operation, using the authenticated identity and the requested resource and action. It should validate inputs and avoid trusting client-supplied role or ownership claims. CORS is a browser cross-origin policy, not authentication or authorization; non-browser clients can call an API regardless of CORS headers.

## WHERE?
Authorization belongs at trusted service boundaries, especially on the server that owns the data. User-interface checks can improve usability, but cannot replace server-side enforcement.

## WHEN?
Check permissions whenever a request reads or changes protected information. Apply least privilege: grant only the access needed, for only as long as needed.

## WHO?
Service owners define policy; server code enforces it; administrators assign roles; users receive access according to policy. Security reviews should include both ordinary and privileged accounts.

## WHAT IF?
If a client changes an API request to name another user's record, the server must deny access unless policy permits it. Missing checks can expose or alter data at scale. Log security-relevant decisions without recording passwords, tokens, or unnecessary personal data.