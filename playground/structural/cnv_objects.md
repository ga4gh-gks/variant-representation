## CNV object representations


#### Example of CNV with start and end intervals

This version expresses the uncertainty about the exact mapping of the start and end positions through "intervals as loci". Those intervals would correspond to the high confidence start and end positions (e.g. taking spacial resolution of an array platform into consideration).

```
{
  "referenceName" : 9,
  "startInterval" : {
    "start" : 21967000,
    "end" : 21968000,  
  }
  "endInterval" : {
    "start" : 21974000,
    "end" : 21975000,  
  }
  "variantType" : {
    "termId" : "SO:0001743",
    "termLabel": "copy_number_loss",
    "info" : {
      "alleleCount" : 0
    }
  }
}
```

#### Example of CNV with start, end and confidence intervals

This version is similar to VCF `INFO:CIPOS` and `INFO:CIEND`.

```
{
  "referenceName" : 9,
  "start: 21967753,
  "end: 21975098,
  "ciStart" : [ 500, 500 ],
  "ciEnd" : [ 500, 500 ],
  "variantType" : {
    "termId" : "SO:0001743",
    "termLabel": "copy_number_loss",
    "info" : {
      "alleleCount" : 0
    }
  }
}
```