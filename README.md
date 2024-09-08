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



