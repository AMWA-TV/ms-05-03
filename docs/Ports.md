# Ports

An object's ports may be defined in one of two ways, depending on its nature.

* For some kinds of objects (_concrete_ objects), the set of ports is fixed.  For example:
  * A block's ports are defined in the block port collection of its blockspec, as described above.
  * A bespoke multichannel audio processor (e.g. a Dolby 5.1 processor) will have statically defined inputs and outputs.

* For other kinds of objects (_port-flexible_ objects), the set of ports may be defined by the blockspec that deploys them. For example:
  * A gain object may be deployed as a monaural control (one input, one output) in one case, but as a stereophonic control (two inputs, two outputs) in another.
  * A matrix object may be deployed with different matrix sizes in different cases; in all cases, its port list will correspond to its size. For instance, a 2x2 matrix will have two input ports and two output ports, while a 4x16 matrix will have four input ports and sixteen output ports.
