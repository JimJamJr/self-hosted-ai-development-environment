# SSH Keys

SSH keys were a simple and effective way of making remote access more secure. This was done by generating an ssh key set on my main PC then sharing the public key to the server. Once I had verified and enabled the ssh key on the server, I could easily access the server remotely from my main PC without needing to use passwords. The security benefits of this is that it is much more secure than using the password which could be bruteforced or leaked. But the main benefit was convenience as I did this early on in the install so that I could continue the install from my main PC via command prompt. 

## How it works

The SSH key concept is quite simple. A public and private key is generated. The private key is retained only on the device the key was generated for. The public key is shared to the device that need to verify the connection. In practice this meant generating a key for my laptop and PC then copying the public keys onto the server. Then when the laptop or PC sends a request to the server, the server challenges the request, which is responded to with a signal encrypted with the private key, then the server verifies the connection by decrypting the signal using the provided public key. Once verified, access is granted. This provides a consistent authentication system which is done device to device without the need for constant password entry.

## Benefits

- Improved security
- Protection against bruteforce attacks
- Industry standard implementation
- Convenience
