# Retrieve All Patient Vital Signs

To retrieve all vital sign observations for Patient 108636 (Arthas Menethil) in a single query, use the following FHIR search query:

## Working Query (Verified)
This query successfully retrieves ALL observations for the patient:

```
GET /Observation?patient=108636&_count=100
```

**Query Parameters:**
- `patient=108636` - Filters observations for this specific patient (shorthand for `subject=Patient/108636`)
- `_count=100` - Limits results to 100 (adjust if needed)

**Full URL:**
```
http://fhirserver.hl7fundamentals.org/fhir/Observation?patient=108636&_count=100
```

**Note:** If you need sorting, try `_sort=-date` (descending, most recent first) or `_sort=date` (ascending). Some servers may not support sorting on Observation resources.

## Alternative Query Format
You can also use the full subject reference format:

```
GET /Observation?subject=Patient/108636&_sort=date&_count=100
```

## Filtered Query: Only Specific Vital Signs
If you want to retrieve only the 4 vital signs we're tracking:

```
GET /Observation?patient=108636&code=9279-1,8480-6,8462-4,8867-4&_count=100
```

**Query Parameters:**
- `patient=108636` - Filters observations for this specific patient
- `code=9279-1,8480-6,8462-4,8867-4` - Filters to only these LOINC codes:
  - `9279-1` - Respiratory rate
  - `8480-6` - Systolic blood pressure
  - `8462-4` - Diastolic blood pressure
  - `8867-4` - Heart rate
- `_count=100` - Limits results to 100

**Note:** Removed `_sort=date` as some FHIR servers don't support sorting on Observation resources. If sorting is needed, try `_sort=-date` (descending) or handle sorting in your application code.

## Usage

**Using cURL:**
```bash
curl -X GET "http://fhirserver.hl7fundamentals.org/fhir/Observation?patient=108636&code=9279-1,8480-6,8462-4,8867-4&_count=100" \
  -H "Accept: application/fhir+json"
```

**Using Postman or similar:**
- Method: GET
- URL: `http://fhirserver.hl7fundamentals.org/fhir/Observation?patient=108636&code=9279-1,8480-6,8462-4,8867-4&_count=100`
- Headers: `Accept: application/fhir+json`

## Response Format

The response will be a FHIR Bundle containing all matching Observation resources, each with:
- `effectiveDateTime` - When the measurement was taken
- `valueQuantity` - The measured value and unit
- `code` - The LOINC code identifying what was measured
- `subject` - Reference to Patient/108636

This data can be directly used by the UX team to create graphs showing:
- Vital signs over time
- Trends for each measurement type
- Comparison between different vital signs

