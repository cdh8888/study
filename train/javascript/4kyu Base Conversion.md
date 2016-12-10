# Base Conversion

### Instructions

In this kata you have to implement a base converter, which converts between arbitrary bases / alphabets. Here are some pre-defined alphabets:

```
var Alphabet = {
  BINARY:        '01',
  OCTAL:         '01234567',
  DECIMAL:       '0123456789',
  HEXA_DECIMAL:  '0123456789abcdef',
  ALPHA_LOWER:   'abcdefghijklmnopqrstuvwxyz',
  ALPHA_UPPER:   'ABCDEFGHIJKLMNOPQRSTUVWXYZ',
  ALPHA:         'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ',
  ALPHA_NUMERIC: '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
};
```

The function convert() should take an input (string), the source alphabet (string) and the target alphabet (string). You can assume that the input value always consists of characters from the source alphabet. You don't need to validate it.

#### Examples:

```
// convert between numeral systems
convert("15", Alphabet.DECIMAL, Alphabet.BINARY); // should return "1111"
convert("15", Alphabet.DECIMAL, Alphabet.OCTAL); // should return "17"
convert("1010", Alphabet.BINARY, Alphabet.DECIMAL); // should return "10"
convert("1010", Alphabet.BINARY, Alphabet.HEXA_DECIMAL); // should return "a"

// other bases
convert("0", Alphabet.DECIMAL, Alphabet.ALPHA); // should return "a"
convert("27", Alphabet.DECIMAL, Alphabet.ALPHA_LOWER); // should return "bb"
convert("hello", Alphabet.ALPHA_LOWER, Alphabet.HEXA_DECIMAL); // should return "320048"
convert("SAME", Alphabet.ALPHA_UPPER, Alphabet.ALPHA_UPPER); // should return "SAME"
```

#### Additional Notes:

The maximum input value can always be encoded in a number without loss of precision in JavaScript. In Haskell, intermediate results will probably be to large for Int.
The function must work for any arbitrary alphabets, not only the pre-defined ones
You don't have to consider negative numbers

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function convert(input, source, target) {

  if(source === target){
    return input;
  }

  const decimal = convertAlphabetToDecimal(input, source); 
  const result = convertDecimalToAlphabet(decimal, target); 

  function convertAlphabetToDecimal(alphabetValue, alphaType){
    let result = 0;
    let value = alphabetValue;

    for(i=0; i<value.length; i++){
      if(i === value.length-1){
        result += alphaType.indexOf(value.charAt(i));
      }
      else {
        result = (result + alphaType.indexOf(value.charAt(i))) * alphaType.length;
      }
    }

    return result;
  }

  function convertDecimalToAlphabet(decimal, alphaType){
    let result = '';
    let value = decimal;
    while(true){
      if(alphaType.length > value) {
        result=alphaType[Math.floor(value)].concat(result);
        break;
      } else {
        result=alphaType[Math.floor(value % alphaType.length)].concat(result);
        value = Math.floor(value / alphaType.length);
      }
    }
    return result;
  }

  return result;
}
```
  </p>
</details>
