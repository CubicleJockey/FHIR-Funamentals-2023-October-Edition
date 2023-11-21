# Transactions 

>All Transactions go to the base url: http://fhirserver.hl7fundamentals.org/fhir
>* Method: POST
>* Header:
>   * Content-Type: application/fhir+json

#### Transaction 1
>Post Body
```JSON
{
	"resourceType": "Bundle",
	"type": "transaction",
	"entry": [
		{
			"fullUrl": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E",
			"resource": {
				"resourceType": "Organization",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UWEARME - A DIVISION OF HEALTH GIZMOS CORP </div>"
				},
				"identifier": [
					{
						"system": "http://fhirfun2021.org/ids",
						"value": "UWEARME"
					}
				],
				"name": "UWEARME",
				"address": [
					{
						"line": [
							"2000 WEARABLE DRIVE"
						],
						"city": "ANN ARBOR",
						"state": "MI",
						"country": "US"
					}
				]
			},
			"request": {
				"method": "PUT",
				"url": "Organization?identifier=http://fhirfun2021.org/ids|UWEARME"
			}
		},
		{
			"fullUrl": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9",
			"resource": {
				"resourceType": "Patient",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> Andre Davis Id # andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://mypatientidentifier.com/ids",
						"value": "andre.davis"
					}
				],
				"name": [
					{
						"family": "Davis",
						"given": [
							"Andre"
						]
					}
				],
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
				"managingOrganization": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Patient?identifier=http://mypatientidentifier.com/ids|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24",
			"resource": {
				"resourceType": "Device",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Device andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/dev",
						"value": "andre.davis"
					}
				],
				"expirationDate": "2020-10-10",
				"lotNumber": "22222",
				"modelNumber": "u888800-1",
				"type": {
					"coding": [
						{
							"system": "http://snomed.info/sct",
							"code": "33894003",
							"display": "Experimental Device"
						}
					]
				},
				"patient": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"owner": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Device?identifier=http://uwearme.com/dev|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:9b3055be-bb9f-4fce-b5da-599286eb2841",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Respiratory Rate:16/min on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-9279-1"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "9279-1",
							"display": "Respiratory Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 16,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:bf551c01-8aa5-4ace-99d4-ae03a5bc89e7",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Systolic Blood Pressure: 154mmHg on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8480-6"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8480-6",
							"display": "Systolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
                    "value": 154,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:54e8f280-8f5c-4d63-a174-29a091ecb06a",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Diastolic Blood Pressure:63mmHg on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8462-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8462-4",
							"display": "Diastolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 63,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:55c0f3ad-4a2e-4516-8e2c-3db15ed62941",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat #andre.davis Heart Rate:79/min on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8867-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8867-4",
							"display": "Heart Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 79,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		}
	]
}
```

#### Transaction 2
```JSON
{
	"resourceType": "Bundle",
	"type": "transaction",
	"entry": [
		{
			"fullUrl": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E",
			"resource": {
				"resourceType": "Organization",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UWEARME - A DIVISION OF HEALTH GIZMOS CORP </div>"
				},
				"identifier": [
					{
						"system": "http://fhirfun2021.org/ids",
						"value": "UWEARME"
					}
				],
				"name": "UWEARME",
				"address": [
					{
						"line": [
							"2000 WEARABLE DRIVE"
						],
						"city": "ANN ARBOR",
						"state": "MI",
						"country": "US"
					}
				]
			},
			"request": {
				"method": "PUT",
				"url": "Organization?identifier=http://fhirfun2021.org/ids|UWEARME"
			}
		},
		{
			"fullUrl": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9",
			"resource": {
				"resourceType": "Patient",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> Andre Davis Id # andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://mypatientidentifier.com/ids",
						"value": "andre.davis"
					}
				],
				"name": [
					{
						"family": "Davis",
						"given": [
							"Andre"
						]
					}
				],
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
				"managingOrganization": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Patient?identifier=http://mypatientidentifier.com/ids|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24",
			"resource": {
				"resourceType": "Device",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Device andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/dev",
						"value": "andre.davis"
					}
				],
				"expirationDate": "2020-10-10",
				"lotNumber": "22222",
				"modelNumber": "u888800-1",
				"type": {
					"coding": [
						{
							"system": "http://snomed.info/sct",
							"code": "33894003",
							"display": "Experimental Device"
						}
					]
				},
				"patient": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"owner": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Device?identifier=http://uwearme.com/dev|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:9b3055be-bb9f-4fce-b5da-599286eb2841",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Respiratory Rate:14/min on 2023-11-09T10:45:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T10:45:00Z-9279-1"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "9279-1",
							"display": "Respiratory Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T10:45:00Z",
				"valueQuantity": {
					"value": 14,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:bf551c01-8aa5-4ace-99d4-ae03a5bc89e7",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Systolic Blood Pressure: 137mmHg on 2023-11-09T10:45:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T10:45:00Z-8480-6"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8480-6",
							"display": "Systolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T10:45:00Z",
				"valueQuantity": {
                    "value": 137,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:54e8f280-8f5c-4d63-a174-29a091ecb06a",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Diastolic Blood Pressure:119mmHg on 2023-11-09T10:45:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T10:45:00Z-8462-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8462-4",
							"display": "Diastolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T10:45:00Z",
				"valueQuantity": {
					"value": 119,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:55c0f3ad-4a2e-4516-8e2c-3db15ed62941",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat #andre.davis Heart Rate:69/min on 2023-11-09T10:45:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T10:45:00Z-8867-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8867-4",
							"display": "Heart Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T10:45:00Z",
				"valueQuantity": {
					"value": 69,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		}
	]
}
```

