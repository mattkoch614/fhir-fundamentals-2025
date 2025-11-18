# Week 4: FHIR Resource Validation

## Assignment
Validate a flawed Patient resource against the FHIR server's `$validate` operation and fix all validation errors.

## Fixes Applied
1. **Added `gender` field** - Required by BerzerkistanPatient profile
2. **Fixed extension code** - Changed from invalid "X" to valid "M" (Mandated)
3. **Fixed identifier system** - Changed to required "http://www.berzerkistan.gov/nhib"
4. **Fixed phone number** - Changed from "+3411..." to "+5411..." (profile constraint)
5. **Added text narrative** - Added generated narrative to satisfy dom-6 constraint

The fixed resource (`fixed-patient-json.json`) now passes validation with no errors or warnings.

