# EReferral MedicationAdministration - PH eReferral Implementation Guide v0.1.0

## Resource Profile: EReferral MedicationAdministration 

 
Profile for medications administered to patients in the Philippine eReferral context. Captures medications given as part of treatment (REF-39) and referenced via ServiceRequest.supportingInfo (REF-15) to provide clinical context for referrals. 

**Usages:**

* Examples for this Profile: [MedicationAdministration/ExampleERefMedicationAdministrationAntibiotic](MedicationAdministration-ExampleERefMedicationAdministrationAntibiotic.md) and [MedicationAdministration/ExampleERefMedicationAdministrationChronic](MedicationAdministration-ExampleERefMedicationAdministrationChronic.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/fhir.ph.ereferral|current/StructureDefinition/ereferral-medication-administration)

### Formal Views of Profile Content

 [Description Differentials, Snapshots, and other representations](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](../StructureDefinition-ereferral-medication-administration.csv), [Excel](../StructureDefinition-ereferral-medication-administration.xlsx), [Schematron](../StructureDefinition-ereferral-medication-administration.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "ereferral-medication-administration",
  "url" : "urn://example.com/ph-ereferral/fhir/StructureDefinition/ereferral-medication-administration",
  "version" : "0.1.0",
  "name" : "ERefMedicationAdministration",
  "title" : "EReferral MedicationAdministration",
  "status" : "draft",
  "date" : "2026-06-06T03:42:54+00:00",
  "publisher" : "SILab CoP IG Accelerator (eReferral)",
  "contact" : [{
    "name" : "SILab CoP IG Accelerator (eReferral)",
    "telecom" : [{
      "system" : "url",
      "value" : "https://github.com/UP-Manila-SILab"
    }]
  }],
  "description" : "Profile for medications administered to patients in the Philippine eReferral context. Captures medications given as part of treatment (REF-39) and referenced via ServiceRequest.supportingInfo (REF-15) to provide clinical context for referrals.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "PH",
      "display" : "Philippines"
    }]
  }],
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "workflow",
    "uri" : "http://hl7.org/fhir/workflow",
    "name" : "Workflow Pattern"
  },
  {
    "identity" : "rim",
    "uri" : "http://hl7.org/v3",
    "name" : "RIM Mapping"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  },
  {
    "identity" : "v2",
    "uri" : "http://hl7.org/v2",
    "name" : "HL7 v2 Mapping"
  },
  {
    "identity" : "w3c.prov",
    "uri" : "http://www.w3.org/ns/prov",
    "name" : "W3C PROV"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "MedicationAdministration",
  "baseDefinition" : "https://fhir.doh.gov.ph/phcore/StructureDefinition/ph-core-medicationadministration",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "MedicationAdministration",
      "path" : "MedicationAdministration"
    },
    {
      "id" : "MedicationAdministration.status",
      "path" : "MedicationAdministration.status",
      "short" : "Medication administration status",
      "definition" : "The status of the medication administration. Tracks whether the medication was completed, in-progress, or not administered.",
      "mustSupport" : true
    },
    {
      "id" : "MedicationAdministration.medication[x]",
      "path" : "MedicationAdministration.medication[x]",
      "short" : "Medication administered",
      "definition" : "The medication that was administered to the patient. Can be a reference to a Medication resource or a coded concept.",
      "mustSupport" : true
    },
    {
      "id" : "MedicationAdministration.subject",
      "path" : "MedicationAdministration.subject",
      "short" : "Patient receiving medication",
      "definition" : "The patient who received the medication. Constrained to PHCorePatient.",
      "mustSupport" : true
    },
    {
      "id" : "MedicationAdministration.effective[x]",
      "path" : "MedicationAdministration.effective[x]",
      "short" : "When medication was administered",
      "definition" : "The date/time or period when the medication administration occurred.",
      "mustSupport" : true
    }]
  }
}

```
