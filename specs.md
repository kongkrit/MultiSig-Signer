I want a product suite consists of 2 pieces of software

A. key gen and split -- input master secret which is already a high entropy 32B hex. use appropriate KDF to derive private key from this secret. output private key as split secrets n ways. all n parts are required to reconstruct the private key. the private key is never shown. the public key is shown for future use. this app only runs offline. the user discards the master secret after A is finished.

B. signer - takes a blob and sufficient number of splits from A. -- and sign the blob with the private key with secure computation, which means private key may never exist in memory or disk. only signature is spit out.

Prefer web-based offline JS for both A and B. no network access, not even CORS.

C. application of A & B: securely sign bitcoin and (preferred, but not required: lightning) and (totally optional: ethereum, solana) transactions. how hard is it to add QR code scanning (to read message to sign) and show QR for signature?

show ideas and libraries to build these 2 apps.