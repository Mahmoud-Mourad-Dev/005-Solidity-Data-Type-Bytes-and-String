# 005-Solidity-Data-Type-Bytes-and-String
String literals in programming languages like Solidity can be written using either single quotes ' ' or double quotes " ". For example:"foo" or 'bar'.
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract stringExample {
   string public name = "mahmoud";
}
```
String splitting
you can split a string into multiple consecutive parts, and they will automatically be concatenated. For example, "foo" "bar" will be treated as "foobar". This is useful when dealing with long strings to avoid cluttering a single line.
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract stringExample {
   string public name = "mah""moud";
}
```
Unlike some languages like C that append a null character (\0) at the end of a string to mark its end, string literals in Solidity or JavaScript only represent the actual number of characters. For example, "foo" represents 3 bytes, not 4 as in C.
String literals can implicitly convert to other data types if they fit in size. For instance, if a string is small enough, it can be converted into types like bytes1 up to bytes32, as well as the more general types bytes and string.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract stringExample {
   bytes5 public say = "hello";
}
```
In Solidity, string literals are limited to printable ASCII characters. This means they can only include characters with hexadecimal values ranging from 0x20 to 0x7E. These are the characters between space (0x20) and tilde (0x7E), which includes letters, digits, punctuation, and symbols.

Here’s what the range includes:

0x20: Space character
0x21 to 0x7E: All printable ASCII characters, such as:
Letters: A-Z, a-z
Digits: 0-9
Symbols: !, @, #, etc.
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    string public name = "mahmoud \n mourad"; // Newline
    string public Name = "mahmoud \\ mourad";
    string public nAme = "mahmoud \" mourad";
    string public naMe = "mahmoud \r mourad"; // Carriage return
    string public namE = "mahmoud \t mourad"; // Tab
    string public example = "Hello\x20World"; // \x20 يمثل مسافة
    string public Example = "Hello, \u2764!"; 
    }
```
Until version 0.8.0 there were three additional escape sequences: \b, \f and \v. They are commonly available in other languages but rarely needed in practice. If you do need them, they can still be inserted via hexadecimal escapes, i.e. \x08, \x0c and \x0b, respectively, just as any other ASCII character.
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    string public name = "mahmoud\x08mourad";
    string public Name = "mahmoud\x0cmourad";
    string public nAme = "mahmoud\x0bmourad";    
    }
```
Let's break down the string "\n\"\'\\abc\def" to determine how many bytes it occupies in memory.

\n: Represents a single newline character. This is 1 byte.
\": Represents a single double quote ("). This is 1 byte.
\': Represents a single single quote ('). This is 1 byte.
\\: Represents a single backslash (\). This is 1 byte.
abc: These are regular ASCII characters. Each character (a, b, c) is 1 byte, so this is 3 bytes.
\d: This is an invalid escape sequence (in most programming languages like Solidity or C), so it is treated as two separate characters: a backslash (\) and d. This is 2 bytes.
ef: These are regular ASCII characters, each 1 byte, so this is 2 bytes.
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    string public name ="\n\"\'\\abc\
def";
       
    }
```
The Unicode escape sequence is useful for inserting special characters, symbols, or characters from different languages into strings. Since Unicode supports a wide range of characters from almost all writing systems, it is widely used for internationalization and displaying special symbols.
```solidity
/ SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract stringExample {
   bytes5 public say = "hello";
}
```

Hexadecimal Literals
Hexadecimal literals are prefixed with the keyword hex and are enclosed in double or single-quotes (hex"001122FF", hex'0011_22_FF'). 
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    string  public a = hex"0x1A01";   
    }
```
we can optionally use a single underscore as separator between byte boundaries
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    bytes8  public a = hex'0011_22_FF';   
    }
```
Multiple hexadecimal literals separated by whitespace are concatenated into a single literal: hex"00112233" hex"44556677" is equivalent to hex"0011223344556677"
```solidity
//SPDX-License-Identifier: MIT
pragma solidity 0.8.24;
contract stringExample{
    bytes8  public a = hex'0011_22_FF' hex"0a";   
    }
```


















