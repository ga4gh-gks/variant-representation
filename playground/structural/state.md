# State

## Biological definition

A sequence that may or may not have a known location, or is complex, such as copy number variation or tandem repeats.

## Computational definition

The existence of a sequence change

## Information Model

### id
**type**: id

**label**: optional

**description**:State object identifier; must be unique within document

### sequence
**type**: Sequence

**label**: required

**description**: Sequence that is included or copied

### location_id
**type**: Identifier

**label**: required

**description**: Reference to a subsequence that is included or copied

### copies
**type**: Integer

**label**: optional

**description**: Number of repeats of sequence, default 1.

## Examples

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
