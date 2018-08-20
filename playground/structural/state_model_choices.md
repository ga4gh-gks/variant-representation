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

# Sequence reference in Genomic Sequence Count

## Alternatives:

* Use State object as reference
* Use Location object as reference

## Pros vs cons

* (potential) confusion when a state including multiple copies is referenced from a sequence count including multiple copies.
  * This probably should not happen
  * But if it does, the meaning isn't incredibly ambiguous; state defines a sequence, and genomic sequence count describes a number of copies of that sequence.
* Given the above should not happen, the reference to a state object is not structurally necessary to describe genomic sequence count.
* It may be structurally useful to maintain the reference to a state object in order to facilitate comparisions with copy number variants where the location of the new sequence is known.
  * Giving 'Genomic Sequence Count' a similar structure to 'State' might be a better way to accomplish this, however.

# Genomic Sequence Count 

## Alternatives: 

* Count only signifies increase in count relative to refrerence
* Count signifies absolute count across genome

## Pros vs cons

* Making 'count' a relative increase makes it impossible to use this form for copy number loss.
  * avoids ambiguity about whether to use genomic sequence count vs allele
* Making 'count' relative also improves ability to compare a 'genomic sequence count' object to a 'state' ojbect
* Making count absolute fits current nomenclature used to describe copy number.

## Edge cases

# Coordinates of an allele that contains a copy number increase

## Alternatives

* Use same location in allele object as in state object
  * Would require the copy number for a wild-type allele to be '1'
* Use a point for insertion of sequence in allele object
  * Copy number would be 0 for wild-type
  
## Pros vs Cons
  

