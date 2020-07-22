# encryption_vigenere_cipher
Program to encrypt and break Vigenère ciphers

Can break Vigenère ciphers of any language or key length, both known or unknown.

<b>CaesarCipher</b> - Class provides an implementation of the Caesar cipher algorithm with public encrypt and decrypt methods.
* uses object-oriented design, in which the constructor takes the key.
* provides public methods to encrypt or decrypt one single character <b>encryptLetter</b> and <b>decryptLetter</b>.
* In the constructor, the alphabets are built to have upper- and lowercase letters to preserve the case of a message.

Contains the following methods:
* <b>CaesarCipher</b> - constructor method to initial the *key*, *alphabet*, and *shiftedAlphabet* variables.
* <b>transformLetter</b> - helper method that takes in a character *c* and two strings *from* and *to*, used to transform the letter from the *alphabet* to the *shiftedAlphabet*.
* <b>encryptLetter</b> - takes in a character *c* and returns the encrypted letter, with help from the *transformLetter* method.
* <b>decryptLetter</b> - takes in a character *c* and returns the decrypted letter, with help from the *transformLetter* method.
* <b>transform</b> - takes in a String input and two other Strings (the alphabet the input is taken from, and the alphabet it is being transformed to), uses the <b>transformLetter</b> method to encrypt or decrypt the entire String and returns the result.
* <b>encrypt</b> - simple method that takes in a String input and the two alphabets, then uses the <b>transformLetter</b> method to encrypt the String and returns the result.
* <b>decrypt</b> - simple method that takes in a String input and the two alphabets, then uses the <b>transformLetter</b> method to decrypt the String and returns the result.
* <b>toString</b> - common method to return the key as a String.

<b>CaesarCracker</b> - Class provides an implementation of the Caesar cipher cracking (or breaking) algorithm.
* The constructor takes a parameter for the most common letter, so it can be used for languages other than English.
* Finding the key has been separated from decrypting the message. Can use the method getKey to pass in an encrypted message and receive the key back.
