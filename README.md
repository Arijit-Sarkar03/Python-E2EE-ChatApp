
# 🔐 Secure Chat App (WSS + RSA + PyQt5)

A secure, end-to-end encrypted chat application built with Python using WebSockets over TLS and RSA encryption. The app features a GUI client built with PyQt5 and a robust asyncio-powered server.

## 🚀 Features

- ✅ **WSS (WebSocket Secure)** communication using TLS
- 🔐 **RSA 2048-bit encryption** at the application layer
- 🧑‍💻 **Username-based login** with duplicate check
- 🪪 **Public key exchange** for end-to-end message encryption
- 💬 **Group & private messaging** using `@username` format
- 🖥️ **PyQt5 GUI client** for an intuitive chat experience
- 📜 Server logging for monitoring and debugging

---

## 📁 Project Structure

```
.
├── client.py      # PyQt5-based GUI client
├── server.py      # Async WebSocket server with RSA encryption
├── cert.pem       # TLS certificate (not included here)
├── key.pem        # TLS private key (not included here)
```

## ⚙️ Requirements
Create a Virtual Environment:
```
python3 -m venv <name>

source <name>/bin/activate

to deactivate, run the command:

deactivate
```
Install required Python packages:

```
pip install websockets pyqt5 pycryptodome
```
Note: You will also need a `cert.pem` and `key.pem` for running WSS. You can generate a self-signed certificate using OpenSSL:

```
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes

```

## 🖥️ Running the App
### Start the Server
```
python3 server.py
```
### Launch the Client
```
python client.py
```
You can run multiple instances of client.py to simulate multiple users.
## 💬 Messaging
- Send a normal message → it goes to everyone.

- Send a private message → start your message with @username, e.g.: `@alice Hey, how are you?`

## 🔐 Security Architecture
- TLS (WSS): Ensures encrypted transport layer communication.

- RSA (2048-bit): Each client and the server generate their own key pairs. Public keys are exchanged during the handshake.

- App-Layer Encryption: Messages are encrypted with the recipient’s public key, ensuring only they can decrypt them.

## Debugging
To check if this works or not install `Wireshark` in your system and then run the project, trace the packets while sending the messages
there you should be able to check whether your messages are End-to-End Encrypted or not

## 🛠️ Notes
- This is a demo application and not intended for production use.

- The app currently supports basic messaging and does not store chat history.

- Proper certificate validation is disabled by default for self-signed certs; uncomment validation lines in `client.py` to enforce strict checks.

## 🙌 Credits
Developed with ❤️ using Python, PyQt5, and websockets.
Note: for GUI you can use `Tkinter` module too.

#### made by
- Arijit Sarkar
- Arghadeep Saha
- Sreya Sahoo

Department of `ECE` from `RCC Institute of Information Technology`



