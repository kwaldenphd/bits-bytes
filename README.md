# Binary Number Systems & Encoding Schema

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Overview and Goals

In this lab, we are going to explore how information is represented in binary code. Binary code is the machine code or machine language. These are the 1’s and 0’s that represent the bits and Bytes that make up computer programs or the data processed by the computer. Everything that you see on your computer screen can be reduced to binary code, although most users of computers have few reasons to interact with the computer at this level. This will be one of the rare times when you will manipulate binary data, but this project provides an opportunity to further explore the relationship between what you seen on the screen and what is going on inside the machine.

By the end of this lab you will be able to:
-	Calculate the value of bytes using binary addition
-	Explain how text and color are represented in binary
-	Use a hex editor to manipulate binary code
-	Define the relationship between the logical, physical, and conceptual facets of a digital object

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=517ac0ae-6466-4508-9264-aef401054b25">Lecture/live coding playlist</a></td>
  </tr>
  </table>

## Acknowledgements

Sections of this lab were adapted from the "Project 1: Binary, Bits, and Basics" project materials developed by [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

The "Binary Number Systems" and "Encoding Schema" lecture segments were adapted from the following PBS *[Crash Course Computer Science](https://www.pbs.org/show/crash-course-computer-science/)* episodes:
- "[Representing Numbers and Letters With Binary](https://www.pbs.org/video/representing-numbers-and-letters-with-binary-crash-course-c-pgrlei/)"
- "[Boolean Logic & Logic Gates](https://www.pbs.org/video/boolean-logic-logic-gates-crash-course-computer-science-nobmpt/)"

## Table of Contents
- [Lecture & Live Coding](#lecture--live-coding)
- [Lab Notebook Template](#lab-notebook-template)
- [Physical, Logical & Conceptual Objects](#physical-logical--conceptual-objects)
- [Binary Number Systems](#binary-number-systems)
- [Encoding Schema](#encoding-schema)
- [File Formats](#file-formats)
- [Representing Other Information in Binary](#representing-other-information-in-binary)
- [Putting It All Together](#putting-it-all-together)
- [Lab Notebook Questions](#lab-notebook-questions)

## Lecture & Live Coding

Throughout this lab, you will see a Panopto icon at the start of each section.

This icon indicates there is lecture/live coding asynchronous content that accompanies this section of the lab. 

You can click the link in the figure caption to access these materials (ND users only).

Example:

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=517ac0ae-6466-4508-9264-aef401054b25">Lecture/live coding playlist</a></td>
  </tr>
  </table>

# Lab Notebook Template

[Link to lab notebook template](https://docs.google.com/document/d/172KM0g9zsvhJeeWzvUszeqCxfJOWMulwetfx8hLCu9M/copy) (ND users, Google Doc)

# Physical, Logical & Conceptual Objects

Librarians, archivists, and information professionals who work in digital preservation often think of digital technologies and digital objects as incorporating three layers: the physical object, the logical object, and the conceptual object. The following definitions are taken from UNESCO’s Guidelines for the Preservation of Digital Heritage, page 35 (available at http://unesdoc.unesco.org/images/0013/001300/130071e.pdf).

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_1.jpg?raw=true" width="500"></p>

"As physical objects, consisting of ‘inscriptions’ (usually binary states of ‘on-ness’ or ‘off-ness’) on carrier media such as computer disks or tapes. (Despite the impression of that they exist in ‘cyberspace’, even online resources must exist on physical carriers somewhere)”

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_2.png?raw=true" width="500"></p>

"As logical objects consisting of computer readable code, whose existence at any particular time depends on the physical inscriptions but is not tied to any particular carrier”

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/c/c9/Main_Building_at_the_University_of_Notre_Dame.jpg" width="500"></p>

"As conceptual objects that have meaning to humans, unlike the logical or physical objects that encode them at any particular time. (This is recognisable as the performance presented to a user)”

This lab will explore the relationship between the logical and conceptual object – the bits and bytes that the computer translates into the representations of information on the screen that we can understand.

# Binary Number Systems

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=248cf9cd-9aa7-4175-bd96-aef30144f577">Binary Number Systems</a></td>
  </tr>
  </table>
  
## Key Terms

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Bits_Bytes_Image.png?raw=true" width="500"></p>

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

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Pattern_Ranges.png?raw=true" width="500"></p>

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

## Application

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Binary_Conversion.png?raw=true" width="500"><br>Converting binary numbers</p>

Resources:
- [Decimal – Hexadecimal – Binary Conversion Table](https://github.com/kwaldenphd/bits-bytes/blob/main/ASCII-Conversion-Chart.pdf)
- [WikiHow, "How to Convert Binary to Decimal" (26 July 2022)](https://www.wikihow.com/Convert-from-Binary-to-Decimal)

Q1: What would a byte representing the decimal number `0` look like? 

Q2: Calculate the value of byte 01101101.

Q3: How would you representing the decimal number 40 using binary digits?

# Encoding Schema

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=124b4fbb-7a33-4d0d-9cc9-aef3015169e6">Encoding Schema</a></td>
  </tr>
  </table>

## Key Terms

<table border="0"><tr><td><p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/ACM_1.png?raw=true" width="500"></p></td>
<td><p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/ACM_2.png?raw=true" width="500"></p></td></tr>
<tr><td>Table 1a. R.W. Bemer, "<a href="https://web.archive.org/web/20131017062654/http://www.trailing-edge.com/~bobbemer/SURVEY.HTM">Survey of coded character representation</a>", Commun. ACM 3, No. 12, 639-641, 1960 Dec</td><td>Table 2. H.J. Smith, Jr., F.A. Williams, "<a href="https://web.archive.org/web/20131017062654/http://www.trailing-edge.com/~bobbemer/SURVEY.HTM">Survey of punched card codes</a>", Commun. ACM 3, 639 & 642, 1960 Dec</td></tr></table>

**Character encoding**
- "Character encoding is used to represent a repertoire of characters by some kind of encoding system. Depending on the abstraction level and context, corresponding code points and the resulting code space may be regarded as bit patterns, octets, natural numbers, electrical pulses, etc. A character encoding is used in computation, data storage, and transmission of textual data" ([Wikipedia](https://en.wikipedia.org/wiki/Character_encoding))

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/ASCII.png?raw=true" width="500"></p>

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

**Unicode**
- "Unicode is a computing industry standard for the consistent encoding, representation, and handling of text expressed in most of the world's writing systems. The standard is maintained by the Unicode Consortium, and as of May 2019 the most recent version, Unicode 12.1, contains a repertoire of 137,994 characters (consisting of 137,766 graphic characters, 163 format characters and 65 control characters) covering 150 modern and historic scripts, as well as multiple symbol sets and emoji" ([Wikipedia](https://en.wikipedia.org/wiki/Unicode))
- [Click here](https://home.unicode.org/basic-info/overview) to learn more about the Unicode consortium

<table>
 <tr><td>
<img src="https://www.freeiconspng.com/thumbs/survey-icon/survey-icon-12.png" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLScOk5_z6dRF8WvPUezpyU78sI2bvVrdnySVmNfH9IUGnXYh0w/viewform?usp=sf_link">Encoding Schema Comprehension Check</a></td>
  </tr>
  </table>

# File Formats

For this section of the lab, you'll need to download three different text files:
- `hello_world.txt`
- `hello_world.rtf`
- `hello_world.docx`

[Click here](https://github.com/kwaldenphd/bits-bytes/blob/draft/files/hello-world-files.zip) to download all three files.

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=eefecb77-0cd9-407c-90ca-aef400fb57ec">File Formats</a></td>
  </tr>
  </table>

## Key Terms

**File Manager (or File Browser)**
- "A file manager or file browser is a computer program that provides a user interface to manage files and folders. The most common operations performed on files or groups of files include creating, opening (e.g. viewing, playing, editing or printing), renaming, copying, moving, deleting and searching for files, as well as modifying file attributes, properties and file permissions. Folders and files may be displayed in a hierarchical tree based on their directory structure" ([Wikipedia](https://en.wikipedia.org/wiki/File_manager))
- Examples: Finder (Mac), File Explorer (Windows)

**File Extension (or Filename Extension)**
- "A filename extension, file name extension or file extension is a suffix to the name of a computer file (e.g., `.txt`, `.docx`, `.md`). The extension indicates a characteristic of the file contents or its intended use. A filename extension is typically delimited from the rest of the filename with a full stop (period)" ([Wikipedia](https://en.wikipedia.org/wiki/Filename_extension))

**Proprietary File Formats**
- "We will say that a file format is proprietary if the mode of presentation of its data is opaque and its specification is not publicly available. Proprietary formats are developed by software companies in order to encode data produced by their applications: only the software produced by a company who owns the specification of a file format will be able to read correctly and completely the data contained in this file. Proprietary formats can be further protected through the use of patents and the owner of the patent can ask royalties for the use or implementation of the formats in third-party's software" ([OpenFormats.org](https://web.archive.org/web/20081112110558/http://www.openformats.org/en1))
- Common proprietary formats include:
  * `PDF` (Adobe Portable Document Format)
  * `DOCX` (Microsoft Word Document)
  * `XLSX` (Microsoft Excel Document)

**Open File Formats**
- "We will say that a file format is open if the mode of presentation of its data is transparent and/or its specification is publicly available. Open formats are ordinarily standards fixed by public authorities or international institutions whose aim is to establish norms for software interoperability. There are nevertheless cases of open formats promoted by software companies which choose to make the specification of the formats used by their products publicly available…an open format can either be coded in a transparent way (readable in any text editor) or in a binary mode (unreadable in a text editor but thoroughly decodable once the format specifications are known)” ([OpenFormats.org](https://web.archive.org/web/20081112110558/http://www.openformats.org/en1))
- Common open formats include:
  * `TXT` (plain-text)
  * `CSV` (comma-separated value)
  * `HTML` (hyper-text markup language)
  * `PNG` (portable network graphic)

**Hexadecimal (hex)**
- "In mathematics and computing, hexadecimal (also base 16, or hex) is a positional system that represents numbers using a base of 16. Unlike the common way of representing numbers with ten symbols, it uses sixteen distinct symbols, most often the symbols ‘0’–’9’ to represent values zero to nine, and ‘A’–’F’ (or alternatively ‘a’–’f’) to represent values ten to fifteen. Hexadecimal numerals are widely used by computer system designers and programmers, as they provide a human-friendly representation of binary-coded values. Each hexadecimal digit represents four binary digits…For example, a single byte can have values ranging from 00000000 to 11111111 in binary form, which can be conveniently represented as 00 to FF in hexadecimal" ([Wikipedia](https://en.wikipedia.org/wiki/Hexadecimal))

<table>
 <tr><td>
<img src="https://www.freeiconspng.com/thumbs/survey-icon/survey-icon-12.png" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSeyt0uZ05pfAf_IFJEC-_t55dfCGBERoNlLWfWSqI9pO_VoYw/viewform?usp=sf_link">File Formats Comprehension Check</a></td>
  </tr>
  </table>
  
## Application

Q4: Why does the proprietary versus open file format distinction matter in relation to character encoding?

Q5: Open the `hello-world.txt` file in a hex editor ([HexEd.it](https://hexed.it/)). How large would you expect this file to be (in bits and bytes)? You can use the hex editor or your own computer's file manager to verify the file size.

Q6: How large is the 'hello-world.rtf' file (in bits and bytes)? How does this compare to the `.txt` file? Why do these two files differ in size?
- HINT: Open the `hello-world.rtf` file in a hex editor ([HexEd.it](https://hexed.it/)) and compare with the `.txt` file.

# Representing Other Information in Binary

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=fabb1a9f-de9e-4bcd-94b4-aef400c1a6c9">Representing Color</a></td>
  </tr>
  </table>

The end of the "Encoding Schema" lecture mentioned how binary numbers are also used to represent things other than numbers, text, or characters.

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Bit_Comparison.png?raw=true" width="500"></p>

What about color? If we use a single byte or 8-bits to represent color, we can represent a total of 256 different colors. However, we perceive a much wider range of colors, so to extend the palette we can represent colors using more bits. 

<fig>
 <p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_13.png?raw=true"></p>
 <p align="center"><figcaption>Image from http://i.imgur.com/UqHhN.png</figcaption></p>
 </fig>

Consider the difference between the color palette on old video game systems as compared to what you see on your computer screen today. Mario is a great example. The original Nintendo used 8-bit color, but Super Nintendo used 16-bit color giving a wider range of colors to represent the graphics in the game.

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Hot_Air_Balloons.png?raw=true" width="500"></p>

In 8-bit color, each color is represented in 8-bits or 1 Byte giving a color palette of 256 colors.  16-bit color increases the number of colors in the palette by a factor of two, representing over 65,000 different colors by using 16-bits or 2 Bytes to represent each color (256 x 256 = 65,536). 

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_17.png?raw=true" height="500"></p>

As with text encoding standards, there are many different color encoding schemas. We can represent color using discrete values for the primary colors red, green, and blue.

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Color_Table.png?raw=true" width="500"></p>

An `RGB` (red-green-blue) color system can be represented using hex or decimal values.

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_15.png?raw=true" height="500"></p>

The Mario example featured 8-bit and 16-bit color. If you've ever seen Red-Green-Blue color sliders, you've seen a 3 byte (24-bit) color system in action.

<table>
 <tr><td>
<img src="https://www.freeiconspng.com/thumbs/survey-icon/survey-icon-12.png" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSfJMHhYmWaqMo7_Zl2o-RLVwpDVzPDAzSSr2egZdlGjGTf__A/viewform?usp=sf_link">Representing Color Comprehension Check</a></td>
  </tr>
  </table>

## Key Terms

**Color depth**
- "Color depth, also known as bit depth, is either the number of bits used to indicate the color of a single pixel, or the number of bits used for each color component of a single pixel. Color depth expresses the precision with which the amount of each primary can be expressed; the other aspect is how broad a range of colors can be expressed (the gamut). The definition of both color precision and gamut is accomplished with a color encoding specification which assigns a digital code value to a location in a color space" ([Wikipedia](https://en.wikipedia.org/wiki/Color_depth))

**Hexadecimal (hex)**
- "In mathematics and computing, hexadecimal (also base 16, or hex) is a positional system that represents numbers using a base of 16. Unlike the common way of representing numbers with ten symbols, it uses sixteen distinct symbols, most often the symbols ‘0’–’9’ to represent values zero to nine, and ‘A’–’F’ (or alternatively ‘a’–’f’) to represent values ten to fifteen. Hexadecimal numerals are widely used by computer system designers and programmers, as they provide a human-friendly representation of binary-coded values. Each hexadecimal digit represents four binary digits…For example, a single byte can have values ranging from 00000000 to 11111111 in binary form, which can be conveniently represented as 00 to FF in hexadecimal" ([Wikipedia](https://en.wikipedia.org/wiki/Hexadecimal))

**RGB color model**
- "The RGB color model is an additive color model in which the red, green, and blue primary colors of light are added together in various ways to reproduce a broad array of colors. The name of the model comes from the initials of the three additive primary colors, red, green, and blue. The main purpose of the RGB color model is for the sensing, representation, and display of images in electronic systems, such as televisions and computers" ([Wikipedia](https://en.wikipedia.org/wiki/RGB_color_model))

## Application

Q7: How would the colors Magenta, Cyan, and Yellow be represented in binary, hex, and decimal? 
- [RGB Color Table](http://www.rapidtables.com/web/color/RGB_Color.htm)

# Putting It All Together

In a future lab, we'll spend more time working with image files and encoding. But digital sound represents another example of file formats and encoding in action. The image below shows a 16-bit sound sample.

<p align="center"><img src="https://github.com/kwaldenphd/bits-bytes/blob/main/images/Image_19.jpg?raw=true"></p>

Digital sound recordings are created by taking samples of sound at a specific rate. “CD quality” sound is sampled at 44.1 kHz (kilohertz) or 44,100 times per second. This means that 44,100 times per second, a program measures and records the height of a sound’s sound wave and then translates the height to a binary representation in 16-bits or 2 Bytes.

The important take away here is that any piece of information can be represented in bits and then interpreted by the computer. It's not likely you will have to work with the machine at this level. For now, just know that behind the scenes everything that you input into the computer and everything that is outputted is at some point in the process a string of bits.

## Final Questions

Q8: Take a moment to explain the difference between the decimal digit, the hex representation, and ASCII code in your own words.

Q9: Using the definitions of physical, logical, and conceptual objects from earlier in this lab, explain these layers of a digital object in your own works, referring to the helloworld examples and your experience using the hex editor.

# Lab Notebook Questions

[Link to lab notebook template](https://docs.google.com/document/d/172KM0g9zsvhJeeWzvUszeqCxfJOWMulwetfx8hLCu9M/copy) (ND users, Google Doc)

Resources for Q1-Q3:
- [Decimal – Hexadecimal – Binary Conversion Table](https://github.com/kwaldenphd/bits-bytes/blob/main/ASCII-Conversion-Chart.pdf)
- [WikiHow, "How to Convert Binary to Decimal" (26 July 2022)](https://www.wikihow.com/Convert-from-Binary-to-Decimal)

Q1: What would a byte representing the decimal number `0` look like? 

Q2: Calculate the value of byte 01101101.

Q3: How would you representing the decimal number 40 using binary digits?

Q4: Why does the proprietary versus open file format distinction matter in relation to character encoding?

Q5: Open the `hello-world.txt` file in a hex editor ([HexEd.it](https://hexed.it/)). How large would you expect this file to be (in bits and bytes)? You can use the hex editor or your own computer's file manager to verify the file size.

Q6: How large is the 'hello-world.rtf' file (in bits and bytes)? How does this compare to the `.txt` file? Why do these two files differ in size?
- HINT: Open the `hello-world.rtf` file in a hex editor ([HexEd.it](https://hexed.it/)) and compare with the `.txt` file.

Q7: How would the colors Magenta, Cyan, and Yellow be represented in binary, hex, and decimal? 
- [RGB Color Table](http://www.rapidtables.com/web/color/RGB_Color.htm)

Q8: Take a moment to explain the difference between the decimal digit, the hex representation, and ASCII code in your own words.

Q9: Using the definitions of physical, logical, and conceptual objects from earlier in this lab, explain these layers of a digital object in your own works, referring to the helloworld examples and your experience using the hex editor.
