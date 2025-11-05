This set of exercises was to:

1. Create, update, and read a resource. We updated with a `PUT` method so we needed to include the entire resource again with the changed fields. 
2. Perform queries:
- **Query #1** – by ID assigned by the server 
- **Query #2** – by Patient Identifier value 
- **Query #3** – by Patient Family Name and the result must be ordered by ID, in descending order  
- **Query #4** – by Patient Gender, birthdate and Given Name (all in the same query) 
- **Query #5** – Is up to you. (You cannot repeat previous queries or combinations of previously used parameters but your resource has to be in the first page result)  

QUERIES

1. http://fhirserver.hl7fundamentals.org/fhir/Patient?_id=108636

2. http://fhirserver.hl7fundamentals.org/fhir/Patient?identifier=http://hospitalxyz.com/patients%7Carthas.menethil

3. http://fhirserver.hl7fundamentals.org/fhir/Patient?family=Menethil&_sort=-_id 

4. http://fhirserver.hl7fundamentals.org/fhir/Patient?gender=male&birthdate=1985-06-14&given=Arthas 

5. http://fhirserver.hl7fundamentals.org/fhir/Patient?address-city=Stormwind&_count=50&_sort=_id