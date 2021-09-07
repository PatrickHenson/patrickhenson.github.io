---
layout: post
title: "Super Secret Messages"
tag: [ software ]
description: "Quick python program to encode messages using a substitution cipher."
---

One of the many things I enjoy is playing tabletop RPGs.  Since I wanted to include secret messages containing 
information and clues for players to find I decided to write a quick program to do it for me.  My goal was to easily 
encode messages using substitution ciphers since the result is easy to decipher with or without the key and should be 
a fun puzzle.  

Check my GitHub for the [puzzle_script](https://github.com/PatrickHenson/puzzle_script) repo to use it yourself.

To make the messages feel more immersive, I used a custom font that looked like it would fit in the game's world.  The 
comparison to the latin alphabet can be seen below.  However, it should be noted that a few of the characters 
('a','g','i','q') share traits (backwards 'c') that can make the custom font hard to translate if you're not paying 
attention to small details.
<img src="\images\substitution_cipher\alphabet.jpg" width='550' />

After generating and applying the substitution cipher, the original and encoded message are rendered using the custom 
font as images.  This allows for easy use without needing to install any font files on your computer.

For example, "this is a super secret message" turns into
<img src="\images\substitution_cipher\original_message.jpg" width='500'/>

and substitution cipher output the following encoded string.
<img src="\images\substitution_cipher\encoded_message.jpg" width='500'/>


To encode multiple messages with the same key, puzzle_script takes advantage of the fun truth that "random numbers 
aren't random."  When you run puzzle_script, you can set the random seed to a known value to ensure that the generated 
key is the same.


Finally, every run is summed up in the log file containing ascii output.

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
