# Types to model

* Copy number loss/deletions
* Copy number gain/duplications
* Translocations
* Inversions
* Short tandem repeats
* Imprecise loci

# Imprecise loci

Three alternatives have been proposed, involving modifications to the Interval object:

## Polymorphic definition

Polymorphic definition of Interval, permitting either integer as start and end values,
or a Range as start and end values

Range itself has integer start and end values
Interval : {start: <integer>, end: <integer> } U {start: Range, end: Range}
Range: {start: <integer>, end: <integer>}

## Non-polymorphic definition

Interval defined in terms of Range objects always,
Precise endpoints are defined with Range.start = Range.end

Interval : {start: Range, end: Range}
Range: {start: <integer>, end: <integer>}

## Defined with external annotation

Keep existing definition of Interval, represent imprecision in additional annotation type.


# Copy number loss / Deletions

May need no extension to the VMC beyond imprecise locii

# Copy number gain

Three concepts to represent:

* Insertion of sequence based on known, existing sequence
* Number of copies of that sequence
* Location where the copy was inserted
  * Need to represent more than simple tandem duplication
  * Also need to be able to represent when the location of insertion is unknown,
  as with microarray based detection methods
  
Princples to apply when modelling this:

* Use the existing constructs in the VMC to the maximum extent possible
* Model this by composing small, atomic data types rather than inventing new and complicated ones specific to this type of variation. Ideally we can reuse these when modelling other types of variation.

**Proposal**: Create a State entity that can be referenced by the 'state' property in allele.

One additional copy, unknown location

https://www.ncbi.nlm.nih.gov/clinvar/variation/221409/

```
{
    "LOC32":{
        "id":"LOC32",
        "interval":{
            "start":{max: 11850846},
            "end": {min: 11867218}},
        "sequence_id":"NC_000001.10",
    },
    "clinvar:223138":{
        "id":"clinvar:223138",
        "location_id":"LOC32",
        "identity":null
    }
}
```

Five additional copies, unknown location

https://www.ncbi.nlm.nih.gov/clinvar/variation/221410/

```
{
    "LOC34":{
        "id":"LOC34",
        "interval": {
            "start": {max: 61543299},
            "end": {min: 61548462p}},
        "sequence_id":"NC_000001.10"
    },
    "clinvar:223139":{
        "id":"clinvar:223139",
        "location_id":"LOC34",
        "identity":null,
        "copies":5
    }
}
```

One additional copy, known tandem repeat (referencing clinvar:223138)


```
{
    "LOC32":{
        "id":"LOC32",
        "interval": {
            "start": {max: 61543299},
            "end": {min: 61548462p}},
        "sequence_id":"NC_000001.10",
    },
    "LOC33":{
        "id":"LOC33",
        "start":11850846,
        "end":11850846
    },
    "clinvar:223138":{
        "id":"clinvar:223138",
        "location_id":"LOC32",
        "identity":null
    },
    "clinvarallele:223138":{
        "id":"clinvar:223138",
        "location":"LOC33",
        "state":"clinvar:223138"
    }
}
```
