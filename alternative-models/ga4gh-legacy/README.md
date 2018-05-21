---
title: The GA4GH Leagacy Variant Model
---

## The GA4GH Leagacy Variant Model

The GA4GH variant model is a VCF-derived data schema, linking _variant description_ and occurrences (_calls_) towards the representation of _callsets_ (i.e., variants of a biosample derived analysis).

At the time of schema freezing, the variant types represented and documented through the GA4GH schema were:

* precise sequence variants, i.e. reference base(s) and alternate base(s)
* CNV, i.e. copy number variants represented by start (with _cipos_ probability interval) and end (with _ciend_) positions and _variant_type_ (i.e., _DUP_, _DEL_) 

Additional variant types (e.g. breakends, fusions) had not yet been adopted.

The original GA4GH variant model development can be found at [ga4gh-schema](https://github.com/ga4gh/ga4gh-schemas/blob/master/src/main/proto/ga4gh/variants.proto).
