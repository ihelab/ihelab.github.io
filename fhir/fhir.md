# SLL Medical Device Integration Lab Implementation Guide
This implementation guide describes a set of resource profiles designed to support specific use cases which are part of the proof-of concept implementation of a clinical decision support system at the Medical Device Integration Lab of the Stockholm County Council (Stockholms Läns Landsting). 

<!---
## Definitions, interpretations and requiremets common to all MDI-Actors

## Conformance requirements for each MDI-Actor
-->

## MDI profiles and extensions
A machine readable (XML) FHIR ImplementationGuide-resource along with StructureDefinition resources for all profiles and extensions is available as an archive below. 

> [SLL MDI Lab FHIR Implementation Guide](sll-mdilab-implementation-guide.zip)

### Profiles

|Profile|FHIR Resource|Description|
|---|---|---|
|MDI-Appointment|Appointment|Appointment for patient visit.
|MDI-AutomaticVitalSign|Observation|Automatically measured (by a device) vital signs.
|MDI-Condition|Condition|A record of a confirmed diagnosis of a specific ICD-10 coded medical condition.  
|MDI-Encounter|Encounter|An encounter with a specific primary performer.
|MDI-EpisodeOfCare|EpisodeOfCare|An episode connecting a series of Encounter resources.
|MDI-ManualVitalSign|Observation|Manually measured (by a practitioner) vital signs.
|MDI-MedicationOrder|MedicationOrder|Vital sign based medication orders.
|MDI-MetricOrder|Order|An order for a specific device metric to be monitored.
|MDI-OrderableDeviceMetric|DeviceMetric|A device metric of which monitoring can be ordered.
|MDI-Organization|Organization|Represent a department of the hospital.
|MDI-Patient|Patient|Personal particulars of a patient.|
|MDI-PatientDeviceAssociation|DeviceUseStatement|Patient-device associations.
|MDI-Practitioner|Practitioner|A medical practitioner.
|MDI-SBARReferralRequest|ReferralRequest|A referral request to be represented as an SBAR-transfer between practitioners.
|MDI-SelfReportedVitalSign|Observation|Self-reported (by the patient) vital signs.

### Extensions

|Extension|Usage|Description|
|---|---|---|
|MDI-Issuer-Extension|MDI-PatientDeviceAssociation|Reference to the Practitioner who is responsible for the association.|
|MDI-MedicationList-Extension|MDI-Organization|A list of medications in use by the department
|MDI-ClinicalCategory-Extension|MDI-OrderableDeviceMetric|The clinical category which a parameter belongs to (e. g. respiratory or cardiovascular).
|MDI-AlarmLimits-Extension|MDI-Order|Alarm limits for an ordered vital sign monitoring.
