# Implementation Guide CDA FHIR Maps

This Implementation Guide provides maps to transform documents between CDA and FHIR and back. This manual describes for which exchange formats the transformation can be used and how it is executed.   

This description focuses on how to execute the transformation in the local development environment. You can also add your own maps in this context. 

The transformation as a micro service is described [here](https://github.com/ahdis/test.ahdis.ch/blob/master/Transformation_FHIR-CDA.md).


## Supported document types

The maps are intended for the transformation of documents, especially **eMedication documents**, in the context of the **Swiss EPR**.   
*Note: The scope is based on the eMedication case study; there is as yet no final mapping of data types, templates and documents.*

The following document types are supported and examples of these are shown in these directories:

Document type | CDA examples | FHIR examples | Map CDA to FHIR | Map FHIR to CDA
-------- | -------- | -------- | -------- | --------
**Swiss EPR document** | input\cda-ch | input\ch-core | input\maps\CdaChToBundle.map | input\maps\BundleToCdaCh.map
**Medication Card document** | input\cda-ch-emed | input\ch-emed | input\maps\CdaChEmed MedicationCardDocumentToBundle.map | input\maps\BundleToCdaChEmed MedicationCardDocument.map
**Medication Prescription document** | input\cda-ch-emed | input\ch-emed | input\maps\CdaChEmed MedicationPrescriptionDocumentToBundle.map | input\maps\BundleToCdaChEmed MedicationPrescriptionDocument.map
**Medication Dispense document** | input\cda-ch-emed | input\ch-emed | input\maps\CdaChEmed MedicationDispenseDocumentToBundle.map | input\maps\BundleToCdaCh EmedMedicationDispenseDocument.map
**Medication List document** | input\cda-ch-emed | input\ch-emed | input\maps\CdaChEmed MedicationListDocumentToBundle.map | -

***Table 1**: Document types with examples and maps*

### Specification

The example documents are structured according to the CDA/FHIR specifications for the exchange formats. The specification of the eMedication depends on the specification of the Swiss EPR exchange format.

Documents in the context of the Swiss EPR:

* Art-Decor [CDA-CH](https://art-decor.org/art-decor/decor-project--hl7chcda-)
   * [EPR Document (CDA)](https://art-decor.org/art-decor/decor-templates--hl7chcda-?section=templates&amp;id=2.16.756.5.30.1.1.10.1.9&amp;effectiveDate=2019-10-17T15:22:41&amp;language=en-US)
   
* FHIR Implementation Guide [CH Core](http://fhir.ch/ig/ch-core/index.html)
   * [EPR Document (FHIR)](https://build.fhir.org/ig/hl7ch/ch-core//StructureDefinition-ch-core-document-epr.html)

eMedication Documents:

* Art-Decor [CDA-CH-EMED eMedication](https://art-decor.org/art-decor/decor-project--cdachemed-)
   * [Medication Card document (CDA)](https://art-decor.org/art-decor/decor-templates--cdachemed-?section=templates&amp;id=2.16.756.5.30.1.1.10.1.3&amp;effectiveDate=2016-05-13T00:00:00&amp;language=en-US)
   * [Medication Prescription document (CDA)](https://art-decor.org/art-decor/decor-templates--cdachemed-?section=templates&amp;id=2.16.756.5.30.1.1.10.1.4&amp;effectiveDate=2016-05-21T00:00:00&amp;language=en-US)
   * [Medication Dispense document (CDA)](https://art-decor.org/art-decor/decor-templates--cdachemed-?section=templates&amp;id=2.16.756.5.30.1.1.10.1.5&amp;effectiveDate=2016-05-21T00:00:00&amp;language=en-US)   
   * [Medication Dispense document (CDA)](https://art-decor.org/art-decor/decor-templates--cdachemed-?section=templates&id=2.16.756.5.30.1.1.10.1.13&effectiveDate=2018-01-22T15:17:26&language=en-US)   
   
* FHIR Implementation Guide [CH EMED](http://fhir.ch/ig/ch-emed/index.html)
   * [Medication Card document (FHIR)](http://fhir.ch/ig/ch-emed/StructureDefinition-ch-emed-document-medicationcard.html)
   * [Medication Prescription document (FHIR)](http://fhir.ch/ig/ch-emed/StructureDefinition-ch-emed-document-medicationprescription.html)
   * [Medication Dispense document (FHIR)](http://fhir.ch/ig/ch-emed/StructureDefinition-ch-emed-document-medicationdispense.html)
   * [Medication List document (FHIR)](http://fhir.ch/ig/ch-emed/StructureDefinition-ch-emed-document-medicationlist.html)


## Setup

To transform the documents from CDA to FHIR and back and maybe add your own maps, you should prepare the following setup:

### Editor

* Download [Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
* Install a REST Client for Visual Studio Code:   
    Open VSC, press **Ctrl + Shift + X**, search for **rest-client**, then install it (humao.rest-client) 

### Docker

* Download and install [Docker](https://www.docker.com/)

```
docker pull eu.gcr.io/fhir-ch/matchbox:v0815
docker run -d --name matchbox -p 8080:8080 eu.gcr.io/fhir-ch/matchbox:v0815
docker logs matchbox
```

### GitHub Desktop (optional)

* Download [GitHub Desktop](https://desktop.github.com/)


## Development

Clone this project https://github.com/hl7ch/cda-fhir-maps
   * Option 1: GitHub Desktop
   * Option 2: VSC Terminal:   
    `git clone https://github.com/hl7ch/cda-fhir-maps.git`

Open it with Visual Studio Code (REST Client extension is needed).


## Transform documents between CDA and FHIR and back
* Open **cdatofhir.http** or **fhirtocda.http** from the main directory with Visual Studio Code. 
* Choose @host = http://localhost:8080/r4  
* Add the maps to matchbox (Step 1 to 3).
* Transform your document (Examples shown in Step 5).

## Transform eMedication documents between CDA and FHIR and back
* Open following files, depending on the requiered exchange format, from the main directory with Visual Studio Code:
   * Medication Card document: cdatofhir_card.http, fhirtocda_card.http
   * Medication Dispense document: cdatofhir_dispense.http, fhirtocda_dispense.http
   * Medication Prescription document: cdatofhir_prescription.http, fhirtocda_prescription.http
   * Medication List document: cdatofhir_list.http, -
* Choose @host = http://localhost:8080/r4  
* Transform your document of the choosen exchange format (Examples shown in Step 5).
