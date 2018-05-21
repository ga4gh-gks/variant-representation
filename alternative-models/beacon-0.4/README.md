---
title: The Beacon v0.4 Variant (Query) Model
---

## The Beacon v0.4 Variant (Query) Model

Beacon doesn't provide a representational but rather a query model. Also, specifications so far only document the use against a reference genome edition (e.g. _GRCh38_), and not against arbitrary sequence IDs.

Starting with [version 0.4](), _Beacon_ has extended the original "one SNV/Indel at a precise position" query model through the addition of range queries with intervals for both start and end position. Their use for now has only be documented for matching structural variants (i.e. `DUP`, `DEL`). Documentation about the use of the query options can be found through the [Beacon+ documentation](http://info.progenetix.org/howto/beacon-range-matches.html), in the [Beacon Wiki](https://github.com/ga4gh-beacon/specification/wiki/Beacon-Queries) and as part of the [ELIXIR Beacon innstructions](https://github.com/ga4gh-beacon/beacon-elixir/tree/v0.4) doumentation.

