# To-Be Process Design 

## 1. Purpose
The purpose of the TO-BE Process Design is to define a future-state operating model for the Event Support workflows analyzed in the AS-IS document. The proposed future state focuses on reducing manual effort, improving data consistency, increasing process visibility, standardizing operational procedures, and reducing unnecessary duplication across systems and spreadsheets.

The TO-BE design builds upon the organization's existing systems and workflows while identifying opportunities for process optimization, automation, improved validation, and centralized task tracking.

## 2. Future-State Design Principles

The future-state processes will be designed according to the following principles:

| Principle | Description |
|-----------|-------------|
| Reduce Manual Effort | Minimize repetitive data entry, formatting, validation, and document preparation activities. |
| Improve Data Quality | Introduce validation rules and standardized data handling to reduce errors originating from inconsistent or incomplete information. |
| Minimize Duplicate Work | Reduce unnecessary copying and reformatting of information across spreadsheets, documents, and systems. |
| Standardize Processes | Establish consistent workflows, templates, procedures, and documentation across the Event Support team. |
| Improve Traceability | Provide greater visibility into task ownership, status, changes, and outstanding activities. |
| Leverage Existing Systems | Prioritize improvements that can work with the organization's current technology landscape before considering system replacement. |
| Enable Automation | Identify repetitive, rule-based activities that can be automated through available tools, integrations, or scripts. |
| Improve Scalability | Design processes that can support increased program volume without proportionally increasing manual workload. |

## 3. Improvement Priorities

Based on the AS-IS analysis, the following areas have been identified as the primary improvement priorities:

| Priority | Area | Objective |
|----------|------|-----------|
| IP-01 | Data Quality | Reduce errors caused by inconsistent, incomplete, or incorrectly formatted source data. |
| IP-02 | Process Automation | Automate repetitive and rule-based operational activities where feasible. |
| IP-03 | Spreadsheet Dependency | Reduce unnecessary spreadsheet manipulation and duplicate data handling. |
| IP-04 | Process Standardization | Establish consistent procedures, templates, and documentation. |
| IP-05 | Process Visibility | Improve tracking of tasks, ownership, status, and pending activities. |
| IP-06 | Communication | Reduce unnecessary manual communication and improve information flow between teams. |
| IP-07 | Traceability | Improve the ability to identify changes, responsible parties, and process history. |

## 4. Future-State Process Overview

### 4.1 Travel Manifest Preparation

**Future-State Objective:**  
Create a standardized and traceable travel manifest workflow that consolidates participant travel information, validates travel data, supports airport staff assignment, and generates the required internal and external manifests with minimal manual reformatting and duplicate data entry.

**Future-State Trigger:**  
New or updated participant travel information becomes available and is ready for operational processing.

**Future-State Process:**

| Step | Activity | Future-State Approach |
|------|----------|-----------------------|
| 1 | Retrieve participant travel information | Consolidate available travel information into a standardized working dataset. |
| 2 | Validate travel information | Apply standardized validation rules to identify missing information, incomplete flight details, and arrivals outside the approved window. |
| 3 | Identify exceptions | Automatically categorize records requiring follow-up or operational attention. |
| 4 | Review airport staff availability | Use a centralized staff availability source to determine available airport coverage. |
| 5 | Assign airport staff | Assign staff to verified arrivals using standardized assignment rules. |
| 6 | Identify staffing gaps | Flag arrivals that require additional airport coverage. |
| 7 | Request additional staff | Notify the appropriate team when staffing requirements cannot be met. |
| 8 | Generate internal manifest | Produce a standardized internal manifest from the validated dataset. |
| 9 | Generate vendor manifest | Generate a standardized external version containing only the information required by the airport staffing provider. |
| 10 | Communicate confirmed arrival information | Send standardized notifications based on the final verified travel information. |
| 11 | Publish final manifest | Store the final version in a centralized location with clear version control. |

### 4.2 Room Assignment

**Future-State Objective:**  
Streamline the room assignment workflow by reducing manual data preparation, improving validation of housing requirements, and creating a consistent flow of rooming information from participant data through final program and EventHub outputs.

**Future-State Trigger:**  
Participant housing information and campus room availability are ready for room assignment preparation.

**Future-State Process:**

