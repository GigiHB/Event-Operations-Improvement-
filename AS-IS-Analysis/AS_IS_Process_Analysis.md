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
| P-01 | Room Assignment             | Documented |
| P-02 | Travel Manifest Preparation | Documented |
| P-03 | Certificate Generation      | Pending    |
| P-04 | Name Badge Generation       | Pending    |
| P-05 | Parent Communications       | Pending    |

## 3. System Used
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

## 4. Current Process 

### Travel Manifest Preparation
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

| KPI                 | Current Observation |
| ------------------- | ------------------- |
| Manual Steps        | High                |
| Number of Systems   | 8+                  |
| Email Notifications | Manual              |
| Spreadsheet dependency| High              |
| Manual Validation   | High                |
| Standardization     | Medium-Low          |

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

### Room Asignment 

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
| KPI                      | Current Observation |
| ------------------------ | ------------------- |
| Manual  Steps            | High                |
| Number of Systems        | 4                   |
| Spreadsheet Dependency   | High                |
| Automated Matching       | Partial             |
| Manual Validation        | High                |
| Standardization          | Medium              |

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




