﻿Over the Wire's **Krypton** Walkthrough by AlbertoSpinella.

Don't be sly! Try to solve the challenges on your own before comparing with my solutions.

# Index
1. krypton 0 -> 1
2. krypton 1 -> 2
3. krypton 2 -> 3
4. krypton 3 -> 4

## krypton 0 -> 1

Find an online tool for decoding from base64. You'll find that the password is `KRYPTONISGREAT`.
Then, run the command:
```
ssh krypton.labs.overthewire.org -p 2231 -l krypton1
```

## krypton 1 -> 2
Run the commands:
```
cd /krypton
ls -la
cd krypton1
cat krypton2
```
Find an online tool for breaking rotation ciphers. You'll find that the result is `LEVEL TWO PASSWORD ROTTEN`. Obviously, the password for krypton 2 is just `ROTTEN`.
Run the command:
```
ssh krypton.labs.overthewire.org -p 2231 -l krypton2
```

## krypton 2 -> 3
Run the commands:
```
cd /krypton/krypton2
ls -la
mkdir /tmp/kry3
cd /tmp/kry3
ln -s /krypton/krypton2/keyfile.dat
chmod 777 .
/krypton/krypton2/encrypt /krypton/krypton2/krypton3
cat ciphertext
```
Using an online tool, break the ciphertext encrypted with ROT(x). Try every x between 0 and 26, and you'll find that the plaintext is `CAESARISEASY`.
Run the command:
```
ssh krypton.labs.overthewire.org -p 2231 -l krypton3
```

## krypron 3 -> 4
