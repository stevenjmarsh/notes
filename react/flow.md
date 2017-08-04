# Flow notes

## Pros 
* type checking...

## Cons
* makes language verbose, in some case less readable

## Notes 
* The better you know javascript, the easier flow will be 
    - I am still gaining understanding of intermediate / advanced topics, such as class, instances, etc.
* to add insult to injury, you can add eslint flowtype 
    - it's somewhat nice in that it integrates nicely with many editors
    - however, although configurable, it can be more strict than flow 
        + e.g., flow recognizes render, eslint flow does not, and you can't specifically suppress return type warning for just render 
* there are many times I curse flow for saying I have the wrong type, and I think it's unnecessary at that line, but turns out I made a mistake
    - ie, flow complained an element didnt' have value property, I had incorrectly typed the element as an htmldivelement, which indeed does not have a value
* Ways to check or not check 
    - include header at top of file 
    - broad libdef or type annotation definitions: essentially wild card something
    - ingnore next line with FlowFixMe comment

## Resources

## Usage Notes 
* $FlowFixMe - suppressess a flow error message
    - https://wietse.loves.engineering/ignore-a-flowtype-error-on-a-specific-line-14cdfa70a739
