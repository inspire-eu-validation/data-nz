# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list vanzed property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following empty code lists:

* [SpecificExposedElementTypeValue](#SpecificExposedElementTypeValue) :  http://inspire.ec.europa.eu/codelist/SpecificExposedElementTypeValue

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
SpecificExposedElementTypeValue <a name ="SpecificExposedElementTypeValue"></a>	| //schema-element(nz-core:ExposedElement)/nz-core:assessmentOfVulnerability/nz-core:VulnerabilityAssessment/nz-core:typeOfElement/nz-core:ExposedElementClassification/nz-core:specificExposedElementType/@xlink:href | 1 | Yes
SpecificExposedElementTypeValue <a name ="SpecificExposedElementTypeValue"></a>	| //schema-element(nz-core:ExposedElementCoverage)/nz-core:typeOfElement/nz-core:ExposedElementClassification/nz-core:specificExposedElementType/@xlink:href | 1 | Yes
SpecificHazardTypeValue <a name ="SpecificHazardTypeValue"></a>	| //schema-element(nz-core:ObservedEvent)/nz-core:typeOfHazard/nz-core:NaturalHazardClassification/nz-core:specificHazardType/@xlink:href | 1 | Yes
SpecificHazardTypeValue <a name ="SpecificHazardTypeValue"></a>	| //schema-element(nz-core:HazardArea)/nz-core:typeOfHazard/nz-core:NaturalHazardClassification/nz-core:specificHazardType/@xlink:href | 1 | Yes
SpecificHazardTypeValue <a name ="SpecificHazardTypeValue"></a>	| //schema-element(nz-core:RiskZone)/nz-core:sourceOfRisk/nz-core:NaturalHazardClassification/nz-core:specificHazardType/@xlink:href | 1 | Yes
SpecificHazardTypeValue <a name ="SpecificHazardTypeValue"></a>	| //schema-element(nz-core:ExposedElement)/nz-core:assessmentOfVulnerability/nz-core:VulnerabilityAssessment/nz-core:sourceOfVulnerability/nz-core:NaturalHazardClassification/nz-core:specificHazardType/@xlink:href | 1 | Yes
