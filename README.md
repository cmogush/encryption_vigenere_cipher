# encryption_vigenere_cipher
Program to encrypt and break Vigenère ciphers of any language or key length, both known or unknown

<b>VigenereBreaker</b> - Class that breaks the Vigenere cipher of any key length or language, both known or unknown. Contains the following methods:
* <b>sliceString</b> - has three parameters—a String *message*, representing the encrypted message, an integer *whichSlice*, indicating the index the slice should start from, and an integer *totalSlices*, indicating the length of the key. This method returns a String consisting of every totalSlices-th character from message, starting at the whichSlice-th character.
  * For example:
  * sliceString("abcdefghijklm", 0, 3) should return "adgjm"
  * sliceString("abcdefghijklm", 1, 3) should return "behk"
  * sliceString("abcdefghijklm", 2, 3) should return "cfil"
* <b>tryKeyLength</b> - takes three parameters—a String *encrypted* that represents the encrypted message, an integer *klength* that represents the key length, and a character *mostCommon* that indicates the most common character in the language of the message. Uses the CaesarCracker class, as well as the <b>sliceString</b> method, to find the shift for each index in the key. Returns the key.
* <b>readDictionary</b> - has one parameter—a FileResource *fr*. This method first makes a new HashSet of Strings, then reads each line in *fr* (which should contain exactly one word per line), converting that line to lowercase, and putting that line into the HashSet created. The method then returns the HashSet representing the words in a dictionary. 
* <b>countWords</b> - has two parameters—a String *message*, and a HashSet of Strings *dictionary*. This method splits the message into words (use .split(“\\W+”), which returns a String array), iterate over those words, and sees how many of them are “real words”—that is, how many appear in the *dictionary*. Recall that the words in *dictionary* are lowercase. This method returns the integer *count* of how many valid words it found.
* <b>breakForLaguage</b> - has two parameters—a String *encrypted*, and a HashSet of Strings *dictionary*. This method tries all key lengths from 1 to 100 (using <b>tryKeyLength</b> method to try one particular key length) to obtain the best decryption for each key length in that range. For each key length, the method decrypts the message (using VigenereCipher’s <b>decrypt</b> method), and counts how many of the “words” in it are real words in English, based on the dictionary passed in (using the <b>countWords</b> method). This method figures out which decryption gives the largest count of real words, and returns that String decryption. 
  * Note that there is nothing special about 100, and the program could be modified to iterate all the way to encrypted.length(). Your program would just take a bit longer to run.
* <b>breakVigenere</b> - Creates a new FileResource using its default constructor (which displays a dialog for you to select a file to decrypt). Uses the <b>asString</b> method to read the entire contents of the file into a String. Uses the <b>tryKeyLength</b> to find the key for the message read in. Create a new VigenereCipher, passing in the key that <b>tryKeyLength,</b> finds. Uses the VigenereCipher’s <b>decrypt</b> method to decrypt the encrypted message. Print out the decrypted message!
* <b>mostCommonCharIn</b> - has one parameter—a HashSet of Strings *dictionary*. This method determines which character, of the letters in the language, appears most often in the words in *dictionary*. It returns this most commonly occurring character.
* <b>breakForAllLangs</b> -has two parameters—a String *encrypted*, and a HashMap, called *languages*, mapping a String representing the name of a language to a HashSet of Strings containing the words in that language. Tries breaking the encryption for each language, and see which gives the best results!. Uses the <b>breakForLanguage</b> and <b>countWords</b> methods. Prints out the decrypted message as well as the language identified for the message.

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

<b>Tester</b> - Class to test the classes and methods above.

Links to exercises:
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/od7mx/programming-exercise-known-language-and-key-length
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/B1ENJ/programming-exercise-unknown-key-length
* https://www.coursera.org/learn/java-programming-arrays-lists-data/supplement/e5ZZK/programming-exercise-unknown-language-unknown-key-length
