# encryption_vigenere_cipher
Program to encrypt and break Vigenère ciphers of any language or key length, both known or unknown

<b>VigenereBreaker</b> - Class that breaks the Vigenere cipher of any key length or language, both known or unknown. Contains the following methods:


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
* <b>encrypt</b> - method that takes in a String input and the two alphabets, then uses the <b>transformLetter</b> method to encrypt the String and returns the result.
* <b>decrypt</b> - method that takes in a String input and the two alphabets, then uses the <b>transformLetter</b> method to decrypt the String and returns the result.
* <b>toString</b> - returns a String representing the key for this cipher.

<b>CaesarCracker</b> - Class provides an implementation of the Caesar cipher cracking (or breaking) algorithm.
* The constructor takes a parameter for the most common letter, so it can be used for languages other than English.
* Finding the key has been separated from decrypting the message. Can use the method getKey to pass in an encrypted message and receive the key back.

Contains the following methods:
* <b>CaesarCracker</b> - constructor that sets the public vairable *mostCommon* to *e*
* <b>CaesarCracker</b> - overloaded constructor if a parameter for 1 char *c* is provided, sets the *mostCommon* public variable to *c*.
* <b>countLetters</b> - takes in a String message and counts the number of occurences of each letter in an int[26] array *counts*, returns the result.
* <b>maxIndex</b> - takes in 1 int array parameter *vals*, finds and returns the index of the most occuring letter.
* <b>getKey</b> - takes in 1 parameter, the encrypted String, and returns the decryption key as an int.
* <b>decrypt</b> - takes in 1 parameter, the encrypted String and returns the decrypted String.

<b>VigenereCipher</b> - Class that implements a Vigenère cipher. It contains the following methods:
* <b>public VigenereCipher(int[] key)</b>: the constructor, which takes a key, which is an array of integers and initializes the field ciphers, which is an array of CaesarCipher objects.
* <b>encrypt</b> - method that encrypts a String passed in and returns the encrypted message.
* <b>decrypt</b> - method that decrypts a String passed in and returns the decrypted message.
* <b>toString</b> - returns a String representing the key for this cipher.

Links to exercises:
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/od7mx/programming-exercise-known-language-and-key-length
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/B1ENJ/programming-exercise-unknown-key-length
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/e5ZZK/programming-exercise-unknown-language-unknown-key-length
