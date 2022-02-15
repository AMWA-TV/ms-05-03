# Introduction

NCA, the NMOS Control Architecture, includes the ability for developers and development support organizations to define standard modules called `blocks` that encapsulate sets of control functions.

A `blockspec` is the formal specification of the contents of a particular type of block. In device design, Blockspecs can be instantiated to form blocks.

For example, a Blockspec named "MicPre" could describe a particular kind of microphone preamplifier.  A 24-channel mixing console's device model could instantiate MicPre 24 times.  The result would be 24 microphone preamplifier blocks in the mixing console's NCA control API.

By defining and using standard, reusable blocks, the engineering of NCA-compliant devices and software functions will be eased, and the quality of control interoperability among devices increased.

It is anticipated that, over time, organizations will collect blockspecs into libraries from which developers may select useful elements. For example, AMWA will probably support one or more public blockspec libraries.

This document relies on previous familiarity with the following existing documents:

* NC-Architecture (NMOS Control Architecture)
* NC-Framework (NMOS Control Framework)
