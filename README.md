# crack-js

A Javascript class that enables you to brute force generate all possible Strings of a given length (defined by ascii codes).

# Use

## Import

```html
<script src="https://cdn.jsdelivr.net/gh/ColonelParrot/crack-js@main/src/script.min.js"></script>
```

## Usage

Consider the following example:

```javascript
function callback(combo){
  console.log(combo);
}
new BruteForce(callback, 33, 125, 1, false)
```

**33** is the ascii start code (e.g, `!`). **125** is the ascii end code (e.g, `|`). **1** defines how many digits to permute, and **false** defines whether it is async or not.

Using async should be used carefully. Not using async improves user experience (e.g, the page still is responsive) but makes it much more slower. Using async makes it lightning-fast, but freezes the page. The async-non-async ratio is approximately 30000ms : 7ms.

The above code prints all ascii characters from `!` to `|`.

**Cracking a hash using Crack.js**

The following code illustrates how to crach a hashed String using Crack.js:

```javascript
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

If you return `true` in the callback function, the premutation generator will be terminated.

The code prints:

```
hi
```
