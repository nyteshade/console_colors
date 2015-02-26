## Console-Colors
This module provides ANSI colorized logging statements which can be used to more easily identify errors, info statements and warnings in your servers logs at a glance. Sometimes the output generated, especially by complex applications can be quite large and it is easy to miss crucial bits of information you're looking for as an engineer.

### How It Works
While this script would technically work (*or be made to work*) in a browser, the console output would be even harder to read in those environments and the logging statements wouldn't be in color; defeating the whole purpose.

What it does is safely package references to the original console['*'] functions in the global/window scope and route them through a function that, while preserving the output of a normal console.log, prepends and appends some ANSI CSI codes to do so. This package depends on a tiny npm module called node-csi which, as you might imagine, provides many of the ANSI CSI escape sequences in an easier to use and reference manner.

### Version

1.0.1 - This is essentially the first commit and provides basic functionality with very little documentation or extensibility.

### Potential Plans
If there was a desire for it, I could add more features. If you think something should be here that isn't, send me a pull request or suggest the feature to me directly.

#### Installation
`npm install console-colors`

Then somewhere within your node.js application, usually in the app.js, do the following:

`require('console-colors').patchConsole();`

#### Notes
While it is highly unlikely that you'd need the functionality, the console can be unpatched as easily as it is patched. To do so, simply invoke the following:

`require('console-colors').unpatchConsole();`
