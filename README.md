# How to debug node.js addons in xcode?

I recently started programming native addons but couldn't find any information about debugging this.
After digging for couple nights, I found very easy solution, so going to share it with you.

This repository serves as a quick reference point for future and current node.js addon developers.

To debug native addons generate an xcode project file, from the root of your project (where `binding.gyp` lives):

```
node-gyp configure -- -f xcode
```

This will create `./build/binding.xcodeproj` folder, which you can open:

```
open build/binding.xcodeproj
```

Once project is opened, make sure to configure the scheme.  Open `Product -> Scheme -> Edit Scheme`, and then:

1. Select `Info -> Executable -> Other` and enter path to node executable
2. Select `Arguments` and enter full path to the javascript file which invokes native addon.

# [screencast demo](https://www.youtube.com/watch?v=DND2H2-XfAc)


