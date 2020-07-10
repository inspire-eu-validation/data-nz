# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks are performed for every feature in the dataset.

* Check that if the [sourceOfSpatialRepresentation](#sourceOfSpatialRepresentation) association role is empty, the [geometry](#geometry) of the ExposedElement spatial object shall be provided. If the exposed element spatial object is provided with a spatial representation, then the object does not have to be linked to any other spatial object defined in another INSPIRE theme. If the exposed element spatial object is NOT provided with a spatial representation, then it shall reference another object defined in another INSPIRE theme by using the association sourceOfSpatialRepresentation.
* Check that for the data type [LevelOrIntensity](#LevelOrIntensity) either the qualitative value or the quantitative value is provided.
* Check that for the data type [LikelihoodOfOccurrence](#LikelihoodOfOccurrence) either the qualitative likelihood or the quantitative likelihood is provided.


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
sourceOfSpatialRepresentation <a name="sourceOfSpatialRepresentation"></a> | //schema-element(nz-core:ExposedElement)/nz-core:sourceOfSpatialRepresentation|0..1 |Yes
geometry <a name="geometry"></a> | //schema-element(nz-core:ExposedElement)/nz-core:geometry|0..1 |No
 LevelOrIntensity <a name="LevelOrIntensity"></a> | //schema-element(nz-core:\*)nz-core:LevelOrIntensity/nz-core:qualitativeValue | 1 | Yes 
\- | //schema-element(nz-core:\*)nz-core:LevelOrIntensity/nz-core:quantitativeValue | 1 | Yes
LikelihoodOfOccurrence <a name="LikelihoodOfOccurrence"></a> | //schema-element(nz-core:\*)nz-core:LikelihoodOfOccurrence/nz-core:qualitativeLikelihood | 1 | Yes 
\- | //schema-element(nz-core:\*)nz-core:LikelihoodOfOccurrence/nz-core:quantitativeLikelihood | 1 | Yes