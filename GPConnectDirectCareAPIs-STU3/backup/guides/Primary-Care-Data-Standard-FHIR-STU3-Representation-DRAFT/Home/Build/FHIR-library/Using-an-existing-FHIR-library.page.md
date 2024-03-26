## {{page-title}}

GP Connect strongly advises suppliers to use an existing FHIR library as it will reduce development time and result in more robust implementations of the GP Connect API. Benefits of using an existing FHIR library for the implementation of both the consumer and provider side of a GP Connect API are:

- **Reduced complexity** - using a library can reduce the quantity of boilerplate code required to configure provider endpoints, structure a request and validate consumed resources. This will help keep the code base smaller, and make it easier to work on and maintain.
- **Quicker development** - a library gives developers the standard FHIR data types, FHIR resources and some validation of the FHIR resources, allowing developers to focus on data transformation and business rules.
- **Solution resilience** - using a tried and tested implementation of the FHIR resources and data types should result in the implementation being more resilient to receiving valid but unexpected elements within FHIR resources. Many libraries will also include some level of validation to aid in ensuring that only valid data enters the system.
