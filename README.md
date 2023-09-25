# caesar_cipher.py

alphabet=['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']

def encryption(plaintext,shiftkey):
    ciphertext=""
    for char in plaintext:                        
        if char in alphabet:
            position=alphabet.index(char)
            newposition=(position+shiftkey)%26
            ciphertext+=alphabet[newposition]
        else :
            ciphertext +=char
    print(f"Here is the text after Encryption :{ciphertext}")
    
def decryption(ciphertext,shiftkey):
    plaintext=""
    for char in ciphertext:
        if char in alphabet:
            position=alphabet.index(char)
            newposition=(position-shiftkey)%26
            plaintext+=alphabet[newposition]
        else:
            plaintext +=char
    print(f"Here is the text after decryption :{plaintext}")


End=False
while not End:
    whattodo=input("Type 'encrypt' for Encryption ,type 'decrypt' for decryption....:\n")
    text=input("Type Your MEssage:\n").lower()
    shift=int(input("Enter Shift key:\n"))
    if whattodo=="encrypt":
        encryption(plaintext=text,shiftkey=shift)
    elif whattodo=="decrypt":
        decryption(text,shift)
    playagain=input("Type 'YES' to Continue , Typr 'No' to EXIT:\n")
    if playagain=='no':
        End=True
        print("Have A Nice Day BYE !")
