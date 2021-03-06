# CMake Project for PDFium

Use this for PDFium development in CLion on a Mac.

## Quick Start

Install (or update) the Chromium depot tools.

In this project's top-level dir, run `fetch pdfium`. Go get some coffee, because this will take a long time.

Install Homebrew in case you don't have it, then run `brew install libjpg zlib libpng icu4c`.

Open the top-level dir in CLion.

In Preferences -> Build, Execution, Deployment -> CMake, add this to the CMake options field:
```
-DCMAKE_PREFIX_PATH="/usr/local/opt/icu4c"
```

Build the **pdfium_test** target.

Edit the pdfium_test run configuration, add as program arguments e.g. `--png --scale=4 your.pdf`, then run it.

## Use with other PDFium Branch or Revision

Check out a PDFium branch, e.g.
```
cd pdfium
git checkout -b chromium/3163 origin/chromium/3163
gclient sync --with_branch_heads --disable-syntax-validation
```
Unfortunately, it's likely that you'll get build errors because of changes in the PDFium file structure not reflected
in CMakeLists.txt.