# Alternatives for modeling structural variation

## Similar structure/objects as sequence variants

### Approach

* Add 'state' object to VMC, which represents an extent of sequence that can be expressed relative to the reference genome.
* The presence of a state object signifies an insertion of sequence relative to the reference
* State may be contained in an allele object; this signifies that the location of the new sequence is known
* Create a way of representing imprecise endpoints

### Pros

* Representation of structural variation with minimum additional to model--makes use of existing data structures as possible.
* Maximizes continuity of representation between structural variation detected with techniques that allow the location of insertions of sequence to be known, vs techniques that do not allow this. (microarray vs whole genome sequence)

### Cons

* Encumbers model for represening sequence variants with artifacts necessary for representing structural variants (especially imprecise loci).
* Potentially confuses semantics of model in order to accomodate structural variant concepts with the same model objects?
  * What is 'state'
  * How does it make sense to have a 'state' outside our understanding of 'sequence'


## Different structure/objects from sequence variants

### Approach

* Genomics England
* Distinct objects for representing:
  * Sequence Variants
  * Copy Number Variants
  * Short Tandem Repeats
* Each object contains only the minimum data objects necessary to represent the concept.

### Pros

* No need to 'polute' the representation of sequence variants with the artifacts necessary to represent structural variation.
* Allows for most concise representation of each type of variation

### Cons

* Potential discontinuity in representation from variants detected using methods that allow locations of large insertions to be known, vs ones that do not.
* Propagates more model objects.
* Requires potentially arbitrary distinction for when one model object should be used vs another (when is a deletion a copy number loss? when is a duplication a copy number gain?)
