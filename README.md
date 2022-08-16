# Binary Number Systems

## CC statement

## Overview/Goals

## Acknowledgements

## ToC

## Lecture/Live Coding

## Overview

Librarians, archivists, and information professionals who work in digital preservation often think of digital technologies and digital objects as incorporating three layers: the physical object, the logical object, and the conceptual object. The following definitions are taken from UNESCO’s Guidelines for the Preservation of Digital Heritage, page 35 (available at http://unesdoc.unesco.org/images/0013/001300/130071e.pdf).

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_1.jpg?raw=true"></p>

"As physical objects, consisting of ‘inscriptions’ (usually binary states of ‘on-ness’ or ‘off-ness’) on carrier media such as computer disks or tapes. (Despite the impression of that they exist in ‘cyberspace’, even online resources must exist on physical carriers somewhere)”

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_2.png?raw=true"></p>

"As logical objects consisting of computer readable code, whose existence at any particular time depends on the physical inscriptions but is not tied to any particular carrier”

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/c/c9/Main_Building_at_the_University_of_Notre_Dame.jpg"></p>

"As conceptual objects that have meaning to humans, unlike the logical or physical objects that encode them at any particular time. (This is recognisable as the performance presented to a user)”

This lab will explore the relationship between the logical and conceptual object – the bits and bytes that the computer translates into the representations of information on the screen that we can understand.

## Binary Number Systems

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=248cf9cd-9aa7-4175-bd96-aef30144f577">Binary Number Systems</a></td>
  </tr>
  </table>
  
### Key Terms

BITS BYTES IMAGE

**Bits**
- "The bit is a basic unit of information in information theory, computing, including digital communications. As a binary digit, the bit represents a logical state, having only one of two values. It may be physically implemented with a two-state device. These values are most commonly represented as either 0 or 1" ([Wikipedia](https://en.wikipedia.org/wiki/Bit))

**Bytes**
- "The byte is a unit of digital information that most commonly consists of eight bits. Historically, the byte was the number of bits used to encode a single character of text in a computer and for this reason it is the smallest addressable unit of memory in many computer architectures" ([Wikipedia](https://en.wikipedia.org/wiki/Byte))

**Binary**
- "In mathematics and digital electronics, a binary number is a number expressed in the base-2 numeral system or binary numeral system, which uses only two symbols: typically ‘0’ (zero) and ‘1’ (one). The base-2 numeral system is a positional notation... Each digit is referred to as a bit. Because of its straightforward implementation in digital electronic circuitry using logic gates, the binary system is used by almost all modern computers and computer-based devices" ([Wikipedia](https://en.wikipedia.org/wiki/Binary))

**Unit Conversions**
- Kilobyte KB = 1,000 Bytes 
- Megabyte MB = 1 million Bytes 
- Gigabyte GB = 1 billion Bytes 
- Terabyte TB = 1 trillion Bytes

**Pattern Ranges**
- One bit gives us two patterns: `1 and 0`. Two bits allow for four patterns: `00, 11, 01, 10`.
- Every time we add one bit to the length of our bitstring, we double the number of available patterns. So, 8 bits or 1 byte provides a means for representing 256 different patterns, as illustrated below:

PATTERN RANGE IMAGE

  * 1 bit – 2 patterns (21)
  * 2 bits – 4 (22)
  * 3 bits – 8 (23)
  * 4 bits – 16 (24)
  * 5 bits – 32 (25)
  * 6 bits – 64 (26)
  * 7 bits – 128 (27)
  * 8 bits – 256 (28)
  * n bits -  2n patterns

<table>
 <tr><td>
<img src="https://www.freeiconspng.com/thumbs/survey-icon/survey-icon-12.png" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLScQoRbyDYB2Cisg_AmfMhUqj8qXn0ZbeuembRhQpOnbb64I2g/viewform?usp=sf_link">Binary Number Systems Comprehension Check</a></td>
  </tr>
  </table>

### Application

COVNERSION DIAGRAM

Resources:
- [Decimal – Hexadecimal – Binary Conversion Table](https://github.com/kwaldenphd/bits-bytes/blob/main/ASCII-Conversion-Chart.pdf)
- [WikiHow, "How to Convert Binary to Decimal" (26 July 2022)](https://www.wikihow.com/Convert-from-Binary-to-Decimal)

Q1: What would a byte representing the decimal number `0` look like? 

Q2: Calculate the value of byte 01101101.

Q3: How would you representing the decimal number 40 using binary digits?

## Encoding Schema

LIVE LECTURE LINK

### Key Terms

ACM IMAGES
**Character encoding**
- "Character encoding is used to represent a repertoire of characters by some kind of encoding system. Depending on the abstraction level and context, corresponding code points and the resulting code space may be regarded as bit patterns, octets, natural numbers, electrical pulses, etc. A character encoding is used in computation, data storage, and transmission of textual data" ([Wikipedia](https://en.wikipedia.org/wiki/Character_encoding))

ASCII IMAGE

**American Standard Code for Information Interchange (ASCII)**
- "A character encoding standard for electronic communication. ASCII codes represent text in computers, telecommunications equipment, and other devices. Most modern character-encoding schemes are based on ASCII, although they support many additional characters" ([Wikipedia](https://en.wikipedia.org/wiki/ASCII))

**Hexadecimal (hex)**
- "In mathematics and computing, hexadecimal (also base 16, or hex) is a positional system that represents numbers using a base of 16. Unlike the common way of representing numbers with ten symbols, it uses sixteen distinct symbols, most often the symbols ‘0’–’9’ to represent values zero to nine, and ‘A’–’F’ (or alternatively ‘a’–’f’) to represent values ten to fifteen. Hexadecimal numerals are widely used by computer system designers and programmers, as they provide a human-friendly representation of binary-coded values. Each hexadecimal digit represents four binary digits…For example, a single byte can have values ranging from 00000000 to 11111111 in binary form, which can be conveniently represented as 00 to FF in hexadecimal" ([Wikipedia](https://en.wikipedia.org/wiki/Hexadecimal))

Sample conversion table:
<table><tr><th>Decimal</th><th>Hex</th><th>Binary</th><th>ASCII Character</th><th>Description</th></tr>
 <tr><td>0</td><td>00</td><td>000000</td><td>NUL</td><td>Null character</td></tr>
 <tr><td>48</td><td>30</td><td>0110000</td><td>1</td><td>Digit 1</td></tr>
 <tr><td>65</td><td>42</td><td>1000001</td><td>A</td><td>Uppercase A</td></tr>
 <tr><td>97</td><td>61</td><td>1100001</td><td>1</td><td>Lowercase a</td></tr></table> 

[Click here](https://www.asciitable.xyz/) for a full ASCII conversion table.

WIKI SCREENSHOT
**Unicode**
- "Unicode is a computing industry standard for the consistent encoding, representation, and handling of text expressed in most of the world's writing systems. The standard is maintained by the Unicode Consortium, and as of May 2019 the most recent version, Unicode 12.1, contains a repertoire of 137,994 characters (consisting of 137,766 graphic characters, 163 format characters and 65 control characters) covering 150 modern and historic scripts, as well as multiple symbol sets and emoji" ([Wikipedia](https://en.wikipedia.org/wiki/Unicode))
- [Click here](https://home.unicode.org/basic-info/overview) to learn more about the Unicode consortium

<table>
 <tr><td>
<img src="https://www.freeiconspng.com/thumbs/survey-icon/survey-icon-12.png" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLScOk5_z6dRF8WvPUezpyU78sI2bvVrdnySVmNfH9IUGnXYh0w/viewform?usp=sf_link">Encoding Schema Comprehension Check</a></td>
  </tr>
  </table>

## File Formats

Compare txt, rtf, word, and pdf.

Open in processing programs vs plain-text systems.

BRING IN EXCEL/CSV HERE TOO

### Key Terms

### Application




## Representing Other Information



