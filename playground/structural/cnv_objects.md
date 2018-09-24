## CNV object representations

On this page, different options for the representation of copy number variations (CNVs) are proposed, using a "de-normalised" representation (i.e. flat representation of a minimal object structure, with dummy values).

Each example may use different notations for different attributes (e.g., both representation of copy number and positions may vary, allowing more heterogeneity for discussions).

**These examples do not intend to represent "solutions" or exact implementations, but rather demonstrate possible options as basis for discussion.**

#### Example of CNV with start and end intervals

This version expresses the uncertainty about the exact mapping of the start and end positions through "intervals as loci". Those intervals would correspond to the high confidence start and end positions (e.g. taking spacial resolution of an array platform into consideration).

```json
{
  "referenceName" : 9,
  "start" : 
    "location" : {
      "min" : 21967000,
      "max" : 21968000,
      "id" : "loc_9_21967000_21968000"
    }
  },
  "end" : 
    "location": {
      "min" : 21974000,
      "max" : 21975000,  
      "id" : "loc_9_21974000_21975000"
    }
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

#### Example of CNV with information about break ends

In this example, a duplicated sequence has information about the locus of the inserted additional copy (here inserted into another chromosome).

```json
{
  "id" : "3eb13749-176c-4eb1-9403-a1478bcfec27",
  "referenceName" : 8,
  "start": {
    "location" : { 
      "min" : 121866101,
      "max" : 121867002
    },
    "mate_id" : "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448"
  },
  "end": {
    "location" : { 
      "min" : 125065235,
      "max" : 125065235
    },
    "mate_id" : "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448"
  },
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
  "id": "b2cd2a19-9baf-4fb6-b92d-b0fa4b832448",
  "referenceName" : 11,
  "start": {
    "location": {
      "min" : 98780212,
      "max" : 98780212
    }
  }, 
  "end": {
    "location": {
      "min" : 98780212,
      "max" : 98780212
    }
  }, 
  "state" : {
    "termId" : "SO:0001873",
    "termLabel": "interchromosomal_breakpoint",
    "info" : {}
  }
}
```

#### For comparison (not recommended) - Example of CNV with start, end and confidence intervals

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


