## CNV object representations

On this page, different options for the representation of copy number variations (CNVs) are proposed, using a "de-normalised" representation (i.e. flat representation of a minimal object structure, with dummy values).

Each example may use different notations for different attributes (e.g., both representation of copy number and positions may vary, allowing more heterogeneity for discussions).

#### Example of CNV with start and end intervals

This version expresses the uncertainty about the exact mapping of the start and end positions through "intervals as loci". Those intervals would correspond to the high confidence start and end positions (e.g. taking spacial resolution of an array platform into consideration).

```json
{
  "referenceName" : 9,
  "startInterval" : {
    "start" : 21967000,
    "end" : 21968000,  
  },
  "endInterval" : {
    "start" : 21974000,
    "end" : 21975000,  
  },
  "state" : {
    "termId" : "SO:0001743",
    "termLabel": "copy_number_loss",
    "info" : {
      "ploidy" : 2,
      "alleleCount" : 0
    }
  }
}
```

#### Example of CNV with start, end and confidence intervals

This version is similar to VCF `INFO:CIPOS` and `INFO:CIEND`.

```json
{
  "referenceName" : 9,
  "start: 21967753,
  "end": 21975098,
  "ciStart" : [ 500, 500 ],
  "ciEnd" : [ 500, 500 ],
  "state" : {
    "termId" : "SO:0001743",
    "termLabel": "copy_number_loss",
    "info" : {
      "ploidy" : null,
      "alleleCount" : 0
    }
  }
}
```

