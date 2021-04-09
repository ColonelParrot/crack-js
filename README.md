# crack-js

A Javascript class that enables you to brute force generate all possible Strings of a given length (defined by ascii codes).

# Use

## Import

```html
<script src="https://cdn.jsdelivr.net/gh/ColonelParrot/crack-js@main/src/script.min.js"></script>
```

## Documentation

Consider the following example:

```javascript
function callback(combo){
	console.log(combo);
}
new BruteForce(callback, 33, 43, 1, false)
```
`callback` is a callback function. It passes a parameter that is the currently generated permutation.

`33` and `43` define what ascii codes to loop through. Set to `0, 255` to loop through all ascii characters.

`1` defines the number of digits and `false` defines whether it is async or not. Turning off async makes the page unresponsive, but greatly improves speed. The async to non-async ratio is 30000 : 7 milliseconds.

In our case, it prints:
```
!
"
#
$
%
&
'
(
)
*
```
### Cracking a hash using Crack.js**

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

If you return `true` in the callback function, the premutation generator will be terminated. This is important when dealing with hashes of unknown length - not knowing when the program stops will waste a lot of time.

The code prints:

```
hi
```
