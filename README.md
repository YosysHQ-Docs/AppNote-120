YosysHQ AppNote 120 -- Weak precondition cover and witness for SVA properties
===================================

Abstract
========

Formal Verification uses mathematical techniques to exhaustively prove
that a property, or an obligation that must hold in a system, is proven
under all possible conditions or inputs of an RTL design. When this
property is falsified, a waveform or trace showing the sequence of
inputs leading to the violation is produced by the tool, but when no
violation occurs, the tool reports that a property is proven and no
further evidence of what trace leads to the proof of such assertion is
generated. Furthermore, assertions and assumptions are often composed of
a precondition (an expression that specifies when a property should be
checked) and a consequence (the condition that must hold for all
possible paths in the design). When the precondition is not triggered
for any reason, the assertion will pass vacuously [1]_.

Organisation
============

**Introduction:** The definition of weak precondition cover and witness
is described. This section shows some examples where problems such as
vacuity can lead to erroneous conclusions by the design or verification
engineer. Also this section presents a method to extract an evidence of
a proven property in a form of a waveform. This section is mostly
theoretical and explains in detail the rationale behind these special
covers.

**Methodology**: This section delves into the practical application of
the weak precondition cover and witness constructs, applied in two main
case studies using a *valid-ready AXI4 faulty design* to trivially
exemplify the application of both covers, and a more advanced design that
uses an abstract implementation of the *AMBA AXI5 CHI Link FSM* which shows
more interesting scenarios not covered by the set of assertions. This section
ends with a guide that shows how to debug unreached witness covers.
Section *Methodology* is more hands-on-work.
