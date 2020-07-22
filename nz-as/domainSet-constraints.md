# domainSet Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following check is performed for every feature in the dataset.

* The [domainSet](#domainSet) shall be a rectified grid or referenceable grid.

The check is performed on all the different feature types that can be present in the dataset:
* ExposedElementCoverage
* HazardCoverage
* ObservedEventCoverage
* RiskCoverage

The element ReferenceableGrid is not available as subtype of the element domainSet, so only the RectifiedGrid element is checked.

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-NZ](./README.md#ref_TG_DS_NZ) 5.3.6.1

**Test type**: Automatic

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression                     |Multiplicity       |Voidable
---------------------------------------------------------- | --------------------------------------|-------------------|----------
domainSet <a name="domainSet"></a> | //schema-element(nz-core:ExposedElementCoverage)/gml:domainSet/gml:RectifiedGrid<br>//schema-element(nz-core:HazardCoverage)/gml:domainSet/gml:RectifiedGrid<br>//schema-element(nz-core:ObservedEventCoverage)/gml:domainSet/gml:RectifiedGrid<br>//schema-element(nz-core:RiskCoverage)/gml:domainSet/gml:RectifiedGrid | 1 | No
