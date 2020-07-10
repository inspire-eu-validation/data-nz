# Feature references

**Purpose**: Verify that referenced features can be retrieved.

**Prerequisites**

**Test method**

* Verify that any feature reference in an association role is publicly accessible via HTTP, i.e. inspect all relevant properties. If a reference (@xlink:href) has a value that starts with "#", verify that an element with a `gml:id` attribute with the referenced identifier exists in the same document. If the reference starts with "http", verify that a HTTP GET request to the URI retrieves an XML document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following association roles:

* [RiskZone.exposedElement](#RZexposedElement): ExposedElement or ExposedElementCoverage
* [RiskZone.source](#RZsource): HazardArea or HazardCoverage
* [HazardArea.source](#HAsource): ObservedEvent or ObservedEventCoverage
* [ObservedEvent.isMonitoredBy](#OIisMonitoredBy): EnvironmentalMonitoringProgramme

There are also the following association roles related to the Coverage feature types:

* RiskCoverage.exposedElement: ExposedElement or ExposedElementCoverage 
* RiskCoverage.source: HazardArea or HazardCoverage 
* HazardCoverage.source: ObservedEvent or ObservedEventCoverage 
* ObservedEventCoverage.isMonitoredBy: EnvironmentalMonitoringProgramme

but, due to the double inheritance present in the UML model and not encoded in the GML application schema, this associations cannot be present in the dataset. For this reason, the related checks are not implemented at the moment.

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                         |  XPath expression    | Multiplicity    | Voidable
------------------------------------ | ---------------------|-----------------|------------
RiskZone.exposedElement <a name ="RZexposedElement"></a>	| //schema-element(nz-core:RiskZone)/nz-core:exposedElement/@xlink:href | 1..\* | Yes
RiskZone.source <a name ="RZsource"></a>	| //schema-element(nz-core:RiskZone)/nz-core:source/@xlink:href | 1 | Yes
HazardArea.source <a name ="HAsource"></a>	| //schema-element(nz-core:HazardArea)/nz-core:source/@xlink:href | 0..\* | Yes
ObservedEvent.isMonitoredBy <a name ="OIisMonitoredBy"></a>	| //schema-element(nz-core:ObservedEvent)/nz-core:isMonitoredBy/@xlink:href | 0..\* | Yes
