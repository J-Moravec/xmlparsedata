
# xmlparsedata Development version

* Re-parse character literals with octal-escaped expressions of width 1 or 2,
  e.g. `"\1"`, to work around a bug (in R<4.3.0) in `utils::getParseData()`
  (#25, @michaelchirico).

* New `expr_as_xml()` to get an XML representation of R expressions (#27 @MichaelChirico).

# xmlparsedata 1.0.5

* Translate `\` in lambda expression to `OP-LAMBDA` (#18 @renkun-ken).

* Drop all control characters, except horizontal tab and newline (#19).

# xmlparsedata 1.0.4

* Translate ] tokens to `OP-RIGHT-BRACKET` instead of
  `OP-RIGHT-BRACE` (#11 @AshesITR).

* `xml_parse_data()` now works if `includeText = FALSE`
  (#14 @renkun-ken).

# xmlparsedata 1.0.3

* Ensure that closing xml-tags for code expressions that end at the same
  position in a file respect start-first-end-last ordering in the produced xml.
  Ensures that the new `equal_assign` token in `getParseData()` for R-3.6 is
  handled appropriately. #5 @russHyde

# xmlparsedata 1.0.2

* Remove control characters `\003`, `\007`, `\010`, `\027`, as they are
  not allowed in XML 1.0, #1 @GregoireGauriot

* Always convert parsed text to UTF-8

# xmlparsedata 1.0.1

* Fix a bug when the input is already a `getParseData()` data frame.
  https://github.com/jimhester/lintr filters the parsed data to include
  individual functions only, but only filters the data frame, not the
  underlying srcrefs, so when we call `getParseData()` on the data frame
  again, we get the data for the whole source file. This is fixed now by
  noticing that the input is already a data frame

# xmlparsedata 1.0.0

First public release.
