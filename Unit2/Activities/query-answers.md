# Search (Query)

#### Query Patient By Id
```text
Method: GET
Header:
* Content-Type: application/json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?_id=4021
```



#### Query Patient By Identifier
```text
Method: GET
Header:
* Content-Type: application/json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?identifier=https://clinfhir.com/fhir/NamingSystem/identifier|andre.davis
```


#### Query Patient By Family Name Desc Order
```text
Method: GET
Header:
* Content-Type: application/json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?family=Davis&_sort=-_id
```


#### Query Patient By Gender, Birthday, and Given Name
```text
Method: GET
Header:
* Content-Type: application/json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?given=andre&gender=male&birthdate=1978-11-02
```


#### Query Patient By City (Contains)
```text
Method: GET
Header:
* Content-Type: application/json

URL: http://fhirserver.hl7fundamentals.org/fhir/Patient?address-city:contains=Awesome
```