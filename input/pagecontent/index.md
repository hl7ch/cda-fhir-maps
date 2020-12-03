### Introduction

This implementation guide provides maps to transform documents from CDA to FHIR and back using the [FHIR Mapping Language (FML)](https://www.hl7.org/fhir/mapping-language.html).   
The maps are based on each other, first the transformation of the data types ([FHIR Logical model CDA](http://build.fhir.org/ig/HL7/cda-core-2.0/branches/master/index.html)) is defined. Then based on this the mapping between the documents (CDA/FHIR), which becomes more and more specific (Swiss EPR Context, eMedication).

To execute the transformation of the documents locally, see the description [here](https://github.com/hl7ch/cda-fhir-maps#development).

### Maps

The maps listed in the table below are available as [FHIR Structure Maps](https://www.hl7.org/fhir/structuremap.html).

{:class="table table-bordered"}
| Mapping of ... | CDA to FHIR | FHIR to CDA |
|----------------|-------------|-------------|
| **Data types** | [CDA to FHIR types](StructureMap-CdaToFhirTypes.html) | [FHIR to CDA types](StructureMap-FhirToCdaTypes.html) |
| **Documents** | [CDA to Bundle](StructureMap-CdaToBundle.html) | [Bundle to CDA](StructureMap-BundleToCda.html) |
| Documents in the context of the **Swiss EPR** | [CDA-CH to Bundle](StructureMap-CdaChToBundle.html) | [Bundle to CDA-CH](StructureMap-BundleToCdaCh.html) |
| Documents for the **exchange of medication information** in the context of the Swiss EPR | [CDA-CH-EMED to Bundle](StructureMap-CdaChEmedToBundle.html) | [Bundle to CDA-CH-EMED](StructureMap-BundleToCdaChEmed.html) |
| Medication Treatment Plan document | [CDA-CH-EMED Medication Treatment Plan document to Bundle](StructureMap-CdaChEmedMedicationTreatmentPlanDocumentToBundle.html) | [Bundle to CDA-CH-EMED Medication Treatment Plan document](StructureMap-BundleToCdaChEmedMedicationTreatmentPlanDocument.html) |
| Medication Prescription document | [CDA-CH-EMED Medication Prescription document to Bundle](StructureMap-CdaChEmedMedicationPrescriptionDocumentToBundle.html) | [Bundle to CDA-CH-EMED Medication Prescription document](StructureMap-BundleToCdaChEmedMedicationPrescriptionDocument.html) |
| Medication Dispense document | [CDA-CH-EMED Medication Dispense document to Bundle](StructureMap-CdaChEmedMedicationDispenseDocumentToBundle.html) | [Bundle to CDA-CH-EMED Medication Dispense document](StructureMap-BundleToCdaChEmedMedicationDispenseDocument.html) |
| Pharmaceutical Advice document | [CDA-CH-EMED Pharmaceutical Advice document to Bundle](StructureMap-CdaChEmedPharmaceuticalAdviceDocumentToBundle.html) | [Bundle to CDA-CH-EMED Pharmaceutical Advice document](StructureMap-BundleToCdaChEmedPharmaceuticalAdviceDocument.html) |
| Medication List document | [CDA-CH-EMED Medication List document to Bundle](StructureMap-CdaChEmedMedicationListDocumentToBundle.html) | - |
| Medication Card document | [CDA-CH-EMED Medication Card document to Bundle](StructureMap-CdaChEmedMedicationCardDocumentToBundle.html) | [Bundle to CDA-CH-EMED Medication Card document](StructureMap-BundleToCdaChEmedMedicationCardDocument.html) |

### Note
Work in progress, coverage has been based on the eMedication case study (FHIR: [CH EMED](http://build.fhir.org/ig/hl7ch/ch-emed/branches/master/index.html), CDA: [CDA-CH-EMED](https://art-decor.org/art-decor/decor-project--cdachemed-)), no final mapping of data types, templates, documents yet.