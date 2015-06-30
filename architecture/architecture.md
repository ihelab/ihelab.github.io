Overall schematic
-----------

The primary goal of the Patient Care Device (PCD) interopability lab has been to build a proof-of-concept intrastructure for vendor neutral management of PCD-data. The resulting infarstructure features a highly modular design, consisting of several software components which are interconnected using well-defined communication interfaces. Any component can be transparently replaced with commercial alternatives as they become availible on the market. 


 > Example: The DOR-driver can be replaced with a IHE PCD compliant patient monitoring gateway.  

The diagram below summarizes the most important compinents of our proof-of-concept infrastrucutre, along with the ovearall flow of Device Observation Data (as indicated by arrows). 

![Picture description](../images/architecture.png)

Description of integrations
-----------

### Integration #1: Asynchronous PCD data

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 

| Item                 | Value                                                     |
| -------------------- | -------------                                             |
| Data transfer    	   | MLLP-over-TCP                                             |
| Transaction format   | HL7v2 unsolicited according to the IHE-transaction PCD-01 |
| Semantics            | IEEE 11073                                                |


### Integration #2: Synchronous PCD data

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 


| Item                 | Value                                                     |
| -------------------- | -------------                                             |
| Data transfer    	   | TCP                                      			       |
| Transaction format   | HL7 FHIR DSTU 2 (REST/Messaging)						   |
| Semantics            | IEEE 11073                                                |


Description of components
-----------

### C1: DOR-driver
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 

[Project README](https://www.google.com)

### C2: T5-POC
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 

[Project README](https://www.google.com)

### C3: FHIR Backend & PID-proxy
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 


[Project README](https://www.google.com)

### C4: Applications
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 

[Project README](https://www.google.com)
