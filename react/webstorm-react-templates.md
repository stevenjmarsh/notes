# React Configuration Notes and Templates for WebStorm

## Resources
* https://blog.jetbrains.com/webstorm/2015/10/working-with-reactjs-in-webstorm-coding-assistance/
* https://blog.jetbrains.com/webstorm/2015/12/working-with-reactjs-in-webstorm-linting-refactoring-and-compiling/
* https://github.com/minwe/jetbrains-react
* https://www.jetbrains.com/help/webstorm/2016.2/using-reactjs-in-javascript-and-typescript.html


## Live Templates to Update / Create
* jsx - self closing element   <Component /> (emmet sometimes creates opening and closing tags)
    * determine how to have one shortcut for self closing, one for both tags
* learn how to control attribute value delimeters, between ""  and {}
    * props arguments seem to be able to accept either. but when?
* sst (this.setState)
    * needs a space after :
    * TBD, remove last return (blank line) -it adds a blank line before next line of code (not usually needed)
* pt (individual propType), add another var param / move $END$ to end of line (after comma), so hitting enter last time brings you to end of line (easier to add more lines that way)
* when creating a simple pure function, when getting to the parameters, if you type `props` and hit enter, it expands to this.props, when I really want to jump to the next field 
    * consider modifying the this.props abbreviation to t.p or something (so props doesn't expand to this.props)
* 

## Other WebStorm editor desired changes
* find a plugin that can change/replace '', "", {} around selected words
