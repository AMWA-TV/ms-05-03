# Blockspec contents

The formal specification of the blockspec format is described in JSON schemas. See the JSON Schemas section.
The elements of a blockspec are as follows:

* Header data
  * Identification of the blockspec and its parent, if any.
  * A simple text description of the blockspec.

* Collection property specifications
  * Block port collection: List of port descriptors belonging to the block, for media signal flows into and out of the block.
  * Signal path collection: List of signal paths descriptors inside the block

* Member specifications
  * List of definitions of the control objects the block contains.
  * In NCA, a block is a control object. Therefore, nested blocks will be in the member specification list.

All subschemas composing the blockspecs file schema may have a `comment` property which may be used for adding explanatory notes.
