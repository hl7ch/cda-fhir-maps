### Introduction

This implementation guide provides maps to transform documents from CDA to FHIR and back. The maps are based on each other, first the transformation of the data types is defined. Then based on this the mapping between the documents (CDA/FHIR), which becomes more and more specific (Swiss EPR Context, eMedication).

To execute the transformation of the documents locally, see the description [here](https://github.com/hl7ch/cda-fhir-maps#development).

### Maps

The following maps are present as [FHIR Structure Maps](https://www.hl7.org/fhir/structuremap.html):

* Mapping of **data types**
   * [CDA to FHIR types](StructureMap-CdaToFHIRTypes.html)
   * [FHIR to CDA types](StructureMap-FhirToCdaTypes.html)

* Mapping of **documents**
   * [CDA to Bundle](StructureMap-CdaToBundle.html)
   * [Bundle to CDA](StructureMap-BundleToCda.html)

* Mapping of documents in the context of the **Swiss EPR**
   * [CDA-CH to Bundle](StructureMap-CdaChToBundle.html)
   * [Bundle to CDA-CH](StructureMap-BundleToCdaCh.html)

* Mapping of documents for the **exchange of medication information** in the context of the Swiss EPR

   * Medication Card document
      * [CDA-CH-EMED Medication Card document to Bundle](StructureMap-CdaChEmedMedicationCardDocumentToBundle.html)
      * [Bundle to CDA-CH-EMED Medication Card document](StructureMap-BundleToCdaChEmedMedicationCardDocument.html)

   * Medication Prescription document
      * [CDA-CH-EMED Medication Prescription document to Bundle](StructureMap-CdaChEmedMedicationPrescriptionDocumentToBundle.html)
      * [Bundle to CDA-CH-EMED Medication Prescription document](StructureMap-BundleToCdaChEmedMedicationPrescriptionDocument.html)

   * Medication Dispense document
      * [CDA-CH-EMED Medication Dispense document to Bundle](StructureMap-CdaChEmedMedicationDispenseDocumentToBundle.html)
      * [Bundle to CDA-CH-EMED Medication Dispense document](StructureMap-BundleToCdaChEmedMedicationDispenseDocument.html)


### Note
Work in Progress, coverage has been based on the eMedication case study (FHIR: [CH EMED](http://build.fhir.org/ig/hl7ch/ch-emed/branches/master/index.html), CDA: [CDA-CH-EMED](https://art-decor.org/art-decor/decor-project--cdachemed-)), no final mapping of data types, templates, documents yet.