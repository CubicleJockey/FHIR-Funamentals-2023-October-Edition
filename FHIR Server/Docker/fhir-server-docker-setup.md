# FHIR R4 Docker Server Setup

### Required Installations

 * [Docker](https://docs.docker.com/get-docker/)

### Setup Instructions

  1. Turn on **Docker Desktop**
  2. Open [*Windows PowerShell*](https://learn.microsoft.com/en-us/powershell/) or [*Commandline*](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
  3. Execute the following commands in order:
     * Create a Docker Virutal Network:
       * `docker network create fhir_network` **NOTE:** Create once ONLY
     * Run and/or download image if needed:
       * SQLServer Container:
         * `docker run --net fhir_network --name fhir_sql -e SA_PASSWORD=fhir_admin_123 -e ACCEPT_EULA="Y" -d mcr.microsoft.com/mssql/server`
       * Microsoft FHIR R4 Server Container:
         * ```docker run --net fhir_network --name r4_fhir_server -e FhirServer__Security__Enabled="false" -e SqlServer__ConnectionString="Server=tcp:fhir_sql,1433;Initial Catalog=FHIR;Persist Security Info=False;User ID=sa;Password=fhir_admin_123;MultipleActiveResultSets=False;Connection Timeout=30;TrustServerCertificate=True" -e SqlServer__AllowDatabaseCreation="true" -e SqlServer__Initialize="true" -e SqlServer__SchemaOptions__AutomaticUpdatesEnabled="true" -e DataStore="SqlServer" -p 8080:8080 -d mcr.microsoft.com/healthcareapis/r4-fhir-server azure-fhir-api```