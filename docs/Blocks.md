# Blocks

Blocks are instances of the `ncBlock` control class. The formal specifications of `ncBlock` and its properties are in `NC-Framework`.

The contents of a block are control objects, each of which is an instance of an NCA control class that defines a small API for accessing a particular device control or monitoring function. The complete control API of a block is the union of all its individual objects' APIs; the complete control API of an NCA device is the union of all its blocks' APIs.
