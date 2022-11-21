# ClassicCrypto-AffineCipher

## The Affine Cipher

The Affine cipher is a type of monoalphabetic substitution cipher, wherein each letter in an alphabet is mapped to its numeric equivalent, encrypted using a simple mathematical function, and converted back to a letter. The formula used means that each letter encrypts to one other letter, and back again, meaning the cipher is essentially a standard substitution cipher with a rule governing which letter goes to which. 
The whole process relies on working modulo m (the length of the alphabet used). In the affine cipher, the letters of an alphabet of size m are first mapped to the integers in the range 0 … m-1. 

The ‘key’ for the Affine cipher consists of 2 numbers, we’ll call them a and b. The following discussion assumes the use of a 26 character alphabet (m = 26). a should be chosen to be relatively prime to m (i.e. a should have no factors in common with m). 

## How does it work?

Each letter is enciphered with the function (a * x + b) mod 26, where b is the magnitude of the shift. Let’s say we have a word “secret” and we want to encrypt it with a = 5 and b = 7. These numbers are basically the encryption key.

![image](https://user-images.githubusercontent.com/91763346/203161504-aafe4fe7-90b3-4442-8eac-33ba08a2adc7.png)

Now, we have to take the word letter by letter and find the position of every letter in the ABC. Keep in mind that counting starts from 0! All we have to do is substitute these number into the formula. The result will be the position of the encrypted letter in the ABC.


## Encryption

It uses modular arithmetic to transform the integer that each plaintext letter corresponds to into another integer that correspond to a ciphertext letter. 
The encryption function for a single letter is  :

```
 C ( x ) = ( a x + b ) mod m 
modulus m: size of the alphabet (m usually is set to 26)
a and b: key of the cipher.
a must be chosen such that a and m are coprime.
```

## Decryption

In deciphering the ciphertext, we must perform the opposite (or inverse) functions on the ciphertext to retrieve the plaintext. Once again, the first step is to convert each of the ciphertext letters into their integer values. 
The decryption function is  :

```
D ( x ) = a^-1 ( x - b ) mod m
a^-1 : modular multiplicative inverse of a modulo m. i.e., it satisfies the equation
1 = a a^-1 mod m .*
```
* **Finding the Multiplicative Inverse a^-1 (useful when we want to find the key)**

If we find the number x such that the equation is true, then **x** is the **inverse of a**, and we call it **a^-1**. The easiest way to solve this equation is to search each of the numbers 1 to 25, and see which one satisfies the equation : 

```
a * a^-1 = 1
```

If you now multiply x and a and reduce the result (mod 26), you will get the answer 1. Remember, this is just the definition of an inverse i.e. if **a*x = 1** (mod 26), then x is an inverse of a.

* **Example**

![image](https://user-images.githubusercontent.com/91763346/203163228-4abd2168-e459-4fd9-8f55-a5e5335628f2.png)

## Python Implementation
 to be added soon.















