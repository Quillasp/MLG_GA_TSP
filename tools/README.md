This directory contains 3rd-party tools used by this repository.

# pandox-xhtml

This repository contains common XML transformations from Pandoc XML to
ConTeXt XML.

Homepage: <https://github.com/ousia/from-pandoc-to-context>.
License: GPLv2.

To update:

```
$ git subtree pull --prefix="tools/pandoc-xhtml" \
  https://github.com/ousia/from-pandoc-to-context master
```

# inkscape

There are multiple pandoc-plantuml filters out there, for instance there's an
implementation in [in haskell][pandoc-plantuml-filter-haskell] and another one
[in python][pandoc-plantuml-filter-python].
Sadly the one in python does not allow specifying the image output format, hence
plantuml uses SVG by default.

[pandoc-plantuml-filter-haskell]: https://github.com/kbonne/pandoc-plantuml-filter
[pandoc-plantuml-filter-python]: https://github.com/timofurrer/pandoc-plantuml-filter

[ConTeXt doesn't natively support SVG images][context-native-fmts], so it will
try to use inkscape to convert the SVG to pdf.
Unfortunatelly [inkscape changed its command line options][inkscape-pls] in
[release 1.0][inkscape-releases].

[context-native-fmts]: https://wiki.contextgarden.net/Command/externalfigure#Natively_supported_image_formats
[inkscape-pls]: https://graphicdesign.stackexchange.com/a/56792
[inkscape-releases]: https://inkscape.org/release/inkscape-1.0/

This executable adapts the flags passed to inkscape.
