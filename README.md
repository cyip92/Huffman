Huffman
=======

Dictionary Structure:
- The first 4 bits state the maximum code length in the rest of the dictionary, in terms of the length of its binary representation.  In the worst case, the longest code is 256 bits long; 256 can be expressed in 9 bits, and 4 bits is sufficient to express any number up to 15.
- If we define the number expressed in the first 4 bits as n, then the next 256n bits contain how long each ASCII code representation actually is in codes, in order from 0 to 255.  In typical text files, most of these values will be 0.
- The next part of the file contains all of the codes appended in ASCII order.  If a code is absent from the file, the program will read 0 bits from the stream since that will be recognized in the second step.
- After the dictionary is the actual encoded file, which can be identified without any additional padding since the dictionary has a clear ending; it ends when the code for ASCII 255 is read.

This program was made during my Data Structures and Algorithms class (COMP285 @ University of San Diego).
