
## Meteor & React Technical Considerations
* remove blaze: [steps here, scroll down a little](https://guide.meteor.com/react.html#using-with-meteor)
* use [container pattern](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0#.che672mvv) 
* Data Loading / Reactive Data
    - first step, just write nonreactive standard react 
    - see posts: 
        + [Meteor 1.3 & React composition with reactive data](https://thoughts.spacedojo.com/meteor-1-3-and-react-composition-with-reactive-data-b0bb3282fea#.jg3k0sl74)
        + [Discover Meteor, data loading react (4 techniques)](https://www.discovermeteor.com/blog/data-loading-react/)
    - __don't use mixins__
    - look at React-Komposer or TrackerReact
* Locale: [universe:i18n](https://github.com/vazco/meteor-universe-i18n) (per Meteor Guide)
* look at FontAwesome (PostCSS may be overkill)
* look at pure.css grids
* look for various react packages at [thereactivestack](https://github.com/thereactivestack)

## Error Handling
### Server Side
* Throwing errors from methods, and [Error types](https://guide.meteor.com/methods.html#throwing-errors)
