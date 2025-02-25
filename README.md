# ceaser-cipher.py
This is a python script that implements the CEASER CIPHER, a simple encryption technique 

print( "welcome to ceaser cipher program")


def caesar_cipher(text, shift, mode="encrypt"):
    result = ""
    
    if mode == "decrypt":
        shift = -shift  # Reverse shift for decryption
    
    for char in text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            result += char  # Keep non-alphabet characters unchanged
    
    return result

# User Input
mode = input("Enter mode (encrypt/decrypt): ").strip().lower()
message = input("Enter message: ")
shift = int(input("Enter shift value: "))

# Perform Encryption/Decryption
output = caesar_cipher(message, shift, mode)
print(f"Result: {output}")
