# Copies vs Length

## Alternatives:

* Represent copies as number of copies of the referred-to sequence
* Use 'length' instead, (per issue #9, Eric Moyer)--permits flexibility in representing STRs
* Use both, length is more appropriate for STRs and copy number is more appropriate for copy number increase

## Pros vs Cons

* Copies is more appropriate for CNVs
* Length allows for more flexibility of represetation of STRs, otherwise would need to use two alleles in haplotype object, or fall back to bare string representation3
* Both adds complexity to object, but permits flexible usage

# Representation of copy number increase with unknown location

## Alternatives:

* Represent as bare state object
* Represent as state object contained by a wrapper class
  * Wrapper is a statement that state exists as an 'extra' sequence in the context of a genome.
  
## Pros vs Cons

* When one observes 'I have a copy number increase of this region of 3', one is really making a statement about not just that region, but also an individual's genome. If you do a microarray, you know that there's not another copy of that area lurking somewhere else. 'Region' is useful for this construct, but doesn't really capture what we're trying to represent.

### Genomic Sequence Count
```
{
    "sequence": <state> | <location>
    "count": integer
}
```

# Coordinates of an allele that contains a copy number increase

## Alternatives

* Use same location in allele object as in state object
  * Would require the copy number for a wild-type allele to be '1'
* Use a point for insertion of sequence in allele object
  * Copy number would be 0 for wild-type
  
## Pros vs Cons
  

