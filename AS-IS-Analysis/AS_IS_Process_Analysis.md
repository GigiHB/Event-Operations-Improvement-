 # AS-IS Process Analysis

**Project:** Event Operations Improvement

**Version:** v.01

**Author:** Giselle H. Brenes

**Date:** August 2026

## 1. Purpose

The purpose of this document is to analyze the current operational workflows performed by the Event Support team.
The analysis identifies how information flows across systems, highlights manual activities, and documents operational pain points before proposing any process improvements.
This document represents the current ("AS-IS") state of operations.

## 2. Process Inventory 
| ID   | Process                     | Status     |
| ---- | --------------------------- | ---------- |
| P-01 | Travel Manifest Preparation | Documented |
| P-02 | Room Assignment             | Documented |
| P-03 | Certificate Generation      | Pending    |
| P-04 | Name Badge Generation       | Pending    |

## 3. Systems Used
| System       | Function Within the Process                               |
| ------------ | --------------------------------------------------------- |
| Portal Site  | Stores travel and registration forms submitted by parents |
| Database     | Stores participant information                            |
| Dynamics 365 | Provides operational participant data                     |
| EventHub App | Supports programs management                              |
| SharePoint   | Stores operational files and shared tracking documents    |
| Excel        | Used for manual processing, sorting and reporting         |
| Outlook      | Sends notifications to parents and staff                  |
| Teams        | Internal communication                                    |
| Erudio       | Generates student certificates                            |
| Word         | Creates name badges using mail merge                      |

## 4. Process Assessment Framework
To ensure a consistent evaluation across all operational workflows, each process is assessed using a common set of Key Process Indicators (KPIs). These indicators provide a qualitative baseline of the current state ("AS-IS") and facilitate comparison between processes while identifying opportunities for improvement.

**4.1 Standard Process Assessment Criteria**
| KPI                     | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| Manual Effort           | Level of manual work required to complete the process    |
| Number of Systems       | Number of systems or applications involved               |
| Spreadsheet Dependency  | Degree of reliance on Excel or CSV files                 |
| Manual Data Validation  | Amount of manual review required to verify data accuracy |
| Data Quality Dependency | Degree to which process quality depends on source data   |
| Process Standardization | Consistency of process execution across the team         |


## 5. Current Process Analysis 

### 5.1 Travel Manifest Preparation
**Process Objective:** Prepare an accurate travel manifest for airport arrivals and departures by consolidating participant travel information, assigning airport staff and communicating arrival instructions.

**Process Trigger:** Travel forms become available in Portal Site after participants submit their arrival information.

**Process Steps:**
| Step | Activity                                                       | System                 | Manual / Automated |
| ---- | -------------------------------------------------------------- | ---------------------- | ------------------ |
| 1    | Download travel forms                                          | Portal Site            | Manual             |
| 2    | Sort records by submission date, arrival form and arrival time | Excel                  | Manual             |
| 3    | Identify incomplete travel information                         | Excel                  | Manual             |
| 4    | Verify arrival windows                                         | Excel/Detail Program Calendar| Manual       |
| 5    | Review available airport staff                                 | SharePoint Client Grid | Manual             |
| 6    | Assign airport signer to each participant                      | Excel                  | Manual             |
| 7    | Upload internal manifest                                       | SharePoint             | Manual             |
| 8    | Create vendor version of manifest                              | Excel                  | Manual             |
| 9    | Request additional airport staff if necessary                  | Outlook                | Manual             |
| 10   | Notify parents                                                 | Outlook                | Manual             |
| 11   | Generate printable manifest                                    | Excel                  | Manual             |

**Inputs:**
| Input                      | Source            |
| -------------------------- | ----------------- |
| Travel Forms               | Portal Site       |
| Participant Information    | Portal Site       |
| Airport Staff Availability | Client Grid       |
| Session Information        | Dynamics/EventHub |

**Outputs:**
| Output                   | Destination            |
| ------------------------ | ---------------------- |
| Internal Travel Manifest | SharePoint             |
| Vendor Travel Manifest   | Airport Staff Provider |
| Parent Notifications     | Outlook                |
| Printable Manifest       | Operations Team        |

**Pain Points** 

| ID    | Observation                                          | Business Impact           |
| ----- | ---------------------------------------------------- | ------------------------- |
| AP-01 | Multiple Excel files are created during the process. | Duplicate work            |
| AP-02 | Information must be manually reformatted.            | Increased processing time |
| AP-03 | Parent notifications are sent individually.          | High operational effort   |
| AP-04 | Staff assignments are manual.                        | Scheduling errors         |
| AP-05 | Data validation depends on human review.             | Human error               |
| AP-06 | Multiple document versions exist.                    | Version control issues    |
| AP-07 | Changes are communicated by email.                   | Lack of traceability      |

