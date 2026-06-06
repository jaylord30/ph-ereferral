# ERefPatient - PH eReferral Implementation Guide v0.1.0

## Resource Profile: ERefPatient ( Experimental ) 

 
Patient profile for the Philippine eReferral system. Extends PHCorePatient with additional elements specific to referral workflows, including PWD (Person with Disability) registration information. This profile supports the patient demographic requirements defined in the eReferral TDG (Technical Development Group) mapping, elements REF-21 through REF-30. 

**Usages:**

* Refer to this Profile: [ERefEncounter](StructureDefinition-ereferral-encounter.md), [ERefImmunization](StructureDefinition-ereferral-immunization.md) and [EReferral Observation](StructureDefinition-ereferral-observation.md)
* Examples for this Profile: [Patient/ERefPatientExample](Patient-ERefPatientExample.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/fhir.ph.ereferral|current/StructureDefinition/ereferral-patient)

### Formal Views of Profile Content

 [Description Differentials, Snapshots, and other representations](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](../StructureDefinition-ereferral-patient.csv), [Excel](../StructureDefinition-ereferral-patient.xlsx), [Schematron](../StructureDefinition-ereferral-patient.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "ereferral-patient",
  "url" : "urn://example.com/ph-ereferral/fhir/StructureDefinition/ereferral-patient",
  "version" : "0.1.0",
  "name" : "ERefPatient",
  "title" : "ERefPatient",
  "status" : "draft",
  "experimental" : true,
  "date" : "2026-06-06T03:42:54+00:00",
  "publisher" : "SILab CoP IG Accelerator (eReferral)",
  "contact" : [{
    "name" : "SILab CoP IG Accelerator (eReferral)",
    "telecom" : [{
      "system" : "url",
      "value" : "https://github.com/UP-Manila-SILab"
    }]
  }],
  "description" : "Patient profile for the Philippine eReferral system. Extends PHCorePatient with additional elements specific to referral workflows, including PWD (Person with Disability) registration information. This profile supports the patient demographic requirements defined in the eReferral TDG (Technical Development Group) mapping, elements REF-21 through REF-30.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "PH",
      "display" : "Philippines"
    }]
  }],
  "purpose" : "To standardize patient demographic information for Philippine healthcare referrals, ensuring interoperability between referring and receiving facilities.",
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "rim",
    "uri" : "http://hl7.org/v3",
    "name" : "RIM Mapping"
  },
  {
    "identity" : "cda",
    "uri" : "http://hl7.org/v3/cda",
    "name" : "CDA (R2)"
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
    "identity" : "loinc",
    "uri" : "http://loinc.org",
    "name" : "LOINC code for the element"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Patient",
  "baseDefinition" : "https://fhir.doh.gov.ph/phcore/StructureDefinition/ph-core-patient",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Patient",
      "path" : "Patient"
    },
    {
      "id" : "Patient.extension:disabilityRegistration",
      "path" : "Patient.extension",
      "sliceName" : "disabilityRegistration",
      "short" : "PWD Registration Information",
      "definition" : "Person With Disability (PWD) registration information including PWD ID number, type of disability, and ID expiration date. (REF-30)",
      "min" : 0,
      "max" : "1",
      "type" : [{
        "code" : "Extension",
        "profile" : ["urn://example.com/ph-ereferral/fhir/StructureDefinition/ereferral-pwd-disability"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Patient.name",
      "path" : "Patient.name",
      "min" : 1
    },
    {
      "id" : "Patient.telecom",
      "path" : "Patient.telecom",
      "short" : "Contact Number",
      "definition" : "Patient's contact information including phone numbers and email addresses. (REF-28)"
    },
    {
      "id" : "Patient.telecom.system",
      "path" : "Patient.telecom.system",
      "binding" : {
        "strength" : "required",
        "valueSet" : "http://hl7.org/fhir/ValueSet/contact-point-system"
      }
    },
    {
      "id" : "Patient.telecom.use",
      "path" : "Patient.telecom.use",
      "binding" : {
        "strength" : "required",
        "valueSet" : "http://hl7.org/fhir/ValueSet/contact-point-use"
      }
    },
    {
      "id" : "Patient.gender",
      "path" : "Patient.gender",
      "min" : 1
    },
    {
      "id" : "Patient.birthDate",
      "path" : "Patient.birthDate",
      "min" : 1
    },
    {
      "id" : "Patient.address",
      "path" : "Patient.address",
      "short" : "Patient Address",
      "definition" : "Current residence address of the patient. Use PHCoreAddress extensions for PSGC-coded barangay, city/municipality, and province. (REF-27)"
    },
    {
      "id" : "Patient.contact",
      "path" : "Patient.contact",
      "short" : "Accompanied By / Next of Kin",
      "definition" : "Contact details for the patient's companion, guardian, or next of kin who may be contacted regarding the referral. (REF-29)"
    },
    {
      "id" : "Patient.contact.relationship",
      "path" : "Patient.contact.relationship",
      "min" : 1
    },
    {
      "id" : "Patient.contact.name",
      "path" : "Patient.contact.name",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Patient.contact.telecom",
      "path" : "Patient.contact.telecom",
      "mustSupport" : true
    }]
  }
}

```
