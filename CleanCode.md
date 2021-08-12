# Clean Code Principles 

### 1.Magic Numbers


```
//Bad practice
for(let i = 0; i < 50; i++){
    //do something
}

//Good practice
let NUMBER_OF_STUDENTS= 50
for(let i = 0; i < NUMBER_OF_STUDENTS; i++){
    //do something
}
```
### 2. Deep Nesting
```
// bad practice
const array = [ [ ['Shoaib Mehedi'] ] ]
array.forEach((firstArr) =>{
    firstArr.forEach((secondArr) => {
        secondArr.forEach((element) => {
            console.log(element);
        })
    })
})

// good practice
const array = [ [ ['Shoaib Mehedi'] ] ]
const getValuesOfNestedArray = (element) => {
    if(Array.isArray(element)){
        return getValuesOfNestedArray(element[0])
    }
    return element
}
getValuesOfNestedArray(array)
```
### 3. Comments :
   Comments should be good, but your code needs to be self-explanatory.
so Write less Comments.

### 4. Avoid Large Functions
```
// bad practice
const addSub = (a,b) => {
    // add
    const addition = a+b
    // sub
    const sub = a-b
    // returning as a string
    return `${addition}${sub}`
}

// good practice
// add
const add = (a,b) => {
    return a+b
}
// sub
const sub = (a,b) => {
    return a-b
}
```
### 5. Code Repetition
Dont Repeat Code. use function
```
// bad practice
const array = [ [ ['Shoaib Mehedi'] ] ]
array.forEach((firstArr) =>{
    firstArr.forEach((secondArr) => {
        secondArr.forEach((element) => {
            console.log(element);
        })
    })
})

// good practice
const array = [ [ ['Shoaib Mehedi'] ] ]
const getValuesOfNestedArray = (element) => {
    if(Array.isArray(element)){
        return getValuesOfNestedArray(element[0])
    }
    return element
}
getValuesOfNestedArray(array)
```
### 6. Variable Naming
Camel case is the naming standard for both variables and functions,also other identifiers.

### 7.Meaningful Names
Always use a meaningful name for variables, functions, and others. Choose a name that expresses the meaning of your purpose.
> for getting the **user's bank information**,
>>dont use **getUserInfo** use **getUserBankInfo**

### 8. Favor Descriptive Over Concise
```
//We want a function for search user against phone no
//Bad practice
const searchUser = (phone) => {
//Do something
}
//Good practice
const searchUserByPhoneNo = (phone) => {
//Do something
}
```
### 9. Use Consistent Verbs per Concept
If we need a CRUD function, we use `create`, `get`, or `update` with the name.
If we need to get user info from the database, Dont use various naming: `userInfo`, `user`, or `fetchUser`
- Just Use `getUser`

### 10.Use Nouns for Class Name & Use PascalCase
Dont use verbs for naming classes
```
//bad practice
class MakeCar = {
    //...
}
//Good practice
class Car = {
    //...
}
```
### 11. Capitalize Constant Values (SNAKE UPPER CASE)

> const DAYS_IN_A_YEAR = 365;

### 12. Avoid One-Letter Variable Names
```
//bad practice
const q = () => {
    //....
}
//good practice
const query = () => {
    //....
}
//this is also okay
for(let i = 0;i < 10; i++){
    //...
}

```

### 13.General rules
- KISS : Keep It Simple Stupid
- DRY : Don't Repeat Yourself.
- YAGNI : You Aren't Gonna Need It
- Follow standard conventions.
- Boy scout rule. Leave the campground cleaner than you found it.
- Always find root cause. Always look for the root cause of a problem.



### 14.Design rules
- Keep configurable data at high levels.
- Prefer polymorphism to if/else or switch/case.
- Separate multi-threading code.
- Prevent over-configurability. 
- Use dependency injection.
- Follow Law of Demeter. A class should know only its direct dependencies.

## 15.Understandability tips
- Be consistent. If you do something a certain way, do all similar things in the same way.
- Use explanatory variables.
- Encapsulate boundary conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
- Prefer dedicated value objects to primitive type.
- Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
- Avoid negative conditionals.

### 16.Names rules
- Choose descriptive and unambiguous names.
- Make meaningful distinction.
- Use pronounceable names.
- Use searchable names.
- Replace magic numbers with named constants.
- Avoid encodings. Don't append prefixes or type information.

### 17.Functions rules
- Small.
- Do one thing.
- Use descriptive names. 
- Prefer fewer arguments.
- Have no side effects.
- Don't use flag arguments. Split method into several independent methods that can be called from the client without the flag.

### 18. Comments rules
- Always try to explain yourself in code.
- Don't be redundant.
- Don't add obvious noise.
- Don't use closing brace comments.
- Don't comment out code. Just remove.
- Use as explanation of intent.
- Use as clarification of code.
- Use as warning of consequences.

### 19.Source code structure
- Separate concepts vertically.
- Related code should appear vertically dense.
- Declare variables close to their usage.
- Dependent functions should be close.
- Similar functions should be close.
- Place functions in the downward direction.
- Keep lines short.
- Don't use horizontal alignment.
- Use white space to associate related things and disassociate weakly related.
- Don't break indentation.

### 20.Objects and data structures
- Hide internal structure.
- Prefer data structures.
- Avoid hybrids structures (half object and half data).
- Should be small.
- Do one thing.
- Small number of instance variables.
- Base class should know nothing about their derivatives.
- Better to have many functions than to pass some code into a function to select a behavior.
- Prefer non-static methods to static methods.
### 21.Tests
- One assert per test.
- Readable.
- Fast.
- Independent.
- Repeatable.
### 22.Code smells
- Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
- Fragility. The software breaks in many places due to a single change.
- Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
- Needless Complexity.
- Needless Repetition.
- Opacity. The code is hard to understand.


#### References:
https://www.markdownguide.org/basic-syntax
https://www.markdownguide.org/extended-syntax/
https://x-team.com/blog/principles-clean-code/
https://betterprogramming.pub/12-conventions-for-writing-clean-code-e16c51e3939a
https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29

