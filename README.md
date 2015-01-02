# Size Classes

An attempt to simplify the "breakpoints mess" in web development using something Apple has named *Size Classes* in **Xcode 6** (see [WWDC216][] for details) for creating so-called "Adaptive Layouts".

I still have no idea if it'll work, but I'm going to use it extensively until I know more :)

## Usage

To create "compact" and "regular" styles for a selector:

```less
.header {
	// These styles apply to all size classes
	font: Times, serif;

	// These only applies within the "regular" horizontal size class
	.regular-width({
		font-size: 2.5rem;
	});

	// These only applies within the "compact" horizontal size class
	.compact-width({
		font-size: 1rem;
	});
}
```

### Output (simplified)

```css
.header {
  font: Times, serif;
}
@media only screen and (min-width: 569px) {
  .header {
    font-size: 2.5rem;
  }
}
@media only screen and (max-width: 568px) {
  .header {
    font-size: 1rem;
  }
}
```


## Implementation

It's using [a nifty feature of LESS][LESS-FEATURE], where you can pass a ruleset to a mixin and have it output within a media query, still scoped to the original selector. This lets you keep the rules very close to each other, and it's easy to see which rules apply to the different "sizes".

[WWDC216]: https://developer.apple.com/videos/wwdc/2014/?include=216#216
[LESS-FEATURE]: http://lesscss.org/features/#detached-rulesets-feature