**Process Metrics**

| KPI                     | Current Observation |
| ----------------------- | ------------------- |
| Manual Effort           | High                |
| Number of Systems       | 8+                  |
| Spreadsheet Dependency  | High                |
| Manual Data Validation  | High                |
| Data Quality Dependency | High                |
| Process Standardization | Medium-Low          |
| Manual Notifications    | High                |


**Improvement Oportunities**

| ID    | Opportunity                    |
| ----- | ------------------------------ |
| IO-01 | Reduce spreadsheet dependency  |
| IO-02 | Improve data validation        |
| IO-03 | Standardize document templates |
| IO-04 | Centralize task tracking       |
| IO-05 | Improve process visibility     |
| IO-06 | Reduce manual communications   |
| IO-07 | Minimize duplicate data entry  |

### 5.2 Room Assignment 

**Process Objective:**  
Assign students to available campus rooms by matching participant information and campus room availability while ensuring room assignments meet program requirements.

**Process Trigger:**  
Student participant information becomes available after registration data is collected and room assignment preparation begins for an upcoming program session.

**Process Steps:**
| Step | Activity                                                                                     | System           | Manual / Automated |
| ---- | -------------------------------------------------------------------------------------------- | ---------------- | ------------------ |
| 1    | Retrieve participant information including number by gender and pkcode                       | Database         | Manual             |
| 2    | Consult housing preferences and roommate requests                                            | Erudio           | Manual             |
| 3    | Review Dynamic cases for roomate request                                                     | Dynamics 365     | Manual             |
| 4    | Review available buildings, rooms and occupancy capacity                                     | Excel Sharepoint | Manual             |
| 5    | Fill the room assignment template with information collected of housting Database            | Excel            | Manual             |
| 6    | Upload room assignment template to database                                                  | Database         | Manual             |
| 7    | Database auto assign students with available rooms based roomate request and prioritizing by age| Database      | Automated          |
| 8    | Fill the Staff Template provided by Program Team                                             | Sharepoint/Excel | Manual             |
| 9    | Share finalized rooming information with relevant teams                                      | SharePoint/Teams | Manual             |
|10    | Fill the template csv for EventHubb App Room Import                                          | csv/Eventhub App | Manual             |

**Inpunts:**

| Input                           | Source            |
| ------------------------------- | ----------------- |
| Session program information     | Database          |
| Gender information              | Database          |
| Roommate requests               | Erudio/Dynamics   |
| Campus room availability        | SharePoint        |

**Outputs:**
| Output                                | Destination      |
| ------------------------------------- | ---------------- |
| Student room assignments              | Database         |
| Updated rooming spreadsheet           | SharePoint       |
| Housing information for program teams | SharePoint/Teams |
| Final room allocation report          | Operations Team  |

**Pain Points:**
| ID    | Observation                                                                          | Business Impact                                |
| ----- | ------------------------------------------------------------------------------------ | ---------------------------------------------- |
| AP-08 | Room availability information is maintained separately from participant information. | Requires manual reconciliation between sources |
| AP-09 | Room assignment templates require manual preparation and formatting.                 | Increases processing time                      |
| AP-10 | Housing changes require manual updates across documents.                             | Risk of inconsistent information               |
| AP-11 | Validation of room assignments depends on manual review.                             | Potential assignment errors                    |
| AP-12 | Final rooming information depends on spreadsheet updates.                            | Limited real-time visibility                   |
| AP-13 | Room assignment logic depends on operational knowledge.                              | Higher dependency on team experience           |

**Process metrics:**
| KPI                     | Current Observation |
| ----------------------- | ------------------- |
| Manual Effort           | High                |
| Number of Systems       | 5                   |
| Spreadsheet Dependency  | High                |
| Manual Data Validation  | High                |
| Data Quality Dependency | High                |
| Process Standardization | Medium              |
| Automated Processing    | Partial             |


**Improvement Opportunities:**
| ID    | Opportunity                                                                                                      |
| ----- | ---------------------------------------------------------------------------------------------------------------- |
| IO-08 | Improve synchronization between participant information, housing preferences and room availability data          |
| IO-09 | Reduce manual data preparation and spreadsheet-based processing before room assignment                           |
| IO-10 | Standardize room assignment templates and data formats across systems                                            |
| IO-11 | Improve visibility of room assignment status and completion tracking                                             |
| IO-12 | Reduce manual data transformation required for system imports                                                    |
| IO-13 | Improve validation of housing requirements, roommate requests and assignment exceptions                          |
| IO-14 | Reduce dependency on individual operational knowledge through improved documentation and process standardization |


