# Blockspec library references

As noted in the introduction above, it is anticipated that blockspecs will be collected into libraries for developer reuse. To manage the incorporation of library blockspecs:

* Each blockspec has a globally unique ID - probably a UUID
* A blockspec reference may be associated with an arbitrary `library ID` that designates a particular blockspec library
* Library ID values are local to each blockspec file.

Blockspec library IDs are local to the blockspec in which they are used.  A separate section of the blockspec file (the `library directory`) attaches each library ID to a physical library.
