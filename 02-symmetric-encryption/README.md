# Symmetric Encryption

Symmetric encryption uses the same key for both encryption and decryption. It's fast and efficient, making it ideal for encrypting large amounts of data.

### Example with Python

```python
from Crypto.Cipher import AES
import base64

def encrypt_message(key, raw):
    cipher = AES.new(key, AES.MODE_ECB)
    return base64.b64encode(cipher.encrypt(raw))

def decrypt_message(key, enc):
    cipher = AES.new(key, AES.MODE_ECB)
    return cipher.decrypt(base64.b64decode(enc))

key = b'Sixteen byte key'
message = b'Hello World!!!!!'
encrypted = encrypt_message(key, message)
decrypted = decrypt_message(key, encrypted)

print(f'Encrypted: {encrypted}')
print(f'Decrypted: {decrypted}')
