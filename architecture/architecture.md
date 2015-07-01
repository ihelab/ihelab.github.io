Overall schematic
-----------

A major technical goal of the SLL Medical Device Integration Lab has been to build a proof-of-concept infrastructure for vendor neutral hospital-wide management of Patient Care Device (PCD) data. Capabilities of this infrastructure include:

 * Continuous collection and validation of PCD-data from Medical Device Systems. 
 * Persistent storage of collected data using a canonical data-structure. 
 * Exposure/distribution of data to other clinical IT-systems such as a PDMS

The resulting infrastructure features a highly modular design, consisting of self-contained software components which are interconnected using well-defined communication interfaces. Any component can be transparently replaced with a commercial alternative (as these become available on the market). For example, the Medical Device Simulator can be replaced with a IHE PCD compliant patient monitoring gateway. 

The diagram below summarizes the most important components of our proof-of-concept infrastructure, along with the overall flow of Device Observation Data (as indicated by arrows). The *C2* and *C3* components (including storage) are sometimes collectively referred to as a *T5-system*. 

![Picture description](../images/architecture.png)

Description of integrations
-----------

### Integration #1: Asynchronous PCD data

The Medical Device Integration Lab supports Medical Device integration according to the [IHE PCD Technical Framework](http://www.ihe.net/Technical_Frameworks/#pcd). Additionally, the [IHE PCD WCM trial supplement](http://www.ihe.net/Technical_Framework/upload/IHE_PCD_Suppl_WCM.pdf) is supported. Consequently, all Medical devices are expected to submit Device Observation Data in accordance with the [IHE-PCD-01 transaction](http://www.ihe.net/uploadedFiles/Documents/PCD/IHE_PCD_TF_Vol2.pdf). If a specific Medical Device does not support the IHE PCD framework, a 3rd-party adapter solution will be required. 

| Item                 | Value                                                     |
| -------------------- | -------------                                             |
| Data transfer    	   | MLLP-over-TCP                                             |
| Transaction format   | HL7v2 unsolicited according to the IHE-transaction PCD-01 |
| Semantics            | IEEE 11073                                                |


### Integration #2: Synchronous PCD data

The Medical Device Integration Lab supports clinical application integration according to the [HL7 FHIR DSTU 2 integration framework](http://www.hl7.org/FHIR/2015Jan/index.html). Currently, a REST-API is provided for exchange and manipulation of FHIR-resources. The original IEEE 11073 Device Observation Data semantics are re-used whenever possible. 


| Item                 | Value                                                     |
| -------------------- | -------------                                             |
| Data transfer    	   | TCP                                      			       |
| Transaction format   | HL7 FHIR DSTU 2 (REST)									   |
| Semantics            | IEEE 11073                                                |


Description of components
-----------

### C1: Medical Device Simulator
In order to simplify testing of other components within the lab, a Medical Device Simulator has been implemented. The application simulates a Patient Monitoring Gateway implementing the IHE DEC DOR actor, including the WCM supplement. 

 > Related Source Code Repository: [DOR Driver](http://www.example.com).

### C2: HL7v2 Endpoint
This component continuously collects, validates and stores Device Observation Data from all Medical Device Systems within the lab. It implements the IHE DEC DOC actor, including the WCM supplement, in order to achieve this. The component implemented on top of the Apache Camel integration platform. 

 >  Related Source Code Repository: [HL7v2 Endpoint](http://www.example.com).

### C3: HL7 FHIR Endpoint
This component exposes [HL7 FHIR DSTU 2 resources](http://www.hl7.org/FHIR/2015Jan/index.html) to clinical applications using a REST-API. Only FHIR-resources relevant to the practical scope of the lab have been implemented (such as Observation, Patient Demographics, Encounter Management etc.). 

The API has been implemented as two separate API-platforms. The first platform (FHIR RAW Backend) exposes non-modified Device Observation Data. The second platform (FHIR X-reference Backend) exposes Device Observation Data which has been enriched with patient-ID/device-ID association. This backend is also used for managing these associations. 

 >  Related Source Code Repository: [FHIR Raw Backend](http://www.example.com).
 
 >  Related Source Code Repository: [FHIR X-Reference Backend](http://www.example.com).

### C4: Clinical Applications
Even though the implementation/evaluation of clinical applications are out-of-scope of the Medical Device Integration lab, a small set of proof-of-concept applications have been implemented. The purpose of these applications is to facilitate administration, troubleshooting and demonstration of the other components within the lab. Additionally, they serve as best-practice examples of FHIR-enabled browser applications. The following functionality is currently supported:

 * Admist/Discharge patients
 * Manage patient/Device association
 * Trouble-shooting of other components within the lab
 * Live-data

>  Related Source Code Repository: [FHIR Webapp](http://www.example.com).
