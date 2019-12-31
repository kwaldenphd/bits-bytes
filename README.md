# Bits, Bytes, and Basics: Binary math and encoding schema lab

This tutorial was written by [Lindsay K. Mattock](http://lindsaymattock.net) and adapted by [Katherine Walden](https://github.com/kwaldenphd). 

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.


In this lab, we are going to explore how information is represented in binary code. Binary code is the machine code or machine language. These are the 1’s and 0’s that represent the bits and Bytes that make up computer programs or the data processed by the computer. Everything that you see on your computer screen can be reduced to binary code, although most users of computers have few reasons to interact with the computer at this level. This will be one of the rare times when you will manipulate binary data, but this project provides an opportunity to further explore the relationship between what you seen on the screen and what is going on inside the machine.

## Lab Objectives

By the end of this lab you will be able to:
-	Calculate the value of Bytes using binary addition
-	Read a binary clock
-	Explain how text and color are represented in binary
-	Use a hex editor to manipulate binary code
-	Define the relationship between the logical, physical, and conceptual facets of a digital object

## Acknowledgements

This lab is based on the "Project 1: Binary, Bits, and Basics" project materials developed by [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

## Overview of Key Concepts

Librarians, archivists, and information professionals who work in digital preservation often think of digital technologies and digital objects as incorporating three layers: the physical object, the logical object, and the conceptual object. The following definitions are taken from UNESCO’s Guidelines for the Preservation of Digital Heritage, page 35 (available at http://unesdoc.unesco.org/images/0013/001300/130071e.pdf).

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_1.jpg?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_1.jpg?raw=true" /></a></p>

"As physical objects, consisting of ‘inscriptions’ (usually binary states of ‘on-ness’ or ‘off-ness’) on carrier media such as computer disks or tapes. (Despite the impression of that they exist in ‘cyberspace’, even online resources must exist on physical carriers somewhere)”

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_2.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_2.png?raw=true" /></a></p>

"As logical objects consisting of computer readable code, whose existence at any particular time depends on the physical inscriptions but is not tied to any particular carrier”

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_3.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_3.png?raw=true" /></a></p>

"As conceptual objects that have meaning to humans, unlike the logical or physical objects that encode them at any particular time. (This is recognisable as the performance presented to a user)”

This lab will explore the relationship between the logical and conceptual object – the bits and bytes that the computer translates into the representations of information on the screen that we can understand.

# Bits

## What is a bit?

As you read in Petzold this week, bits are the smallest unit of storage in a binary system - that is, the smallest unit of information processed by a computer. Information is stored as 0 or 1. You are probably more familiar with the term Byte – a group of 8 bits.

Kilobyte KB = 1,000 Bytes 
Megabyte MB = 1 million Bytes 
Gigabyte GB = 1 billion Bytes 
Terabyte TB = 1 trillion Bytes

1. One bit gives us two patterns: `1 and 0`. 

2. 2 bits allow for four patterns: `00, 11, 01, 10`. 

3. Every time we add one bit to the length of our bitstring, we double the number of available patterns. 

4. So, 8 bits or 1 Byte provides a means for representing 256 different patterns, as illustrated in this chart:

1 bit – 2 patterns (21)
2 bits – 4 (22)
3 bits – 8 (23)
4 bits – 16 (24)
5 bits – 32 (25)
6 bits – 64 (26)
7 bits – 128 (27)
8 bits – 256 (28)
n bits -  2n patterns

## Representing Numbers in Bytes

5. Some of the first computers were calculators, so we’ll start with numbers. If 8 bits or 1 Byte provides 256 patterns, then we can represent 256 numbers in binary. So, how does this work? To start, in binary math a 1 has a value or is “on” while a 0 does not have a value or is “off.”

<blockquote>Q1: If 8 bits or 1 Byte can represent 256 patterns, what is the range of positive integers that can be represented in a single Byte? (e.g. 1-10)</blockquote>

6. Following the logic from the chart in section 1, each bit represents 2<sup>n</sup> power. 

7. In binary math we move from right to left, growing exponentially as we go. Each n grows by one representing the growth in the number of “bits” of information we can encode. 
  * (Reminder: Anything to the power of “0” = 1) 

8. The following illustrates how you would calculate the value of the Byte `11111111`. 

9. Starting on the left our first 1 represents 20 or 1, the second 21 or 2, and so on until we reach our eighth 1 which equals 27 or 128. 

10. To calculate the total value of this Byte, you add up all of the orange numbers.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_4.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_4.png?raw=true" /></a></p>

<blockquote>Q2: What is the sum of 1+2+4+8+16+32+64+128? Given the total, do you need to revise your response to Q1?</blockquote>

<blockquote>Q3: Using the diagram above, what would a Byte representing the number 0 look like?</blockquote>

11. Now let’s do some basic binary math. Consider the Byte `00010101`. How do we convert this to a number?

12. In this case, the `0s = 0`. Remember, `0` = off. The 1s will have a value. So, to calculate the value of this Byte we carry down the value of each of the `1`s in the bitstring starting on the right and working to the left.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_5.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_5.png?raw=true" /></a></p>

13. So, this Byte has the value of 16 + 4 + 1 or 21.

<blockquote>Q4: Using the same logic, calculate the value of the Byte <code>01101101</code>.</blockquote>

<blockquote>Q5: Now try working the other way. How would you represent the decimal number 40 in binary? (Hint: this doesn’t involve any advanced math, take a look at the orange numbers in the diagram above.)</blockquote>

14. You can check your answers with the Decimal – Hexadecimal – Binary Conversion Table at https://www.eecis.udel.edu/~amer/CISC651/ASCII-Conversion-Chart.pdf. For now, look at the Decimal column for your number and the Binary column for the correct binary representation.

15. You can also add, subtract, divide, and multiply in binary, see http://academic.evergreen.edu/projects/biophysics/technotes/misc/bin_math.htm

## Reading a Binary Clock

16. Now that you understand the basics of binary addition, you can read a binary clock. A binary clock only requires a few bits to represent each of the numbers in a traditional HH:MM:SS representation of time.

17. The diagram from the previous example is flipped on its side, so that the bits are added from bottom to top rather than right to left. From top to bottom each bit grows exponentially, as with our previous 8 bit example.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_6.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_6.png?raw=true" /></a></p>

18. So, if we wanted to represent the time 9:10:25 AM, it would look like this (orange = on or 1, black = off or 0:

19. In the example above, the first digit of the hours has no bits “on” so the total is 0. In the second, the first and fourth are on representing 1 and 8, so we add these together to total 9. The one bit of the first minutes position is on for the 1 in our 10, the second is off for the 0 in the 10. 

20. In the first seconds column the second bit is on representing 2. And, in the final column the first and third bits are on, representing 1 and 4 to total to 5.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_7.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_7.png?raw=true" /></a></p>

21. Binary clocks typically represent Military or 24-hour time (for a chart see: http://militarytimechart.com/), so 9:10:25 PM would be represented as 21:10:25, like this:

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_8.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_8.png?raw=true" /></a></p>

22. Check out http://binary.onlineclock.net/ to see a binary clock in action.

<blockquote>Q6: In your own words, explain why we only need 4 bits for the second digit of the hours, minutes, and seconds; 3 bits for the first digit of the seconds and minutes; and 2 bits for the first digit of the hours to represent time in this manner.</blockquote>

<blockquote>Q7: What time is represented in the following two examples? Please give your answers in 24-hour time and in traditional 12-hour time.</blockquote>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_10.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_10.png?raw=true" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_11.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_11.png?raw=true" /></a></p>

## Representing Other Information in Binary

23. Today, computers are much more than calculators. All of the information that you see on your computer screen is processed as binary code. Remember, a single Byte can hold quite a bit of information, giving us 256 different opportunities to represent different pieces of information. 

24. This means that we can take anything with less than 256 values and represent it in binary code. What about letters and numerals? Our alphabet A-Z and numbers 1-10 can be represented in one single Byte of information with lots of room to spare.

25. Take for example the number 61. To represent the number as a decimal digit (that is a base-10 number from the first example) we can use one Byte:

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_12.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_12.png?raw=true" /></a></p>

<blockquote>1 + 4 + 8 + 16 + 32 = 61</blockquote>

26. But, what if we wanted to represent each of the individual characters 6 and 1 as numerals? This is where character encoding schemas come into the picture. 

27. There are a number of different encoding schemas out there in the world, but we will use ASCII or the American Standard Code for Information Interchange as an example. See https://www.w3schools.com/charsets/ref_html_ascii.asp for more information on ASCII.

28. Take another look at the Decimal – Hexadecimal – Binary Conversion Table at https://www.eecis.udel.edu/~amer/CISC651/ASCII-Conversion-Chart.pdf. 

29. In the first example when we were calculating the decimal value of each of the Bytes, we used the decimal and binary columns. Now we’ll look at the ASCII and Binary columns.

30. As the chart illustrates, each letter, number, or character has been assigned to a particular set of bits (0-32 are control characters, don’t worry about these). Looking the ASCII column you can see that the numeral 6 has been assigned to `00110110` and the numeral 1 to `00110001`.

31. Note that these correspond to the decimal numbers 54 and 49. In this case instead of representing numbers, these particular Bytes were assigned to represent particular characters on the keyboard. 

32. So, while the decimal digit 61 can be represented in a single Byte `00111101`, the numeral 61 is represented in two ASCII Bytes `00110110 00110001`. 

33. This is the set of Bytes that are returned to the computer when you type 6 and 1 in a word processing program. Words become just strings of ASCII Bytes. 

34. The phrase “Hello World!” would appear in binary as:

`01001000 01100101 01101100 01101100 01101111 00100000 01010111 01101111 01110010 01101100 01100100 00100001`

<blockquote>Q8: Notice that the phrase has a total of 10 letters and an exclamation point, but there are 12 Bytes in the bitstring above. Using the ASCII chart, explain why this is.</blockquote>

<blockquote>Q9: Given what you have just learned about ASCII encoding, is there a difference between the binary representations of “byte”, “Byte,” and “BYTE”?</blockquote>

35. Before ASCII encoding was standardized in the early 1980s, different computers would use different standards for encoding text. Computers were programmed by punching the binary code into cardboard cards called Punched Cards. 

36. Take a few minutes to explore the different standards and punch a virtual card with the Punch Card Emulator http://www.kloth.net/services/cardpunch.php. You can learn more about Punched Cards at http://homepage.cs.uiowa.edu/~jones/cards/codes.html.

<blockquote>Q10: Look closely at the ASCII column of the ASCII chart. As a 1 Byte encoding schema, what limitations do you see? (Hint: compare the ASCII chart to the chart at https://unicode-table.com).</blockquote>

# Representing Other Information

37. Again, all of the information that you encounter on your computer is processed as binary code. With a single Byte we can represent 256 discrete pieces of information – any information that we’d like. 

38. What about color? If we use a single Byte or 8-bits to represent color, we can represent a total of 256 different colors. However, we perceive a much wider range of colors, so to extend the palette we can represent colors using more bits. 

39. As with text encoding standards, there are many different color encoding schemas. Consider the difference between the color palette on old video game systems as compared to what you see on your computer screen today. 

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_13.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_13.png?raw=true" /></a></p>
Image from http://i.imgur.com/UqHhN.png

40. Mario is a great example. The original Nintendo used 8-bit color, but Super Nintendo used 16-bit color giving a wider range of colors to represent the graphics in the game.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_14.jpg?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_14.jpg?raw=true" /></a></p>

41. In 8-bit color, each color is represented in 8-bits or 1 Byte giving a color palette of 256 colors.  16-bit color increases the number of colors in the palette by a factor of two, representing over 65,000 different colors by using 16-bits or 2 Bytes to represent each color (256 x 256 = 65,536). 

42. But, if you recall, the primary colors of light are red, green, and blue. What if we decided to represent each of these primary colors in their own Byte of information?

<blockquote>Q11: If we represented each of the primary colors of light as a single Byte to create colors in three Bytes (one Byte for each color <code><font color="red">00000000</font> <font color="green">00000000</font> <font color="blue">00000000</font></code>), how many different colors could be represented?</blockquote>

43. Each Byte gives us 256 different patterns, so to calculate the total number of colors available in three Bytes we take 256 x 256 x 256 or 16,777,216.

<blockquote>Q12: In our three Byte string <code><font color="red">00000000</font> <font color="green">00000000</font> <font color="blue">00000000</font></code> how many bits are represented?</blockquote>

44. In our Mario examples, we looked at 8-bit and 16-bit color. This particular encoding of colors across 3 Bytes is 24-bit color or 24-bit RGB for Red Green and Blue. If you’ve played with the color sliders in Microsoft Office, then you’ve seen 24-bit color in action.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_15.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_15.png?raw=true" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_16.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_16.png?raw=true" /></a></p>

45. In the left image above, all three colors (red green and blue) are set to their maximum value or
255. As the color chart illustrates, white is created by blending all of the colors together. So to create white in 24-bit RGB color, all three Bytes are set to 1s: <code><font color="red">11111111</font> <font color="green">11111111</font> <font color="blue">11111111</font></code>. Remember from our addition exercises the total decimal value for the Byte <code>11111111</code> is 255.

46. The color black is the absence of light, so the color black is represented as 0s. <code><font color="red">00000000</font> <font color="green">00000000</font> <font color="blue">00000000</font></code>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_17.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_17.png?raw=true" /></a></p>

47. This means that the color red can be represented as: <code><font color="red">111111</font> <font color="green">00000000</font> <font color="blue">00000000</font></code> (equal to the decimal digits <code><font color="red">255</font>, <font color="green">0</font>, <font color="blue">0</font></code>)

48. Green can be represented as: <code><font color="red">000000</font> <font color="green">111111</font> <font color="blue">00000000</font></code> (equal to the decimal digits <code><font color="red">0</font>, <font color="green">255</font>, <font color="blue">0</font></code>)

49. And, blue can be represented as: <code><font color="red">000000</font> <font color="green">000000</font> <font color="blue">111111</font></code> (equal to the decimal digits <code><font color="red">0</font>, <font color="green">0</font>, <font color="blue">255</font></code>)

<blockquote>Q13: Given this logic, how would the colors Magenta, Cyan, and Yellow be represented in binary? You can check your answers with this RGB Color Codes Chart http://www.rapidtables.com/web/color/RGB_Color.htm.</blockquote>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_18.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_18.png?raw=true" /></a></p>

50. So, in a 24-bit color digital image, the color for each pixel would be encoded as three Bytes.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_19.jpg?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_19.jpg?raw=true" /></a></p>

51. Digital sound is encoded in a similar way.  In the following image is an example of 16-bit encoded sound. Digital recordings are created by taking samples of sound at a specific rate. “CD quality” sound is sampled at 44.1 kHz (kilohertz) or 44,100 times per second. This means that 44,100 times per second, a program measures and records the height of a sound’s sound wave and then translates the height to a binary representation in 16-bits or 2 Bytes.

52. Don’t get caught in the details. The important take away here is that any piece of information can be represented in bits and then interpreted by the computer. You will never have to work with the machine at this level. We’ll talk more about programming next week. For now, just know that behind the scenes everything that you input into the computer and everything that is outputted is at some point in the process a string of bits.

# Hex and Bitstreams

53. If you take a look at the Decimal – Hexadecimal – Binary Conversion Table (https://www.eecis.udel.edu/~amer/CISC651/ASCII-Conversion-Chart.pdf) from earlier, you will note that there are a few columns that we didn’t talk about – Octal and Hex. 

54. Petzold’s “Bytes and Hex” chapter explained the details of Hexidecimal encoding. What is important to understand here is that along with binary, there are other ways to represent numbers and string of Bytes or bitstreams.

55. If binary is base-2 and decimal is base-10, then octal is base-8 and hexadecimal or hex is base-16. What this means for us is that we can represent more bits with fewer symbols. Hexidecimal code is a way of representing 8-bit Bytes in just two symbols.

56. Take for example, the character `Z`. Look at your chart. In binary `Z` is represented as `01011010` (or the decimal digit 90). In hex this string of bits can be represented simply as `5A`.

<blockquote>Q14: Take a moment to explain the difference between the decimal digit, the hex representation, and ASCII code in your own words.</blockquote>

57. Our 24-bit color palette gives us another example. 

58. Open the RGB Color Codes Chart (http://www.rapidtables.com/web/color/RGB_Color.htm) and select the color white. 

59. Below the R, G, and B, you should see another code preceded by a # symbol. This is the hex code for the color. 

60. We can represent the color with the bits <code><font color="red">11111111</font> <font color="green">11111111</font> <font color="blue">11111111</font></code>, or we can use the corresponding decimal digits <code><font color="red">255</font> <font color="green">255</font> <font color="blue">255</font></code>, or we can use the hex value <code><font color="red">FF</font> <font color="green">FF</font><font color="blue">FF</font></code>. 

61. We will see later when we work with HTML that this is exactly how you name the color value that you would like to use in your formatting (see https://www.w3schools.com/colors/colors_picker.asp).

## Manipulating Bitstreams with a Hex Editor

62. Now that you are familiar with hex, we can experiment a bit with a hex editor. A hex editor is a program that allows for the direct manipulation of the binary data of a computer file.

63. First download the `hello_world.txt` file from the course website. 

64. This is a plain text file, meaning that the text characters are encoded in a standard coding schema like ASCII. In this example, the text has been encoded in the Unicode UTF-8 standard. 

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_20.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_20.png?raw=true" /></a></p>

65. If you open the file you should see the familiar phrase “Hello World!”

66. Now let’s look at the bits and Bytes that make up this file. 

67. Open the HexEd.it hex editor at https://hexed.it/ in your web browser, and click “Open File” in the menu bar, and open `helloworld.txt` from your computer.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_21.jpg?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_21.jpg?raw=true" /></a></p>

68. The first set of numbers that you see on the left (`00000000`) is a reference to where you are in the file. 

69. This not a particularly large file, so we only have one line to reference. In the middle of the screen we see each Byte represented in hex. And, on the right we see the interpreted text encoded according to UTF-8. Note that the “.” represents a space.

<blockquote>Q15: Based on what you see in the hex editor, how large would you expect this file to be in bits and Bytes?</blockquote>

70. UTF-8 is very similar to ASCII, so you can use the Decimal – Hexadecimal – Binary Conversion Table (https://www.eecis.udel.edu/~amer/CISC651/ASCII-Conversion-Chart.pdf) to confirm that the hex corresponds to the encoded letter.

71. Earlier we determined that “Hello World!” would look like this in binary:

`01001000 01100101 01101100 01101100 01101111 00100000 01010111 01101111 01110010 01101100 01100100 00100001`

72. As the chart demonstrates, the hex code `48 65 6C 6C 6F 20 57 6F 72 6C 64 21` is equivalent to this binary representation. Hex, is simply a short-hand for binary code.

73. With the hex editor, you can modify this file by modifying the hex. Using the hex editor you are modifying the very bitstream (the binary representation of the file). 

74. You can do this in two ways: 
  a. selecting the text in the text pane and typing as you would in any text editor
  b. using the Conversion Chart to write the hex in the hex panel

<blockquote>Q16: Using the hex editor, modify the file, export it to your computer, and open it in a text editor to see the changes that you just made to the file. Explain your process in your notebook.</blockquote>

75. Now, download `helloworld.rtf` from our course site. An `.rtf` file is one saved in a Rich Text Format. 

76. Note that the text is the same as the previous file; however the `.rtf` specification allows for more formatting than an Plain Text file, which means that the information contained within the file is encoded differently. 

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_22.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_22.png?raw=true" /></a></p>

77. You’ll notice that we have a few formatting options with Rich Text, such as font, style, size, and color. (If you are curious, you can review the RTF format specs at http://www.biblioscape.com/rtf15_spec.htm).

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_23.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_23.png?raw=true" /></a></p>

78. Open `helloworld.rtf` in the text editor. 

79. Looking at the text pane, you can now see the binary code interpreted. Our text that we see when we open the file in the text editor is at the very bottom of the file before the end `}`. 

80. The rest of the information is the formatting information for the `.rtf` file. This is hidden from us when we open the file normally, but interpreted behind the scenes by the text editing program.

<blockquote>Q17: Take a look at the text pane, what formatting information can you interpret from the binary code?</blockquote>

<blockquote>Q18: How large is this file in Bytes? How does this compare to the .txt file?</blockquote>

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_24.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_24.png?raw=true" /></a></p>

81. Now let’s compare the `.txt` and `.rtf` files to a Word Document. 

82. Download the `helloworld.docx` file from the course site. As with the other two examples, the text is the same.

<p align="center"><a href="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_25.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/bits-bytes/blob/master/images/Image_25.png?raw=true" /></a></p>

83. Now open `helloworld.docx` in the hex editor.

84. This file should look completely different. In this case, we have a much larger file (almost twice the size) with more information encoded. The text pane on the right no longer makes sense because this information is encoded for the machine and not for us. 

85. `.rtf` files are a relatively simply file format and it just so happens that the information is encoded in a way that we can translate the information when it is decoded as text. This isn’t always true, as we can see with the Word document.

86. As with the `.rtf` what you see here is all of the information that the machine needs to render the file in the way that you see it when you open the file in Word. Unlike the `.txt` and `.rtf` files, the information is encoded in a way that cannot be easily interpreted by us.

<blockquote>Q19: What information about this file can you identify in the hex editor?</blockquote>

<blockquote>Q20: Using the definitions of physical, logical, and conceptual objects from page 1, explain these layers of a digital object in your own works, referring to the helloworld examples and your experience using the hex editor.</blockquote>

# Lab Questions

All of the required questions are listed here for you to reference. Be sure to answer each question completely, including an explanation of how you arrived at your answer.

Q1: If 8 bits or 1 Byte can represent 256 patterns, what is the range of positive integers that can be represented in a single Byte? (e.g. 1-10)

Q2: What is the sum of 1+2+4+8+16+32+64+128? Given the total, do you need to revise your response to Q1?

Q3: Using the diagram above, what would a Byte representing the number 0 look like?

Q4: Using the same logic, calculate the value of the Byte `01101101`.

Q5: Now try working the other way. How would you represent the decimal number 40 in binary? (Hint: this doesn’t involve any advanced math, take a look at the orange numbers in the diagram above.)

Q6: In your own words, explain why we only need 4 bits for the second digit of the hours, minutes, and seconds; 3 bits for the first digit of the seconds and minutes; and 2 bits for the first digit of the hours to represent time in this manner.

Q7: What time is represented in the following two examples? Please give your answers in 24-hour time and in traditional 12-hour time.

Q8: Notice that the phrase has a total of 10 letters and an exclamation point, but there are 12 Bytes in the bitstring above. Using the ASCII chart, explain why this is.

Q9: Given what you have just learned about ASCII encoding, is there a difference between the binary representations of “byte”, “Byte,” and “BYTE”?

Q10:  Look closely at the ASCII column of the ASCII chart. As a 1 Byte encoding schema, what limitations do you see? (Hint: compare the ASCII chart to the chart at https://unicode-table.com).

Q11: If we represented each of the primary colors of light as a single Byte to create colors in three Bytes (one Byte for each color <code><font color="red">00000000</font> <font color="green">00000000</font> <font color="blue">00000000</font></code>), how many different colors could be represented?

Q12: In our three Byte string <code><font color="red">00000000</font> <font color="green">00000000</font> <font color="blue">00000000</font></code> how many bits are represented?

Q13: Given this logic, how would the colors Magenta, Cyan, and Yellow be represented in binary? You can check your answers with this RGB Color Codes Chart http://www.rapidtables.com/web/color/RGB_Color.htm.

Q14: Take a moment to explain the difference between the decimal digit, the hex representation, and ASCII code in your own words.

Q15: Based on what you see in the hex editor, how large would you expect this file to be in bits and Bytes?

Q16: Using the hex editor, modify the file, export it to your computer, and open it in a text editor to see the changes that you just made to the file. Explain your process in your notebook.

Q17: Take a look at the text pane, what formatting information can you interpret from the binary code?

Q18: How large is this file in Bytes? How does this compare to the .txt file?

Q19: What information about this file can you identify in the hex editor?

Q20: Using the definitions of physical, logical, and conceptual objects from page 1, explain these layers of a digital object in your own works, referring to the helloworld examples and your experience using the hex editor.
