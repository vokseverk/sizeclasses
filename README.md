# Size Classes

An attempt to simplify the "breakpoints mess" in web development using something Apple has named *Size Classes* in **Xcode 6** (see [WWDC216][] for details) for creating so-called "Adaptive Layouts".

I still have no idea if it'll work, but I'm going to use it extensively until I know more :)

## Implementation

I'm using [a nifty feature of LESS][LESS-FEATURE], where I can pass a ruleset to a mixin and have it output within a media query, still scoped to the original selector. This lets me keep the rules very close to each other, and it's easy to see which rules apply to the different "sizes".

[WWDC216]: https://developer.apple.com/videos/wwdc/2014/?include=216#216
[LESS-FEATURE]: http://lesscss.org/features/#detached-rulesets-feature