| Step | Activity | Future-State Approach |
|------|----------|-----------------------|
| 1 | Retrieve participant information | Use a standardized participant dataset containing required housing information. |
| 2 | Consolidate housing preferences | Consolidate roommate requests and housing preferences into the room assignment workflow. |
| 3 | Validate housing requirements | Identify incomplete, conflicting, or exceptional housing information before assignment. |
| 4 | Retrieve room availability | Use a standardized and current source for available buildings, rooms, and occupancy capacity. |
| 5 | Prepare assignment input | Generate the required assignment input using standardized data formatting. |
| 6 | Execute room assignment | Use the existing database assignment logic to match students with available rooms. |
| 7 | Validate assignment results | Apply validation rules to identify assignment conflicts or exceptions. |
| 8 | Generate staff and operational outputs | Generate standardized rooming information for program staff. |
| 9 | Generate EventHub import file | Produce the required CSV using a standardized format. |
| 10 | Publish final rooming information | Store and share the final approved rooming information through a centralized location. |

### 4.3 Certificate Generation

**Future-State Objective:**  
Improve certificate generation and distribution by reducing manual verification effort, improving participant data quality, and ensuring that generated certificates match the correct program session roster.

**Future-State Trigger:**  
Certificates become available for an upcoming or completed program session.

**Future-State Process:**

| Step | Activity | Future-State Approach |
|------|----------|-----------------------|
| 1 | Retrieve certificate files | Access the certificate package through the existing certificate platform. |
| 2 | Validate session roster | Compare available certificates against the expected participant roster. |
| 3 | Validate participant information | Identify inconsistent or incorrectly formatted participant information. |
| 4 | Identify missing or extra certificates | Automatically or systematically flag certificates that do not match the expected session roster. |
| 5 | Resolve exceptions | Route missing, incorrect, or unexpected certificates for correction. |
| 6 | Confirm final certificate package | Verify that all expected participants have a corresponding valid certificate. |
| 7 | Publish final certificates | Store the validated certificate package in a standardized location. |

### 4.4 Name Badge Generation

**Future-State Objective:**  
Standardize and streamline name badge generation by reducing manual data preparation, enforcing consistent name formatting, validating required contact information, and minimizing errors during mail merge preparation.

**Future-State Trigger:**  
The Event Support Report and required program contact information are available for the target session.

**Future-State Process:**

| Step | Activity | Future-State Approach |
|------|----------|-----------------------|
| 1 | Retrieve participant information | Retrieve the required participant information from the Event Support Report. |
| 2 | Retrieve program contact information | Retrieve current program and staff contact information from the standardized Operations Hub source. |
| 3 | Consolidate required data | Combine participant and operational information into a standardized dataset. |
| 4 | Validate participant names | Apply standardized capitalization and formatting rules. |
| 5 | Validate required fields | Identify missing participant, contact, program, or group information. |
| 6 | Select program configuration | Apply the correct program template, color, and QR resources. |
| 7 | Generate name badges | Populate the standardized Word template using the validated dataset. |
| 8 | Validate output | Perform a final automated or structured quality check before distribution. |
| 9 | Generate PDF | Convert the validated name badge output to PDF. |
| 10 | Publish final file | Store the final PDF in the designated SharePoint location. |

## 5. AS-IS to TO-BE Improvement Matrix

The following matrix connects the key issues identified during the AS-IS analysis with the proposed future-state improvements and potential automation opportunities. The matrix is intended to provide a bridge between process improvement and the technical solutions that may be evaluated during later project phases.

