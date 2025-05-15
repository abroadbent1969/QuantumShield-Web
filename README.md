# QuantumShield-Web
QuantumShield Web is a browser-based application for securely encrypting and decrypting files using AES encryption with key management features. It supports both password-protected and key-based encryption, with a unique key-splitting mechanism for added security.

Features
File Encryption/Decryption: Encrypt files with AES using either a password or a generated key; decrypt .enc files with the corresponding key or password.

Key Management: Generate, export, import, and rotate encryption keys.

Key Splitting: Encryption keys are split into two parts using XOR for enhanced security; one part is stored locally, the other is downloaded.

Drag-and-Drop Interface: Easily upload files via drag-and-drop or file input.

Password Protection Option: Optionally encrypt files with a password instead of a key.

Tab Navigation: Switch between Encrypt and Decrypt tabs for a streamlined experience.

Prerequisites
A modern web browser (e.g., Chrome, Firefox, Edge).

Internet connection to load the CryptoJS library (https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js).

Setup
Clone or Download:
Download the index.html file or clone this repository.

Host the File:
Place the index.html file on a web server or host it locally. You can use:
A simple local server like python -m http.server 8000 (Python 3).

VS Code's Live Server extension.

Any static hosting service (e.g., GitHub Pages, Netlify).

Open in Browser:
Navigate to the URL where the file is hosted (e.g., http://localhost:8000) or open index.html directly in a browser (note: some features may require a server due to browser security restrictions).

Usage
Encrypt Files:
Go to the "Encrypt" tab.

Drag and drop files into the drop zone or click to select files.

Optionally, enable "Password Protected" and enter a password.

Click "Encrypt Files" to process and download the encrypted .enc files.

Ensure a key has been generated (see Key Management).

Decrypt Files:
Go to the "Decrypt" tab.

Drag and drop .enc files into the drop zone or click to select files.

If the file is password-protected, check "Password Protected" and enter the password.

If using key-based encryption, upload the second key part (.keypart file downloaded during key generation).

Click "Decrypt Files" to process and download the decrypted files.

Key Management:
Generate New Key: Creates a new key pair and splits the private key into two parts; the second part is downloaded as a .keypart file.

Export Public Key: Downloads the public key for sharing.

Import Key: Imports a previously backed-up key using a passphrase.

Rotate Key: Archives the current key and generates a new one.

Security Notes
Key Storage: Keys are stored in the browser's localStorage. Clear your browser data to remove them.

Key Splitting: The private key is split into two parts using XOR. You must provide the second part (.keypart) for key-based decryption.

Double Encryption: Files are encrypted twice (two AES layers) for added security, whether using a password or a key.

Passphrase for Backup: When generating or importing keys, a passphrase is required for backups to prevent unauthorized access.

Limitations
Large files may cause performance issues due to browser memory constraints.

The application relies on localStorage, which may be cleared by browser settings or user actions.

No server-side validation; all operations are client-side.

Requires an internet connection to load CryptoJS unless hosted locally.

Dependencies
CryptoJS - Used for AES encryption and key generation.

Contributing
Feel free to fork this project, submit pull requests, or open issues for bugs and feature requests.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments
Built with CryptoJS for encryption.

Inspired by the need for simple, browser-based file security.


