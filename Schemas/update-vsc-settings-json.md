# Update Visual Studio Code `settings.json`


Steps:

 1. Press `ctrl+,` to bring up VSC Settings
 2. Search `Schema` in search bar
 3. Click on `Edit in settings.json`
 4. Find section of `settings.json` labeled:
    ```json
        "json.schemas": [
        /*reduced for clarity*/
        ],
    ```
5. Add the following JSON settings to the `json.schemas` array
   ```json
    {
        "fileMatch": ["/*.fhir.json"],
        "url": "./fhir.schema.json"
    } 
   ```
   Resulting in:
   ```json
    "json.schemas": [
       /*reduced for clarity*/,
        {
        "fileMatch": ["/*.fhir.json"],
        "url": "./fhir.schema.json"
        } 
    ],
   ```
6. Press `ctrl+s` to save `settings.json`

> This is the intellisense for the FHIR JSON Format and valid properties. Although, to NOTE the `fhir.schema.json` must be add to the same level in the directory as the files being worked on with this basic set-up.