### 5.3 Certificate Generation 

**Process Objective:**  
Provide students with accurate program completion certificates by retrieving certificate files from Erudio and ensuring certificates match the correct program session and participant information.

**Process Trigger:**  
Certificates become available in Erudio after participant information has been processed and certificate records have been generated for completed program sessions.

**Pocess Steps:**
| Step | Activity                                                             | System                       | Manual / Automated |
| ---- | -------------------------------------------------------------------- | ---------------------------- | ------------------ |
| 1    | Access available certificates for completed program sessions         | Erudio                       | Manual             |
| 2    | Download certificate files from Erudio                               | Erudio                       | Manual             |
| 3    | Review downloaded certificate files                                  | Local files/ZIP              | Manual             |
| 4    | Compare certificate recipients against expected session participants | Event Support Report SQL Server| Manual           |
| 5    | Identify missing certificates or incorrect certificates              | Excel ESR                    | Manual             |
| 6    | Validate participant information displayed on certificates           | Certificate Files            | Manual             |
| 7    | Report certificate discrepancies or request corrections if needed    | Outlook/Teams                | Manual             |
| 8    | Provide final certificates for distribution                          | SharePoint/Program Resources | Manual             |

**Inputs:**
| Input                                | Source                    |
| ------------------------------------ | ------------------------- |
| Participant registration information | Parent Registration Forms |
| Student information                  | SQL Server                |
| Generated certificate files          | Erudio                    |

**Outputs:**
| Output                                    | Destination                |
| ----------------------------------------- | -------------------------- |
| Student certificates                      | Program Resources          |
| Certificate validation results            | Event Support Team         |
| List of missing or incorrect certificates | Internal Team              |

**Pain Point:**
| ID    | Observation                                                                       | Business Impact                                                   |
| ----- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| AP-14 | Certificate information depends on data entered by parents during registration.   | Incorrect formatting or spelling can appear on official documents |
| AP-15 | Name formatting is not standardized before certificate generation.                | Inconsistent student names (uppercase/lowercase issues)           |
| AP-16 | Downloaded certificate packages may contain certificates from incorrect sessions. | Additional manual review required                                 |
| AP-17 | Some expected certificates may be missing from downloaded files.                  | Delays certificate distribution                                   |
| AP-18 | Certificate validation requires manual comparison against session participants.   | Increased operational effort                                      |
| AP-19 | Certificate generation workflow visibility is limited.                            | Difficult to identify where errors originate                      |

**Process Metrics:**
| KPI                     | Current Observation |
| ----------------------- | ------------------- |
| Manual Effort           | High                |
| Number of Systems       | 3                   |
| Spreadsheet Dependency  | Low                 |
| Manual Data Validation  | High                |
| Data Quality Dependency | High                |
| Process Standardization | Medium-Low          |
| File Verification       | High                |


**Improvement Oportunities**
| ID    | Opportunity                                                                                       |
| ----- | ------------------------------------------------------------------------------------------------- |
| IO-14 | Improve validation of participant information before certificate generation                       |
| IO-15 | Standardize student name formatting rules across registration and operational systems             |
| IO-16 | Improve certificate reconciliation between generated certificates and active session participants |
| IO-17 | Reduce manual effort required to identify missing or incorrect certificates                       |
| IO-18 | Improve visibility into certificate generation status and completion                              |
| IO-19 | Establish a standardized certificate quality control process                                      |

### 5.4 Name Badge Generation 

**Process Objective:**
Generate accurate and standardized student name badges by consolidating participant information, program contact details and program-specific resources into a mail merge template for printing and distribution.

**Process Trigger:**
The Event Support Report (ESR) becomes available after participant registration information has been processed for an upcoming program session.

**Process Steps:**
| Step | Activity                                                                                                     | System                               | Manual / Automated |
| ---- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------ | ------------------ |
| 1    | Download the Event Support Report (ESR) for the selected program and session                                 | SQL Server Reporting Services (SSRS) | Manual             |
| 2    | Review participant information contained in the ESR                                                          | Excel                                | Manual             |
| 3    | Populate the Name Badge Excel template with participant information from the ESR                             | Excel                                | Manual             |
| 4    | Retrieve Program Lead, Education Lead and 24/7 phone numbers from the Operations Hub Contact List            | SharePoint                           | Manual             |
| 5    | Populate contact information into the Name Badge template                                                    | Excel                                | Manual             |
| 6    | Verify the appropriate Word template and color based on the program                                          | Word                                 | Manual             |
| 7    | Verify that the correct QR codes for Scholar Daily Survey and Scholar Resources are included in the template | Word / Scanova                       | Manual             |
| 8    | Review participant names for formatting consistency (capitalization and spelling)                            | Excel                                | Manual             |
| 9    | Execute the Mail Merge process to generate Name Badges                                                       | Microsoft Word                       | Manual             |
| 10   | Export the generated Name Badges to PDF                                                                      | Word / PDF                           | Manual             |
| 11   | Upload the final PDF to SharePoint                                                                           | SharePoint                           | Manual             |

