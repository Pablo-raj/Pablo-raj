def caesar_encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            result += char
    return result

def caesar_decrypt(text, shift):
    return caesar_encrypt(text, -shift)

def main():
    print("Caesar Cipher Program")
    choice = input("Type 'encrypt' to encrypt or 'decrypt' to decrypt: ").strip().lower()
    message = input("Enter your message: ")
    shift = int(input("Enter shift value: "))

    if choice == 'encrypt':
        encrypted = caesar_encrypt(message, shift)
        print("Encrypted message:", encrypted)
    elif choice == 'decrypt':
        decrypted = caesar_decrypt(message, shift)
        print("Decrypted message:", decrypted)
    else:
        print("Invalid choice.")

if __name__ == "__main__":
    main()

