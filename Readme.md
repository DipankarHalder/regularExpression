# @Regular Expression  or /regex/
Regular expressions are patterns used to match character combinations in strings or text. In JavaScript, regular expressions are also objects.
<br><br>

### @ - Regex uses
1. Validate user input
2. Search inside text
<br><br>

### @ - Regex methods
> * `exec()` &nbsp;-&nbsp; Executes a **search for a match in a string**. It returns an **array of information or null** on a mismatch.
> * `test()` &nbsp;-&nbsp; Tests for a **match in a string**. It returns **true** or **false**.
> * `match()` &nbsp;-&nbsp; Returns an **array containing all of the matches**, including capturing groups, or **null if no match** is found.
> * `search()` &nbsp;-&nbsp; Tests for a **match in a string**. It returns the index of the match, or **-1 if the search fails**.
> * `split()` &nbsp;-&nbsp; Uses a regular expression or a fixed **string to break a string** into an **array of substrings**.
> * `replace()` &nbsp;-&nbsp; Executes a search for a match in a string, and replaces the matched substring with a replacement substring.
> * `matchAll()` &nbsp;-&nbsp; Returns an **iterator containing all of the matches**, including capturing groups.
> * `replaceAll()` &nbsp;-&nbsp; Executes a **search for all matches in a string**, and replaces the matched **substrings with a replacement substring**.

<br><br>

### @ - Advanced searching with flags
Regular expressions have six optional flags that allow for functionality like global and case insensitive searching.

* `d` - Generate indices for substring matches. <br>
```javascript
// RegExp.prototype.hasIndices (Corresponding property)
const regex = new RegExp('foo', 'd');
console.log(regex.hasIndices);                      // output: true
```

* `g` &nbsp;-&nbsp; Global search.
```javascript
// RegExp.prototype.global (Corresponding property)
const regex = new RegExp('foo', 'g');
console.log(regex.global);                          // output: true
```

* `i` &nbsp;-&nbsp; Case-insensitive search.
```javascript
// RegExp.prototype.ignoreCase (Corresponding property)
const regex1 = new RegExp('foo');
const regex2 = new RegExp('foo', 'i');
console.log(regex1.test('Football'));               // output: false
console.log(regex2.ignoreCase);                     // output: true
```

* `m` &nbsp;-&nbsp; Multi-line search.
```javascript
// RegExp.prototype.multiline (Corresponding property)
const regex1 = new RegExp('^football');
const regex2 = new RegExp('^football', 'm');
console.log(regex1.multiline);                      // output: false
console.log(regex2.multiline);                      // output: true
console.log(regex1.test('rugby\nfootball'));        // output: false
console.log(regex2.test('rugby\nfootball'));        // output: true
```

* `s` &nbsp;-&nbsp; Allows . to match newline characters.
```javascript
// RegExp.prototype.dotAll (Corresponding property)
const regex1 = new RegExp('foo', 's');
const regex2 = new RegExp('bar');
console.log(regex1.dotAll);                         // output: true
console.log(regex2.dotAll);                         // output: false
```

* `u` &nbsp;-&nbsp; "unicode"; treat a pattern as a sequence of unicode code points.
```javascript
// RegExp.prototype.unicode (Corresponding property)
const regex1 = new RegExp('\u{61}');
const regex2 = new RegExp('\u{61}', 'u');
console.log(regex1.unicode);                        // output: false
console.log(regex2.unicode);                        // output: true
console.log(regex1.source);                         // output: "a"
console.log(regex2.source);                         // output: "a"
```

* `y` &nbsp;-&nbsp; Perform a "sticky" search that matches starting at the current position in the target string. See sticky.
```javascript
// RegExp.prototype.sticky (Corresponding property)
const str1 = 'table football';
const regex1 = new RegExp('foo', 'y');
regex1.lastIndex = 6;
console.log(regex1.sticky);                         // output: true
console.log(regex1.test(str1));                     // output: true
console.log(regex1.test(str1));                     // output: false
```














<!-- | Flag | Description | Corresponding property |
| ----------- | ----------- | ----------- |
| `d` |  | RegExp.prototype.hasIndices |
```javascript
const regex1 = new RegExp('foo', 'd');
console.log(regex1.hasIndices); // output: true
``` -->