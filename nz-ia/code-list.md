# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list vanzed property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following extensible code lists:

* [ExposedElementCategoryValue](#ExposedElementCategoryValue) : http://inspire.ec.europa.eu/codelist/ExposedElementCategoryValue

* [SpecificExposedElementTypeValue](#SpecificExposedElementTypeValue) :  http://inspire.ec.europa.eu/codelist/SpecificExposedElementTypeValue

* [NaturalHazardCategoryValue](#NaturalHazardCategoryValue) : http://inspire.ec.europa.eu/codelist/NaturalHazardCategoryValue

* [SpecificHazardTypeValue](#SpecificHazardTypeValue) : http://inspire.ec.europa.eu/codelist/SpecificHazardTypeValue

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression      |Multiplicity   |Voidable
---------------------------------------------------------- | -----------------------|---------------|---------------------------------
ExposedElementCategoryValue <a name ="ExposedElementCategoryValue"></a>	| //schema-element(nz-core:\*)/nz-core:typeOfElement/nz-core:ExposedElementClassification/nz-core:exposedElementCategory/@xlink:href | 1 | No
SpecificExposedElementTypeValue <a name ="SpecificExposedElementTypeValue"></a>	| //schema-element(nz-core:\*)/nz-core:typeOfElement/nz-core:ExposedElementClassification/nz-core:specificExposedElementType/@xlink:href | 1 | Yes
NaturalHazardCategoryValue <a name ="NaturalHazardCategoryValue"></a>	| //schema-element(nz-core:\*)/nz-core:\*/nz-core:NaturalHazardClassification/nz-core:hazardCategory/@xlink:href | 1 | No
SpecificHazardTypeValue <a name ="SpecificHazardTypeValue"></a>	| //schema-element(nz-core:\*)/nz-core:\*/nz-core:NaturalHazardClassification/nz-core:specificHazardType/@xlink:href | 1 | Yes