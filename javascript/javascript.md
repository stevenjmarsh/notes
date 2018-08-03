# General JavaScript Notes

## Types
* good reference
    - https://codeburst.io/explaining-value-vs-reference-in-javascript-647a975e12a0
* primitives
    - values
    - Boolean, Null, Undefined, String, Number, Symbol
        + note Symbol is new ES6 (they are immutable, and unique)
* objects
    - by reference
    - Object Literals (collection of properties, name value pairs)
    - Dates, Arrays, TypedArray, JSON
    - ES6 objects (new)
        + Set, WeakSet, Map, WeakMap

## Comparison
* ==  compares values of two items (will convert types)
    - aka, Abstract Equality
    - "3" == 3   (true)
    - true == 1   (true)
* === compares value and type 
    - aka, Strict Equality
    - "3" === 3  (false)
    - true === 1 (false)
    - x = 2;   x === 2   (true)
* Object comparison: == , === , Object.is() 
    - object comparison, will return false, unless pointing to the exact same object (false even when two distinctly different objects contain the same values)
        + let car1 = { color: 'blue', wheels: 4 }
        + let car2 = { color: 'blue', wheels: 4 }
        + let car3 = car1;
        + car1 == car2;             // (false)
        + car1 === car2;            // (false)
        + Object.is(car1, car2);    // (false)
        + car1 == car3;             // (true)
        + car1 === car3;            // (true)
        + Object.is(car1, car3);    // (true)
* FYI, jest expect()
    - .toBe()  uses "===" (is a strict comparison)
    - .toEqual() does a deep value comparison  (recursively check equality of all fields)

## Assignment
* when assigning a variable directly to an object, that variable references the source object 
    - const carCopy = car1;
    - carCopy.wheels = 25;   // will modify car1;

## Cloning Objects (deep clone)
* Object.assign() and spread operator [...obj] or {...obj} DO NOT deep clone
    - will clone an object's top level primitive properties
    - will clone array elements that are primitive 
    - will NOT clone object properties that are objects (they will be referenced)
    - will NOT clone array elements that are objects (they will be referenced)
* To ensure cloning of objects, use a library deep clone function
    - `_.cloneDee()`

