# Table Tab Identation
This repository describes how to use the Table Tab Identation, why you should use it and some examples.

## What is it
Created to further enhance code readability and simplicity, table tab identation divides similar lines in an invisible table that sorts similar parts of the code together. To shorten the repeated use of the identation, we are going to use TTI (Table Table Identation). This helps you separate arguments of a function, variables from it's value and many other things.

## How to use it
You are free to decide how to divide your data inside of this invisible table, but I came up with some rules that I tend to use that have kept a pretty good work:
- when indenting arguments of a function, you should put the same position arguments, in the same column;
``` javascript
//Don't do this
const origin    = new Vector3(axis.x * 100, axis.y - 25, axis.z / 1000);
const end       = new Vector3(0, 10,25);

//Do this
const origin    = new Vector3(axis.x * 100, axis.y - 25,    axis.z / 1000);
const end       = new Vector3(0,            10,             25);
```
- single lines don't need to be TTIed;
``` javascript
//You don't need to do TTI on a single line
const number = 0;

//But you should use when there is more than one
const number    = 0;
const boolean   = true;
```
- Use the default four space tab for identation;
- Only similar lines should be organized;
``` javascript
//You don't need to organize lines that are different
number = 0;
boolean.parse(number);
```
- After each different content, when they are equal, you throw them to the next column;
``` javascript
//Don't do this
import Package1 from        "packages/firstpackage";
import AnotherPackage from  "packages/secondpackage";
const number =  0;
const boolean = false;

//Do this
import Package1         from "packages/firstpackage";
import AnotherPackage   from "packages/secondpackage";
const number    = 0;
const boolean   = false;
```
- Lines with more than 100 characters don't need this indentation, you can break the single line into multiple ones to keep readability;
``` javascript
//You don't need to TTI this line
const reallyhugeline = new Vector3 (xvalue * multiplier - normalization, yvalue * multiplier - normalization, zvalue * multiplier - normalization);

//You can break into this:
const reallyhugeline = new Vector3 (
        xvalue * multiplier - normalization,
        yvalue * multiplier - normalization,
        zvalue * multiplier - normalization
);
```

## Examples

### First example
Without TTI
``` javascript
import Package1 from "packages/firstpackage";
import AnotherPackage from "packages/secondpackage";
```

Using TTI
``` javascript
import Package1         from "packages/firstpackage";
import AnotherPackage   from "packages/secondpackage";
```

Imagine an invisible table organizing everything
|||
|-|-|
|import Package1|from "packages/firstpackage"|
|import AnotherPackage|from "packages/secondpackage"|

### Second example
Without TTI
``` javascript
const origin = new Vector3(axis.x * 100, axis.y - 25, axis.z / 1000);
const end = new Vector3(0, 10, 25);
```

Using TTI
``` javascript
const origin    = new Vector3(axis.x * 100, axis.y - 25,    axis.z / 1000);
const end       = new Vector3(0,            10,             25);
```

Imagine an invisible table organizing everything
|||||
|-|-|-|-|
|const origin|= new Vector3(axis.x * 100,|axis.y - 25,|axis.z / 1000);|
|const end|= new Vector3(0,|10,|25);|
