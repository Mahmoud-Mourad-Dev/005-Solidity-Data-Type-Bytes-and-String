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







