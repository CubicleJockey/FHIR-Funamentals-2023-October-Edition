# Profile Validation

>**Method:** Post
>**Header:**
>* **Content-Type** application/fhir+json
>**URL:** http://fhirserver.hl7fundamentals.org/fhir/Patient/$validate
>**Body**:
```JSON
{
    "resourceType": "Patient",
    "id": "PatientAlbertGruollian",
    "meta": {
        "profile": [
            "http://minhealth.gov.bk/core/StructureDefinition/BerzerkistanPatient"
        ]
    },
    "extension": [
        {
            "url": "http://minhealth.gov.bk/core/StructureDefinition/PPHTaxSituation",
            "valueCode": "X"
        }
    ],
    "identifier": [
        {
            "use": "official",
            "system": "http://www.berzerkistan.gov/bni",
            "value": "9000031"
        },
        {
            "use": "usual",
            "system": "http://www.mypatients.gov/number",
            "value": "23327758999"
        }
    ],
    "name": [
        {
            "family": "Gruollian",
            "given": [
                "Albert"
            ]
        }
    ],
    "gender": "male",
    "telecom": [
        {
            "system": "phone",
            "value": "+541155555555"
        }
    ],
    "birthDate": "1922-06-14"
}
```