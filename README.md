# YAML-cheat-sheet

<br><br>

# Guides
- https://rollout.io/blog/yaml-tutorial-everything-you-need-get-started/

<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

# Node.js (https://www.npmjs.com/package/js-yaml)
```javascript
const yaml = require('js-yaml');
const fs   = require('fs');
 
// Get document, or throw exception on error
try {
  const doc = yaml.safeLoad(fs.readFileSync('/home/ixti/example.yml', 'utf8'));
  console.log(doc);
} catch (e) {
  console.log(e);
}
```


<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

```yml
--- // <-- start new document
 doe: "a deer, a female deer"
 ray: "a drop of golden sun"
 pi: 3.14159
 xmas: true // <-- boolean usage
 french-hens: 3
 calling-birds: // <-- ARRAY - ["huey", "dewey", "louie", "fred"]
   - huey
   - dewey
   - louie
   - fred
 xmas-fifth-day: 
   calling-birds: four // <-- no marks needed when string does not have spaces
   french-hens: 3
   golden-rings: 5
   partridges: 
     count: 1
     location: "a pear tree"
   turtle-doves: two
... // <-- end new document
```


<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

# empty field

```yml
title:
    1: String
    2: String2
    3: ~ // alternative you can use aswell null
```

<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

## Array


# equivalent of array of objects in JSON
```yml
/*
{"AAPL": [
  {
    "shares": -75.088,
    "date": "11/27/2015"
  },
  {
    "shares": 75.088,
    "date": "11/26/2015"
  },
]}
*/

AAPL:
  - shares: -75.088
    date: 11/27/2015
  - shares: 75.088
    date: 11/26/2015
    
    
    
    
    
// method #2
/*
{
  "composites": ["role1", "role2"]
}
*/

composites: ["role1", "role2"]
```

<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

# Comments
```yml
# This is a full line comment
foo: bar # this is a comment, too
```


<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

# Comp Modifiers
- Multiline values may end with whitespace, and depending on how you want the document to be processed you might not want to preserve it. YAML has the strip chomp and preserve chomp operators. So, if the value ends with whitespace, like a newline, YAML will preserve it.
```yml
bar: >+
  this is not a normal string it
  spans more than
  one line
  see?
```

