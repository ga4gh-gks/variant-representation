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
  "start": 21967753,
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

#### Example of CNV with information about break ends

In this example, a duplicated sequence has information about the locus of the inserted additional copy (here inserted into another chromosome).

```json
{
  "id" : 3eb13749-176c-4eb1-9403-a1478bcfec27,
  "referenceName" : 8,
  "start": {
    "position" : 121866264,
    "mate_id" : "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448"
  },
  "end": {
    "position" : 125065235,
    "mate_id" : "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448"
  },,
  "ciStart" : [ 500, 500 ],
  "ciEnd" : [ 500, 500 ],
  "state" : {
    "termId" : "SO:0001742",
    "termLabel": "copy_number_gain",
    "info" : {
      "ploidy" : 2,
      "alleleCount" : 3
    }
  }
},
{
  "id": "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448"
  "referenceName" : 11,
  "start": 98780212,
  "end": 98780212,
  "ciStart" : [ 500, 500 ],
  "ciEnd" : [ 500, 500 ],
  "state" : {
    "termId" : "SO:0001873",
    "termLabel": "interchromosomal_breakpoint",
    "info" : {}
  }
}
```