**Inputs:** 
| Input                      | Source                               |
| -------------------------- | ------------------------------------ |
| Event Support Report (ESR) | SQL Server Reporting Services (SSRS) |
| Participant information    | ESR                                  |
| Program contact list       | Operations Hub (SharePoint)          |
| Name Badge Excel template  | SharePoint                           |
| Name Badge Word template   | SharePoint                           |
| Program QR Codes           | Scanova                              |

**Outputs:**
| Output                | Destination     |
| --------------------- | --------------- |
| Mail Merge Output     | PDF             |
| Name Badge PDF        | SharePoint      |
| Printable Name Badges | Operations Team |

**Pain Points:**
| ID    | Observation                                                                                | Business Impact                                      |
| ----- | ------------------------------------------------------------------------------------------ | ---------------------------------------------------- |
| AP-20 | Participant information must be manually copied from the ESR into the Name Badge template. | Repetitive manual work and increased processing time |
| AP-21 | Contact information is retrieved from a separate spreadsheet.                              | Multiple data sources increase complexity            |
| AP-22 | Participant names require manual formatting corrections before mail merge.                 | Risk of inconsistent printed badges                  |
| AP-23 | Program-specific QR codes must be manually verified.                                       | Incorrect QR codes may be included in printed badges |
| AP-24 | Mail Merge templates depend on exact field names.                                          | Small formatting errors can cause merge failures     |
| AP-25 | Multiple templates must be maintained for different programs.                              | Higher maintenance effort                            |
| AP-26 | Final quality control depends entirely on manual review.                                   | Increased probability of printing errors             |

**Process Metris:**
| KPI                     | Current Observation |
| ----------------------- | ------------------- |
| Manual Effort           | High                |
| Number of Systems       | 5                   |
| Spreadsheet Dependency  | High                |
| Manual Data Validation  | High                |
| Data Quality Dependency | High                |
| Process Standardization | Medium              |
| Mail Merge Dependency   | High                |

**Improvement Oportunities:**
| ID    | Opportunity                                                                              |
| ----- | ---------------------------------------------------------------------------------------- |
| IO-20 | Reduce manual data transfer between the Event Support Report and the Name Badge template |
| IO-21 | Standardize participant name formatting before document generation                       |
| IO-22 | Centralize program contact information used during Name Badge preparation                |
| IO-23 | Reduce manual validation of Mail Merge fields and template configuration                 |
| IO-24 | Improve validation of program-specific QR code assignments                               |
| IO-25 | Standardize Name Badge templates across programs where applicable                        |
| IO-26 | Improve quality control prior to PDF generation and distribution                         |

## 6. Key Findings
The following key findings summarize the most significant observations identified across the four operational processes analyzed. These recurring themes highlight common challenges affecting efficiency, data quality, process visibility, and standardization. 

| Finding ID | Observation                                                                              | Impact                                                  |
| ---------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| KF-01      | Heavy reliance on manual data handling across operational workflows.                     | Increased processing time and risk of human error.      |
| KF-02      | Information is distributed across multiple systems with limited integration.             | Duplicate work and inconsistent data.                   |
| KF-03      | Spreadsheet-based processes are widely used for operational activities.                  | Reduced scalability and limited process visibility.     |
| KF-04      | Data quality issues originating from source systems propagate to downstream processes.   | Rework and inaccurate operational documents.            |
| KF-05      | Operational knowledge is highly dependent on team experience and manual procedures.      | Increased onboarding effort and operational risk.       |
| KF-06      | Process traceability is limited due to decentralized task management and communications. | Difficult to monitor progress and identify bottlenecks. |

## 7. Conclusion

The AS-IS analysis identified several recurring patterns across the Event Support operational workflows. Most processes rely heavily on manual data handling, multiple disconnected systems, spreadsheet-based activities, and manual validation, increasing operational effort and the risk of inconsistencies. While certain activities are partially automated, significant opportunities remain to improve process standardization, data quality, traceability, and operational efficiency. These findings establish the baseline for the TO-BE Process Design, where targeted improvements and future-state workflows will be proposed.