| ID     | AS-IS Problem                                                           | TO-BE Improvement                                 | Automation Opportunity                                                | Potential Technology     |
| ------ | ----------------------------------------------------------------------- | ------------------------------------------------- | --------------------------------------------------------------------- | ------------------------ |
| IMP-01 | Multiple Excel files and repeated data manipulation                     | Establish a standardized working dataset          | Automate data consolidation and formatting                            | Power Automate / Python  |
| IMP-02 | Manual travel information validation                                    | Introduce standardized validation rules           | Automatically identify missing or invalid travel information          | Power Automate / Python  |
| IMP-03 | Manual airport staff assignment                                         | Standardize staff assignment criteria             | Support rule-based staff assignment and exception identification      | Excel / Power Automate   |
| IMP-04 | Multiple travel manifest versions                                       | Generate standardized internal and vendor outputs | Automatically generate required manifest versions                     | Power Automate / Excel   |
| IMP-05 | Room assignment input requires manual preparation                       | Standardize room assignment input                 | Automate data preparation and validation before database upload       | Python / Power Automate  |
| IMP-06 | Manual room assignment validation                                       | Introduce automated validation checks             | Flag room conflicts and missing requirements                          | Python / Excel           |
| IMP-07 | Certificate packages may contain missing or unexpected certificates     | Reconcile certificates against session roster     | Automatically compare expected participants against certificate files | Python                   |
| IMP-08 | Participant names require manual formatting for certificates and badges | Standardize participant name formatting           | Automatically normalize capitalization and formatting                 | Python / Power Automate  |
| IMP-09 | Name badge data is manually copied between sources                      | Consolidate participant and operational data      | Automate dataset preparation for mail merge                           | Power Automate / Python  |
| IMP-10 | Name badge templates require manual verification                        | Standardize program configuration and validation  | Automatically validate required fields and template inputs            | Power Automate           |
| IMP-11 | Operational tasks are tracked through SharePoint grids and messages     | Centralize task tracking and ownership            | Automate task creation, assignment, and status updates                | Jira / Microsoft Planner |
| IMP-12 | Process changes and exceptions are communicated primarily through email | Improve process traceability                      | Trigger notifications based on status or exception conditions         | Power Automate           |
| IMP-13 | Outdated or inconsistent process documentation                          | Establish controlled process documentation        | Maintain standardized procedures and version-controlled documentation | GitHub / SharePoint      |
| IMP-14 | Multiple systems contain related participant information                | Improve information flow between systems          | Evaluate integration opportunities between existing systems           | APIs / Power Automate    |

## 6. Expected Benefits

The proposed future-state processes are expected to improve operational efficiency, data quality, process consistency, and visibility across the Event Support function. The expected benefits include:

| ID | Expected Benefit | Description |
|----|------------------|-------------|
| EB-01 | Reduced Manual Effort | Reduce repetitive activities such as data entry, formatting, validation, document preparation, and duplicate data handling. |
| EB-02 | Improved Data Quality | Reduce errors caused by incomplete, inconsistent, or incorrectly formatted participant and operational information. |
| EB-03 | Reduced Processing Time | Streamline repetitive workflows and reduce the time required to prepare operational documents and outputs. |
| EB-04 | Improved Process Standardization | Establish consistent workflows, templates, validation rules, and documentation across Event Support activities. |
| EB-05 | Improved Process Visibility | Provide greater visibility into task status, ownership, pending activities, and operational exceptions. |
| EB-06 | Improved Traceability | Make process changes, exceptions, and decisions easier to track and review. |
| EB-07 | Reduced Spreadsheet Dependency | Minimize unnecessary spreadsheet manipulation and duplicate versions of operational information. |
| EB-08 | Improved Scalability | Enable the Event Support team to handle increased program volume without a proportional increase in manual workload. |
| EB-09 | Reduced Communication Overhead | Reduce unnecessary email-based coordination through standardized notifications and centralized task information. |
| EB-10 | Improved Operational Reliability | Reduce the likelihood of errors affecting travel manifests, room assignments, certificates, and name badges. |

## 7. Implementation Considerations

Implementation of the proposed future-state processes should consider the organization's existing systems, data dependencies, operational constraints, and user adoption requirements. Improvements should be introduced incrementally and prioritized according to business value, technical feasibility, and implementation effort.

| Consideration | Description |
|---------------|-------------|
| Existing Systems | Proposed improvements should leverage existing platforms and workflows where possible before considering system replacement. |
| Data Dependencies | Automation depends on the availability, consistency, and reliability of participant and operational data across existing systems. |
| System Access | Some automation opportunities may require appropriate access, permissions, APIs, or integration capabilities that must be evaluated before implementation. |
| Process Ownership | Each automated or redesigned process should have a clearly defined owner responsible for maintaining the workflow and resolving exceptions. |
| Exception Handling | Automation should not assume that all cases follow standard rules. Exceptions should be identified and routed for manual review when necessary. |
| Data Quality | Automation will not eliminate problems caused by incorrect source data. Validation and data quality controls should therefore be included in the future-state design. |
| User Adoption | Process changes should be introduced with clear documentation, training, and communication to ensure consistent adoption by the Event Support team and other stakeholders. |
| Change Management | Changes to operational workflows should be documented and communicated to affected teams before implementation. |
| Security and Privacy | Participant and parent information should be handled according to organizational security, privacy, and access requirements. |
| Scalability | Proposed solutions should be evaluated based on their ability to support multiple programs, sessions, and increasing operational volume. |
| Maintainability | Automated workflows, scripts, templates, and integrations should be documented and designed so they can be maintained by the appropriate team. |
| Phased Implementation | Improvements should be implemented incrementally, beginning with high-value and relatively low-complexity opportunities. |