#### Transaction 3
```JSON
{
	"resourceType": "Bundle",
	"type": "transaction",
	"entry": [
		{
			"fullUrl": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E",
			"resource": {
				"resourceType": "Organization",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UWEARME - A DIVISION OF HEALTH GIZMOS CORP </div>"
				},
				"identifier": [
					{
						"system": "http://fhirfun2021.org/ids",
						"value": "UWEARME"
					}
				],
				"name": "UWEARME",
				"address": [
					{
						"line": [
							"2000 WEARABLE DRIVE"
						],
						"city": "ANN ARBOR",
						"state": "MI",
						"country": "US"
					}
				]
			},
			"request": {
				"method": "PUT",
				"url": "Organization?identifier=http://fhirfun2021.org/ids|UWEARME"
			}
		},
		{
			"fullUrl": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9",
			"resource": {
				"resourceType": "Patient",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> Andre Davis Id # andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://mypatientidentifier.com/ids",
						"value": "andre.davis"
					}
				],
				"name": [
					{
						"family": "Davis",
						"given": [
							"Andre"
						]
					}
				],
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
				"managingOrganization": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Patient?identifier=http://mypatientidentifier.com/ids|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24",
			"resource": {
				"resourceType": "Device",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Device andre.davis </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/dev",
						"value": "andre.davis"
					}
				],
				"expirationDate": "2020-10-10",
				"lotNumber": "22222",
				"modelNumber": "u888800-1",
				"type": {
					"coding": [
						{
							"system": "http://snomed.info/sct",
							"code": "33894003",
							"display": "Experimental Device"
						}
					]
				},
				"patient": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"owner": {
					"reference": "urn:uuid:17C7D86E-664F-4FE2-91D7-AF9A8E47311E"
				}
			},
			"request": {
				"method": "PUT",
				"url": "Device?identifier=http://uwearme.com/dev|andre.davis"
			}
		},
		{
			"fullUrl": "urn:uuid:9b3055be-bb9f-4fce-b5da-599286eb2841",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Respiratory Rate:16/min on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-9279-1"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "9279-1",
							"display": "Respiratory Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 16,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:bf551c01-8aa5-4ace-99d4-ae03a5bc89e7",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Systolic Blood Pressure: 154mmHg on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8480-6"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8480-6",
							"display": "Systolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
                    "value": 154,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:54e8f280-8f5c-4d63-a174-29a091ecb06a",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat # andre.davis Diastolic Blood Pressure:63mmHg on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8462-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8462-4",
							"display": "Diastolic Blood Pressure"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 63,
					"unit": "mmHg"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		},
		{
			"fullUrl": "urn:uuid:55c0f3ad-4a2e-4516-8e2c-3db15ed62941",
			"resource": {
				"resourceType": "Observation",
				"text": {
					"status": "generated",
					"div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"> UW Measure for Pat #andre.davis Heart Rate:79/min on 2023-11-09T11:00:00Z </div>"
				},
				"identifier": [
					{
						"system": "http://uwearme.com/measures",
						"value": "andre.davis-2023-11-09T11:00:00Z-8867-4"
					}
				],
				"status": "final",
				"code": {
					"coding": [
						{
							"system": "http://loinc.org",
							"code": "8867-4",
							"display": "Heart Rate"
						}
					]
				},
				"subject": {
					"reference": "urn:uuid:0fc374a1-a226-4552-9683-55dd510e67c9"
				},
				"effectiveDateTime": "2023-11-09T11:00:00Z",
				"valueQuantity": {
					"value": 79,
					"unit": "/min"
				},
				"device": {
					"reference": "urn:uuid:b405c692-54ea-4d0d-afb1-8f91880a3f24"
				}
			},
			"request": {
				"method": "POST",
				"url": "Observation"
			}
		}
	]
}
```

# Observation Query
> Method: GET
> Header:
> * Content-Type: application/json
>
> URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?identifier=http://mypatientidentifier.com/ids|andre.davis