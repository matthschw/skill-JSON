# DPL-JSON

The Cadence Skill functions in the repository are used
to convert Disembodied Property Lists (DPLs) to 
JavaScript Object Notation (JSON) and backwards.

The below shown table shows the corresponding data structures
in Skill and JSON.
Skill tables, arrays etc. are *NOT* considered (a warning message is given).


| JSON              | SKILL                           |
| ----------------- | ------------------------------- |
| Object            | Disembodied Property List (DPL) |
| Array (non-empty) | List                            |
| Array (empty)     | -                               |
| Double            | Floatnum                        |
| Integer           | Fixnum                          |
| String            | String                          |
| `true`            | Symbol `t`                      |
| `false`           | `nil` (empty list)              |
| `null`            | Symbol `unbound`                |


Utilize the function *EDdpl2json* to convert a DPL in a JSON string
and *EDjson2dpl* to convert a JSON string in a DPL.

## Example

```scheme
dpl='(nil grades (nil english unbound math 2.3) likesWine nil likesBeer t 
  favouriteFood ("pizza" "pie" "chips") favouriteNumbers (3.141592 42 1337) 
  height 179.56 age 42 lastName "Doe" firstName "John")

json=EDdpl2json(dpl)
>>"{\"firstName\": \"John\", \"lastName\": \"Doe\", \"age\": 42, \"height\":
 179.56, \"favouriteNumbers\": [3.141592, 42, 1337], \"favouriteFood\":
  [\"pizza\", \"pie\", \"chips\"], \"likesBeer\": true, \"likesWine\": false,
  \"grades\": {\"math\": 2.3, \"english\": null}}"

dpl=EDjson2dpl(json)
(nil grades (nil english unbound math 2.3) likesWine nil
likesBeer t favouriteFood ("pizza" "pie" "chips") favouriteNumbers
(3.141592 42 1337) height 179.56 age 42
lastName "Doe" firstName "John"
)
```

## License

Copyright (c) 2022, [Reutlingen University](https://www.reutlingen-university.de), [Electronics & Drives](https://www.electronics-and-drives.de/)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.