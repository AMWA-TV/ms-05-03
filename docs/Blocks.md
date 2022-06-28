# Blocks

Blocks are instances of the `ncBlock` control class. The formal specifications of `ncBlock` and its properties are in [MS-05-02 NMOS Control Framework](https://specs.amwa.tv/ms-05-02).

Blocks are the means by which a device model can be collected, nested and discovered.

The contents of a block are control objects which may include other nested blocks representing substructures of the device model.

Each control object is an instance of an NCA control class that defines a small API for accessing a particular device control or monitoring function. The complete control API of a block is the union of all its individual objects' APIs; the complete control API of an NCA device is the union of all its blocks' APIs.
