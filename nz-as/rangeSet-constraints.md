# rangeSet Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks shall be performed for every feature in the dataset.

* ExposedElementCoverage
	* The [rangeSet](#rangeSetEEC) shall be the level, or intensity, of the vulnerability assessment.
* HazardCoverage
	* The [rangeSet](#rangeSetHC) shall be described by magnitude or intensity, or by the likelihood of occurence.
* ObservedEventCoverage
	* The [rangeSet](#rangeSetOEC) shall be described by magnitude or intensity, or by the likelihood of occurence.
* RiskCoverage
	* The [rangeSet](#rangeSetRC) shall be described by level or intensity.


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-NZ](./README.md#ref_TG_DS_NZ) 5.3.6.1

**Test type**: Manual

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression                     
---------------------------------------------------------- | -------------------------------------
rangeSet <a name="rangeSetEEC"></a> | //schema-element(nz-core:ExposedElementCoverage)/gml:rangeSet
rangeSet <a name="rangeSetHC"></a> | //schema-element(nz-core:HazardCoverage)/gml:rangeSet
rangeSet <a name="rangeSetOEC"></a> | //schema-element(nz-core:ObservedEventCoverage)/gml:rangeSet
rangeSet <a name="rangeSetRC"></a> | //schema-element(nz-core:RiskCoverage)/gml:rangeSet
