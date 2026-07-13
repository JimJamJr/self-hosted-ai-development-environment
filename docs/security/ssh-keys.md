# SSH Keys

SSH keys provide a secure way of authenticating remote connections between trusted devices without relying on passwords. They are commonly used for administering Linux servers and were an important part of securing remote access to the local AI server throughout this project.

## How it Works

SSH key authentication uses a public and private key pair. The private key is stored securely on the client device, while the public key is copied to the server and added to the user's `authorized_keys` file.

When a connection is made, the server sends a cryptographic challenge which the client signs using its private key. The server then verifies this signature using the stored public key. If the signature is valid, the connection is authenticated without the private key ever leaving the client device.

This provides a secure method of authentication while also removing the need to enter a password every time a trusted device connects to the server.

## Benefits

- More secure than password-based authentication.
- Resistant to brute-force password attacks.
- Industry standard method of securing SSH connections.
- Passwordless access from trusted development devices.
- Well suited to managing remote Linux servers and self-hosted infrastructure.
