# Risk zone theme-specific requirements

**Purpose**: Verify that the features provided in the dataset adhere to the theme-specific requirements specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks are performed for every feature in the dataset.

* Check that if a [RiskZone](#RZsource) is associated with a HazardArea, the RiskZone and the HazardArea shall overlap.
* Check that if a [RiskZone](#RZexposedElement) is associated with an ExposedElement, the ExposedElement shall overlap with the RiskZone.


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-NZ](./README.md#ref_TG_DS_NZ) 5.3.6.1

**Test type**: Automated

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression                     |Multiplicity       |Voidable
---------------------------------------------------------- | ------------------------------------- | ------------------|----------
RiskZone.source <a name ="RZsource"></a>	| //schema-element(nz-core:RiskZone)/nz-core:source/@xlink:href | 1 | Yes
RiskZone.exposedElement <a name ="RZexposedElement"></a>	| //schema-element(nz-core:RiskZone)/nz-core:exposedElement/@xlink:href | 1..\* | Yes