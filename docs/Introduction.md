# AMWA MS-05-03 NMOS Control Blockspecs \[Work In Progress\]

The NMOS Control Architecture, includes the ability for developers and development support organizations to define standard modules called `blocks` that encapsulate sets of control functions.

A `blockspec` is the formal specification of the contents of a particular type of block. In device design, blockspecs can be instantiated to form blocks.

For example, a blockspec named "MicPre" could describe a particular kind of microphone preamplifier. A 24-channel mixing console's device model could instantiate MicPre 24 times. The result would be 24 microphone preamplifier blocks in the mixing console's NCA control API.

By defining and using standard, reusable blocks, the engineering of interoperable devices and software functions will be eased, and the quality of control among devices increased.

It is anticipated that, over time, organizations will collect blockspecs into libraries from which developers may select useful elements. Discussions are underway for an AMWA public library to be created in further iterations of the working group.

This document relies on previous familiarity with the following existing documents:

- [MS-05-01 NMOS Control Architecture](https://specs.amwa.tv/ms-05-01)
- [MS-05-02 NMOS Control Framework](https://specs.amwa.tv/ms-05-02)
