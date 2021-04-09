# Introduction to Crack.js

## Import

To import Crack.js, add this to the `<head>` tag of your page:

```
<script src="https://cdn.jsdelivr.net/gh/ColonelParrot/crack-js@main/src/script.min.js"></script>
```

## Usage

To use Crack.js, use the `BruteForce` class. You can call it like so:

```javascript
new BruteForce(callback, 0, 255, 1, false)
```

The constructor accepts 5 parameters (1 optional). The first constructor is a callback function

The second and third parameters define the ascii start and end codes. For example, setting the second parameter to `0` and the third parameter to `255` will make it loop through all ascii characters.

The fourth parameter is the number of digits to permute, and the fifth defines whether the process should be aync or not. Keep in mind that the async to non-async time ratio is 30000 : 7 milliseconds (non-async is lightning fast).

### The callback function

The callback function accepts one parameter which is the currently permuted String. An example callback function to print all permuted Strings:

```javascript
function callback(c){
  console.log(c);
}
```

If the callback function ever returns `true`, the permutation is halted. E.g, if you want to stop the process when the currently permuted String is `ab`, then you can do it like so:

```javascript
function callback(c){
  if(c == 'ab'){
    return true;
  }
}
```

### Cracking hashes using Crack.js

The following example demonstrates how you can crack a hash using Crack.js:

```
function sha256(text) {
  //Some calculations
	return result;
};
function callback(combo){
	if(sha256(combo) == "8f434346648f6b96df89dda901c5176b10a6d83961dd3c1ac88b59b2dc327aa4"){//"hi" hashed
		console.log(combo);
		return true;
	}
}
new BruteForce(callback, 33, 126, 2, false)
```
