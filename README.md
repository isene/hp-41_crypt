# hp-41_crypt
## HP-41: Cryptography

**NOTE:** This program is part of the ISENE.ROM (https://github.com/isene/hp-41_isene-rom). The FOCAL listing can be found in the "src" folder of that project. Any updates and new version will be found there.

Introducing encryption to the HP-41

This cryptography program encrypts or decrypts an ascii Extended Memory (XM). Ypou can also temporarily view an encrypted file without substituting the file with the decrypted version.

The CRYP program implements the [Vigenere cipher](http://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher) with a key of your choice of up to 300 characters. By default it uses the range of characters from ascii code 32 (space) to ascii code 90 ("Z"), but you can choose any range above ascii code 32 – for example a range value of 90 to include lower case characters (ascii code 122 is "z").

If the key is at least as long as the file to be encrypted, you will actually get perfect security for the encrypted file. You will have what is known as the [One-time pad](http://en.wikipedia.org/wiki/One-time_pad).

Here are the three functions implemented:

Function	|Description
----------------|-----------
ENCR	|Encrypts an ascii file. The file name must be in Alpha when you execute ENCR. The program first prompts for the character range (default 58 – press R/S to accept the default). It then prompts for the key (Alpha is set to ON). Enter the key to use for the encryption 24 characters at the time. As long as you fill the Alpha register with characters for the key, it will keep asking for more key – until you enter less characters than 24 – then it will commence to encrypt the file. The program resizes the memory to accomodate for a large key if necessary. After encrypting the file with the key, you get the message "DONE" along with a beep. All traces of the key have then been removed. Pressing R/S again will launch the EDitor (ED) with the encrypted file.
DECR	|Decrypts the file (name in Alpha. Prompts for the range and the key (use the same range and the same key as when you encrypted the file. Again you will get a "DONE" and a beep when the process is completed. Pressing R/S again will launch the EDitor (ED) to let you view and edit the decrypted file.
VIEWCR	|Lets you view an encrypted file. Instead of actually decrypting the whole file, you get to view each successive record. The program sounds a Tone 9 upon showing each record. The file remains encrypted in Extended Memory. After the last record is viewed, the program displays "DONE" and gives a beep. All traces of the key is removed.

