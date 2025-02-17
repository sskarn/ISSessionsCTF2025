This was an interesting challenge, but also one that was a little easier than we thought the more our team spent time on it!

![[image-28.png|647x109]](ShadowShadowShadow/image-28.png)

Once the string above is decoded into base64, it suggests that part of the entire string is able to be decoded, as using the entire string doesn't lead us anywhere. 
![[image-29.png|609x286]](ShadowShadowShadow/image-29.png)

Once we tried this method, we got the following string from base64 decoding: ``YzI5dFluSmg=``:
![[image-30.png|197x249]](ShadowShadowShadow/image-30.png)

Decoding this into base64 will produce an interesting result, sombra
![[image-31.png|196x303]](ShadowShadowShadow/image-31.png)

Upon a quick Google search, sombra is a word that roughly translates to "shadow" from Spanish to English. This fits the theme of this challenge, where the word shadow is repeated. 
![[image-32.png|382x278]](ShadowShadowShadow/image-32.png)

As for the rest of the string given, this looks like this is encoded with something like a vigenere cipher, as the text file mentions this encoding technique in its hint. 

It is also likely that each of the individual strings in the first line represent a different word, as the challenge name itself also has 3 words (that being "shadow shadow shadow") to represent this.

![[image-34.png|395x112]](ShadowShadowShadow/image-34.png)
Upon decoding the first part of the text ``xpeud`` with a brute-force caesar cipher decoder, we could figure out that one of the following texts represents a decipherable word, umbra.  

![[image-33.png|112x377]](ShadowShadowShadow/image-33.png)

It turns out that the word umbra is used to represent the darkest part of a shadow, relating to the prompt of the challenge (We swear we did not think of Bayonetta).  

Now, this leaves us to work with ``vhrnrw`` as the final string of characters to decode. As the hint mentions vigenere cipher (although spelt incorrectly), this string will likely need to be decoded using this method.

Upon trying to automatically decrypt this string without any mention of a key, this search does not lead us to anything related to the information of the challenge. 

With this information, we tried to use a key to decipher this information. With an educated guess, we tried "dark", a synonym of shadow and also mentioned in the definition of umbra. 

After decrypting this text with the key being "dark", the result becomes more interesting.
![[image-35.png]](ShadowShadowShadow/image-35.png)

The final key to this puzzle has been found. We did not expect the word "shadow" be included in the decoded result.

![[image-36.png|558x25]](ShadowShadowShadow/image-36.png)
Now, using the information the provided text gives us about the flag, we have to place a ``_`` between the first and second word, a ``-`` between the second word and third word and then append a ``.`` in the end of the flag.

Using the words in the order:
umbra, shadow, sombra

The flag would be:
``bhbureauCTF{umbra_shadow-sombra.}`` 

The challenges were very fun for our first time at a CTF. Shoutout to the ISSessions CTF 2025 organizers for making this event happen.