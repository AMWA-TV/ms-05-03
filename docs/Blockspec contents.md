# Blockspec contents

The elements of a blockspec are as follows.  Details of these items follow, beginning with **Header data**, below.

The formal specification of the blockspec format is described in JSON schemas. See the JSON Schemas section.

The structure is:

* Header data
  * Identification of the blockspec and its parent, if any.
  * A simple text description of the block.

* Collection property specifications
  * Block Port collection: List of descriptors of `ncPorts` belonging to the block, for media signal flows into and out of the block.
  * Signal path collection: List of descriptors of signal paths inside the block

* Member specifications
  * List of definitions of the control objects the block contains.
  * In NCA, a block is a control object. Therefore, nested blocks will be in the member specification list.
