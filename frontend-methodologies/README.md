*@outdated: This content may be a useful reference but it's not
  how we approach all frontend projects at this point.*

What follows is our preferred methodology for front-end development. Keeping our front-end tooling consistent across projects should help reduce context switching. Refer to the theme in our [Drupal 8 starter](https://github.com/adaptdk/drupal8-starter) for an example implementation.

These rules aren't set in stone. In the [words of Orwell](https://www.writingclasses.com/toolbox/tips-masters/george-orwell-6-questions-6-rules):
> Break any of these rules sooner than say anything outright barbarous.

## Build tool

- [Laravel Mix](https://github.com/JeffreyWay/laravel-mix): Provides a convenient wrapper around webpack. Despite the name, it's not specific to Laravel. It solves the 80% use case really well.

## Typography

- [RFS](https://github.com/twbs/rfs): Responsive type sizing

## CSS

- [Sass](https://sass-lang.com): Do I need to explain? (we prefer the `.scss` syntax)

## VDOM JS Framework

- [Preact](https://preactjs.com/): If you are considering using React, please first consider Preact in order to reduce bundle size.
- [Preact-cli](https://github.com/preactjs/preact-cli): Check out the project templates for good common sense project starting points.

## Component Spacing

- Prefer `margin-bottom` and avoid `margin-top` for component spacing. This helps ensure components can be re-arranged without breaking the layout.
- Use a standard unit for `margin-bottom` so that components will each have the same spacing (further encouraging re-arranging).