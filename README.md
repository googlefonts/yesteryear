# Yesteryear

No source of this family was ever published: the fonts Google Fonts ships
were its only form. The sources in `sources/` were converted from those
fonts with [babelfont-rs](https://github.com/felipesanches/babelfont-rs/tree/2026-11-02), and
build with [gftools-builder](https://github.com/simoncozens/gftools-rust)
and fontc.

The fonts they were converted from remain in the git history.

How these sources were checked against the released fonts (the tools, this family's plan and the logs): https://github.com/felipesanches/gf-source-modernization.

## Earlier sources

Where this family was published before, kept on record; none of these holds a source of it:


## Known differences from the released fonts

These sources rebuild the fonts Google Fonts ships, except for the following, which were reviewed and deliberately left as they are:

- The released font is hinted (TrueType instructions). These sources carry no TrueType instructions, so the build is hinted by ttfautohint: the outlines, spacing and layout are the release's, its rendering at small sizes under a TrueType interpreter is not. Hinting is not compared by the gates.
- The build's GSUB numbers or packs some lookups differently from the release's (fontc places a lookup that only a contextual lookup calls, and packs chained contextual rules, its own way: gfonts-ai-usage-report 22-fontc-problems, problems 12 and 13); every rule is the same and the text shapes identically (tools/functional_gate.py). Decided 2026-10-02: problems that need fontc are disclosed and fixed in fontc later.
