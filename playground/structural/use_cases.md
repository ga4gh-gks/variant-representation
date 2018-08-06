# Single nucleotide repeat
![single nucleotide repeat](img/single_nucleotide_repeat.png)

# Short tandem repeat
![short tandem repeat](img/short_tandem_repeat.png)

# Tandem duplication
![tandem duplication](img/tandem_duplication.png)

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

# Tandem copy number increase, multiple copies
![tandem copy number increase](img/tandem_three_copy.png)

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

# Duplication with Translocation, same chromosome
![duplication with transloc same chr](img/duplication_transloc_same_chr.png)

# Duplication with Translocation, different chromosome
![duplication with transloc different chr](img/duplication_transloc_different_chr.png)

# Duplication with unknown location
![duplication unknown location](img/duplication_unknown_location.png)

```
{
    // Location
    "LOC32":{
        "id":"LOC32",
        "interval":{
            "start":{max: 11850846},
            "end": {min: 11867218}},
        "sequence_id":"NC_000001.10",
    },
    // State
    "clinvar:223138":{
        "id":"clinvar:223138",
        "location_id":"LOC32",
        "copies": {min: 5, max: 8}
    }
}
```
