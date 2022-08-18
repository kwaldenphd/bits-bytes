# Key Terms

## Binary Number Systems

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

  * 1 bit – 2 patterns (21)
  * 2 bits – 4 (22)
  * 3 bits – 8 (23)
  * 4 bits – 16 (24)
  * 5 bits – 32 (25)
  * 6 bits – 64 (26)
  * 7 bits – 128 (27)
  * 8 bits – 256 (28)
  * n bits -  2n patterns

## Encoding Schema

**Character encoding**
- "Character encoding is used to represent a repertoire of characters by some kind of encoding system. Depending on the abstraction level and context, corresponding code points and the resulting code space may be regarded as bit patterns, octets, natural numbers, electrical pulses, etc. A character encoding is used in computation, data storage, and transmission of textual data" ([Wikipedia](https://en.wikipedia.org/wiki/Character_encoding))

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

## File Formats

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

## Representing Other Informtation in Binary

**Color depth**
- "Color depth, also known as bit depth, is either the number of bits used to indicate the color of a single pixel, or the number of bits used for each color component of a single pixel. Color depth expresses the precision with which the amount of each primary can be expressed; the other aspect is how broad a range of colors can be expressed (the gamut). The definition of both color precision and gamut is accomplished with a color encoding specification which assigns a digital code value to a location in a color space" ([Wikipedia](https://en.wikipedia.org/wiki/Color_depth))

**Hexadecimal (hex)**
- "In mathematics and computing, hexadecimal (also base 16, or hex) is a positional system that represents numbers using a base of 16. Unlike the common way of representing numbers with ten symbols, it uses sixteen distinct symbols, most often the symbols ‘0’–’9’ to represent values zero to nine, and ‘A’–’F’ (or alternatively ‘a’–’f’) to represent values ten to fifteen. Hexadecimal numerals are widely used by computer system designers and programmers, as they provide a human-friendly representation of binary-coded values. Each hexadecimal digit represents four binary digits…For example, a single byte can have values ranging from 00000000 to 11111111 in binary form, which can be conveniently represented as 00 to FF in hexadecimal" ([Wikipedia](https://en.wikipedia.org/wiki/Hexadecimal))

**RGB color model**
- "The RGB color model is an additive color model in which the red, green, and blue primary colors of light are added together in various ways to reproduce a broad array of colors. The name of the model comes from the initials of the three additive primary colors, red, green, and blue. The main purpose of the RGB color model is for the sensing, representation, and display of images in electronic systems, such as televisions and computers" ([Wikipedia](https://en.wikipedia.org/wiki/RGB_color_model))
