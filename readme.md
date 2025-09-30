## ODRL-DPV

The ODRL-DPV ontology is an integration of ODRL2.2 and the OWL profile of DPV 2.1. This integration is based on the integration approach from [Pandit 2024](https://content.iospress.com/articles/semantic-web/sw243583), and updated to match the latest DPV specification. The integrated ontology contains the original ODRL and DPV ontologies with the following modifications:

* `odrl:Action` is now a class
* `dpv-owl:Processing` is now a sublcass of `odrl:Action`
* The label of many `dpv-owl:Processing` subclasses has ben renamed to make the distinction from similar ODRL terms explicit. For example `dpv-owl:Delete` now has "Delete Data" as its preferred label, to distinguish it from `odrl:Delete` which can be applied more broadly. Users should choose the more specific dpv-owl terms where possible.
* The specific actions types are defined as instances of either `odrl:Action` or `dpvowl:Processing`, and the more general type of action they specialise is identified using the `rdfs:subClass` relation. While a clear distinction between classes and instances is often preferred, this was done to remain faithful to the structure of the original ontologies and enhance interoperability.
* `dpv-owl:Entity` is now a subclass of `odrl:Party`
* `dpv-owl:Purpose` is now a subclass of `odrl:purpose`
* `dpv-owl:Data` is now a subclass of `odrl:Asset`
* `dpv-owl:LegalAgreement` now a subclass of `odrl:Agreement`
* Several properties, like `dpv-owl:hasLocation`, `dpv-owl:hasJurisdiction`, `dpv-owl:hasApplicableLaw` and `dpv-owl:hasLegalBasis` have been explicitly listed as instances of `odrl:LeftOperand`. This is not intended to be an exhaustive list of left operands.

For the purpose of having refinements for all entities, even if no custom defined ones exist, the following top-level refinements have been added using the UPCAST vocabulary namespace:
* Actions
 * https://eu-upcast.github.io/vocabulary/index-en.html#hasFinishTime
 * https://eu-upcast.github.io/vocabulary/index-en.html#hasStartTime
* Asset
 * https://eu-upcast.github.io/vocabulary/index-en.html#hasCreationTime
 * https://eu-upcast.github.io/vocabulary/index-en.html#hasFormat
* Purpose
 * https://eu-upcast.github.io/vocabulary/index-en.html#isMonitoredBy
 * https://eu-upcast.github.io/vocabulary/index-en.html#hasApprovalFrom

The main prefix used for DPV terms is `https://w3id.org/dpv/owl#`, to align with its usage in the DPV 2.2 files (https://github.com/w3c/dpv/tree/master/2.2). However we have included owl:sameAs relations tp assert the equivalence of these terms with their corresponding versions that use the `https://w3id.org/dpv#` and `https://w3id.org/dpv/dpv-owl#` prefixes.

[*Pandit, H.J. and Esteves, B., 2024. Enhancing Data Use Ontology (DUO) for health-data sharing by extending it with ODRL and DPV. Semantic Web, 15(4), pp.1473-1498.*](https://content.iospress.com/articles/semantic-web/sw243583)
