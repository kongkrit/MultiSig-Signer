========== {t, n} and {n, n} version =========

I want a product suite consists of 2 pieces of software.
Prefer web-based offline JS (and WASM if necessary) for both A and B. no network access, not even CORS.

A. key gen and split -- input master secret which is already a high entropy 32B hex. use appropriate KDF to derive private key from this secret. output private key as split secrets {t, n}. t parts are required to reconstruct one private key. the private key is never shown. the public key is shown for future use. this app only runs offline. the user discards the master secret after A is finished.

I undestand that the private key will briefly exist in RAM. Suggest a strategy to minimize risk of leak.

B. signer - takes a blob and sufficient number of splits from A. -- and sign the blob with the private key with secure computation, which means private key may never exist in memory or disk. only signature is spit out.

For B, private key must never exist in RAM or disk. B should do a secure computation without ever knowing the private key.

I am willing to settle for split of {n, n} or even {2, 2} if this restriction simplifies A & B significantly. Give recommendations.

C. application of A & B: securely sign bitcoin and (preferred, but not required: lightning) and (totally optional: ethereum, solana) transactions.

D. optionally support QR code scanning (to read message to sign) and show QR for signature.

Question: what network stack do I need if I want app B to get online and sign transactions on blockchains. Is it better to keep B. totally offline?

Question: Can I use B. to create a single wallet on the target chain? Or do I need to create it with A?

show ideas and libraries to build these 2 apps.

========== follow-up ==========

for simplicity, which should i stick with? 1. t < n 2. n of n 3. two of two splits? private key reconstruction in B is always forbidden.

========== {t, n} version ==========

I want a product suite consists of 2 pieces of software.
Prefer web-based offline JS for both A and B. no network access, not even CORS.

A. key gen and split -- input master secret which is already a high entropy 32B hex. use appropriate KDF to derive private key from this secret. output private key as split secrets {t, n}. t parts are required to reconstruct one private key. the private key is never shown. the public key is shown for future use. this app only runs offline. the user discards the master secret after A is finished.

I undestand that the private key will briefly exist in RAM. Suggest a strategy to minimize risk of leak.

B. signer - takes a blob and sufficient number of splits from A. -- and sign the blob with the private key with secure computation, which means private key may never exist in memory or disk. only signature is spit out.

For B, private key must never exist in RAM or disk. B should do a secure computation without ever knowing the private key.

C. application of A & B: securely sign bitcoin and (preferred, but not required: lightning) and (totally optional: ethereum, solana) transactions. how hard is it to add QR code scanning (to read message to sign) and show QR for signature?

Can I use B. to create a single wallet on the target chain? Or do I need to create it with A?

show ideas and libraries to build these 2 apps.

========== {n, n} version ==========

I want a product suite consists of 2 pieces of software.
Prefer web-based offline JS for both A and B. no network access, not even CORS.

A. key gen and split -- input master secret which is already a high entropy 32B hex. use appropriate KDF to derive private key from this secret. output private key as split secrets {n}. All n parts are required to reconstruct one private key. the private key is never shown. the public key is shown for future use. this app only runs offline. the user discards the master secret after A is finished.

I undestand that the private key will briefly exist in RAM. Suggest a strategy to minimize risk of leak.

B. signer - takes a blob and sufficient number of splits from A. -- and sign the blob with the private key with secure computation, which means private key may never exist in memory or disk. only signature is spit out.

For B, private key must never exist in RAM or disk. B should do a secure computation without ever knowing the private key.

C. application of A & B: securely sign bitcoin and (preferred, but not required: lightning) and (totally optional: ethereum, solana) transactions. how hard is it to add QR code scanning (to read message to sign) and show QR for signature?

Can I use B. to create a single wallet on the target chain? Or do I need to create it with A?

show ideas and libraries to build these 2 apps.
