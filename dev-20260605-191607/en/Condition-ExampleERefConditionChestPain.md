# Example Condition - Chest Pain - PH eReferral Implementation Guide v0.1.0

## Example Condition: Example Condition - Chest Pain

Profile: [PH Core Condition](https://build.fhir.org/ig/jldalisay95/ph-core-jld/StructureDefinition-ph-core-condition.html)

**clinicalStatus**: Active

**verificationStatus**: Provisional

**category**: Diagnosis

**severity**: Severe

**code**: Chest pain on exertion

**subject**: [Juan Miguel Dela Cruz Male, DoB: 1965-07-20 ( urn:oid:2.16.840.1.113883.2.9.4.3.2#PH-123456789)](Patient-ExampleERefPatient.md)

**onset**: 2025-03-12



## Resource Content

```json
{
  "resourceType" : "Condition",
  "id" : "ExampleERefConditionChestPain",
  "meta" : {
    "profile" : ["https://fhir.doh.gov.ph/phcore/StructureDefinition/ph-core-condition"]
  },
  "clinicalStatus" : {
    "coding" : [{
      "system" : "http://terminology.hl7.org/CodeSystem/condition-clinical",
      "code" : "active"
    }]
  },
  "verificationStatus" : {
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "provisional",
      "display" : "Provisional"
    }]
  },
  "category" : [{
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "439401001",
      "display" : "Diagnosis"
    }]
  }],
  "severity" : {
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "24484000",
      "display" : "Severe"
    }]
  },
  "code" : {
    "coding" : [{
      "system" : "http://snomed.info/sct",
      "code" : "29857009",
      "display" : "Chest pain"
    }],
    "text" : "Chest pain on exertion"
  },
  "subject" : {
    "reference" : "Patient/ExampleERefPatient"
  },
  "onsetDateTime" : "2025-03-12"
}

```
