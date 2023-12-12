#CRUD

#### Create Patient
```text
Method: POST
Header:
    * Content-Type:** application/fhir+json
URL: http://fhirserver.hl7fundamentals.org/fhir/Patient
Body:
```

```JSON
{
  "resourceType": "Patient",
  "name": [
    {
      "use": "official",
      "family": "Davis",
      "given": [
        "Andre"
      ],      
      "text": "Andre Davis"
    }
  ],
  "telecom": [
    {
      "system": "phone",
      "use": "home",
      "value": "(03) 5555 6789"
    }
  ],
  "address": [
    {
      "line": [
        "3300 Washtenaw"
      ],
      "city": "Ann Harbor",
      "state": "MI",
      "postalCode": "48104",
      "country": "US",
      "district": "Washtenaw"
    }
  ],
  "gender": "male",
  "birthDate": "1973-11-02",
  "deceasedBoolean": false,
  "language": "english",
  "active": true,
  "communication": [
    {
      "preferred": true,
      "language": {
        "text": "english"
      }
    }
  ],
  "identifier": [
    {
      "system": "https://clinfhir.com/fhir/NamingSystem/identifier",
      "value": "andre.davis"
    }
  ]
}
```

#### Get Patient
```text
Method: GET
Header:
    * Content-Type: application/fhir+json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient/3993/
```


#### Update Patient
```text
Method: PUT
Header:
   * Content-Type:** application/fhir+json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient/
Body:
```

```JSON
{
    "resourceType": "Patient",
    "id": "3993",
    "meta": {
        "versionId": "1",
        "lastUpdated": "2023-11-03T22:39:13.056+00:00",
        "source": "#5Wz2mudnezwygT3f"
    },
    "language": "english",
    "text": {
        "status": "generated",
        "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"><div class=\"hapiHeaderText\">Andre <b>DAVIS </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>andre.davis</td></tr><tr><td>Address</td><td><span>3300 Washtenaw </span><br/><span>Ann Harbor </span><span>MI </span><span>US </span></td></tr><tr><td>Date of birth</td><td><span>02 November 1973</span></td></tr></tbody></table></div>"
    },
    "identifier": [
        {
            "system": "https://clinfhir.com/fhir/NamingSystem/identifier",
            "value": "andre.davis"
        }
    ],
    "active": true,
    "name": [
        {
            "use": "official",
            "text": "Andre Davis",
            "family": "Davis",
            "given": [
                "Andre"
            ]
        }
    ],
    "telecom": [
        {
            "system": "phone",
            "value": "(03) 5555 6789",
            "use": "home"
        }
    ],
    "gender": "male",
    "birthDate": "1978-11-02",
    "deceasedBoolean": false,
    "address": [
        {
            "line": [
                "3300 Washtenaw"
            ],
            "city": "Ann Harbor",
            "district": "Washtenaw",
            "state": "MI",
            "postalCode": "48104",
            "country": "US"
        }
    ],
    "communication": [
        {
            "language": {
                "text": "english"
            },
            "preferred": true
        }
    ]
}
```

#### Delete Patient

```text
Method:** DELETE
Header:**
   * Content-Type:** application/fhir+json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient/3993
```



#### Get Patient History By Version

```text
Method:** GET
Header:**
    * Content-Type:** application/json
URL: http://fhirserver.hl7fundamentals.org/fhir/Patient/3993/_history/2
```