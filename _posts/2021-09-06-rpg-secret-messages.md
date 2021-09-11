---
layout: post
title: "Super Secret Messages"
tag: [ software ]
description: "Quick python program to encode messages using a substitution cipher."
---

One of the many things I enjoy is playing tabletop RPGs.  Since I wanted to utilize secret messages containing 
information and clues, I decided to write a quick program to do it for me.  This puzzle_script program encodes messages 
using substitution ciphers, which are easy to decipher with or without the key, and should be a fun addition to the 
game.

Check my GitHub for [puzzle_script](https://github.com/PatrickHenson/puzzle_script) to use it yourself.

**The puzzle_script program works as follows:**

1. Read the message to encode from a text file (default is message.txt).

2. Generate the substitution cipher.

3. Apply the cipher to the message.

4. Render the original and encoded message in a custom font.

    * I selected a custom font to make the messages feel more immersive and look unique to fit the game's world.  

    * The comparison to the latin alphabet can be seen below.  It should be noted that a few of the characters 
('a','g','i','q') share traits (backwards 'c') that can make the custom font hard to translate if you're not paying 
attention to small details.
<img src="\images\substitution_cipher\alphabet.jpg" width='550' />

    * The output is stored as image files to allow for easy use without needing to install the font files.  

5. Finally, every run is summed up in the log file containing ascii output.

    * RANDOM SEED - value used to to generate the substitution cipher.

    * MESSAGE - the original message read from the input file.

    * ENCODED MESSAGE - result after applying the substitution cipher.

    * CIPHER KEY - the reversed key to allow for easy translation of the encoded message.


**Additional Functionality:**

For information on input options, refer to the README in the puzzle_script repo.

Most important, you can encode multiple messages using the same key since puzzle_script takes advantage of the fun 
truth that "random numbers aren't random."  By setting the random seed to a known value, you can ensure that the 
substitution cipher applied to the message(s) is the same over multiple runs.

**Example Output:** 

"This is a super secret message" turns into:
<img src="\images\substitution_cipher\original_message.jpg" width='450'/>

the encoded string is:
<img src="\images\substitution_cipher\encoded_message.jpg" width='450'/>
and log.txt contains:

```
## RANDOM SEED ##
6452268133106355826

## MESSAGE ##
This is a super secret message

## ENCODED MESSAGE ##
qdvf vf i fjocp fcnpcq zcffiuc

## CIPHER KEY##
a b c d e f g h i j k l m n o p q r s t u v w x y z 
x k e h f s j d a u o w b c p r t q y n g i v z l m 
```
