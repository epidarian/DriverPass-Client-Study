# Business Requirements Document

## System Components and Design

### Purpose

The purpose of this project is to design a comprehensive training and management system for the client, DriverPass. The client seeks to address a market deficiency where a significant number of students fail driving tests due to preparation methods limited to studying previous exams. The proposed system will provide a platform for online coursework, practice testing, and the scheduling of on-the-road training sessions. The design must accommodate the specific operational requirements of management, IT support, and administrative staff. Separate provisions must be made to facilitate user-friendly access for customers.

### System Background

DriverPass intends to remediate a 65% failure rate among driving students. This statistic is attributed to preparation strategies currently limited to reviewing past examinations. The proposed system will bridge this gap by offering a hybrid model of online coursework and practical on-the-road training.

Technically, the solution requires a web-based architecture hosted on the cloud. This configuration is selected to minimize internal maintenance overhead regarding security and backups. The system must support data access in both online and offline environments. Furthermore, the architecture requires an integration interface with the Department of Motor Vehicles to ensure regulatory compliance and content currency.

### Objectives and Goals

The primary objective is to deliver a functional reservation and learning management system. Upon completion, the system must enable customers to schedule, modify, and cancel driving appointments independently. Internally, the application is required to track resource allocation, specifically the assignment of drivers and vehicles to scheduled sessions. From an administrative perspective, the system must provide comprehensive audit trails for all record modifications. It must support the generation and export of activity reports for offline analysis. Additionally, the system will maintain synchronization with DMV standards through automated updates to the testing curriculum.

#### Measurable Tasks

**Access Control**
The system must support role-based access, allowing the IT administrator to reset credentials and block user access. It must also provide an automated mechanism for customers to reset forgotten passwords. This justification stems from the IT officer's operational requirements. Ian explicitly specified the need for administrative privileges to manage personnel access and reset accounts. Furthermore, the requirement for a self-service password reset function was identified to minimize technical support dependencies for the client.

**Package Management**
The architecture must support the three specific service packages currently offered. Administrators must have the capability to enable or disable these packages via the interface without requiring code deployment. Liam requested the specific capability to disable these packages through the interface. This feature is necessary to allow management to control inventory and service availability without requiring developer intervention for code changes.

**Student Progress Tracking**
The system must record and display the status of online coursework. This includes logging test names, duration, scores, and completion states (e.g., passed, failed, in progress). This requirement is derived directly from the client's functional description and visual mockup. The owner specified that the interface must quantify student performance. This includes the explicit display of test names, timestamps, scores, and completion statuses to validate the educational component of the service.

**Data Collection and Display**
The registration module must capture comprehensive user data, including billing information and pickup/drop-off coordinates. The interface is required to display driver notes and lesson timestamps in a tabular format for review. The owner enumerated fields such as billing details and geolocational coordinates for pickup and drop-off to ensure logistical feasibility. Additionally, the tabular display of driver notes was a specific request intended to provide a historical record of practical training sessions.

---

## Requirements

### Nonfunctional Requirements

#### Performance Requirements

The system operates as a cloud-hosted web application, designed to function across standard browser environments on both desktop and mobile platforms. To mitigate the risk of data redundancy and ensure record integrity, all database transactions require real-time processing via an active internet connection. Additionally, the system must support an event-driven update cycle, synchronizing testing materials immediately upon receipt of notification from the Department of Motor Vehicles.

#### Platform Constraints

The system architecture requires a platform-agnostic design, capable of executing within standard web browsers across Windows, macOS, and mobile operating systems. The backend infrastructure relies on a cloud-based deployment model to abstract hardware maintenance and physical security requirements. Functionally, the application necessitates a relational database management system to structure and persist reservation data, user profiles, and training logs. Additionally, the reporting module must generate output formats compatible with Microsoft Excel to facilitate offline administrative analysis.

#### Accuracy and Precision

The system must enforce unique identification for each user entity to ensure the precise attribution of record modifications. To guarantee security and data integrity, authentication credentials require case-sensitive input validation. Operationally, the system is obligated to maintain a persistent audit trail, allowing administrators to isolate the source of scheduling conflicts or unauthorized account changes. Additionally, the system must detect and alert administrators to data synchronicity failures or redundancy issues arising from connectivity interruptions.

#### Adaptability

The system architecture must support administrative configuration of service packages, specifically allowing management to enable or disable offerings without requiring code deployment. To accommodate personnel changes, the IT administrator requires elevated privileges to modify user roles, reset credentials, and revoke access rights. Regarding platform evolution, the cloud-based nature of the application dictates that infrastructure updates and security patches are managed by the service provider to minimize local maintenance requirements.

#### Security

The system requires a robust authentication framework that supports distinct user roles with varying privilege levels. The IT administrator must possess the authority to manage all accounts, including the capability to reset credentials and terminate access for specific users. For end-users, the interface must include an automated recovery workflow to allow customers to reset lost passwords without technical intervention. Infrastructure-level security, including data encryption and backup protocols, is delegated to the cloud service provider to minimize the client's technical liability. Additionally, the system must implement strict activity logging to identify the source of all reservation modifications and ensure accountability.

### Functional Requirements

- The system shall validate user credentials against stored profiles to grant access and support an automated mechanism for password recovery.
- The system shall enable customers to schedule, modify, and cancel driving appointments independently via the web interface.
- The system shall allow administrators to toggle the availability of specific service packages without requiring modifications to the underlying codebase.
- The system shall track the allocation of specific drivers and vehicles to reservation timeslots to prevent resource scheduling conflicts.
- The system shall generate comprehensive activity reports detailing reservation history and modification logs to facilitate administrative auditing.
- The system shall capture required user data during the registration process, including billing information and specific addresses for pickup and drop-off.
- The system shall integrate with the Department of Motor Vehicles to automatically ingest updates regarding testing rules, policies, and sample questions.
- The system shall display the real-time progress of online coursework, specifically indicating test names, duration, scores, and completion status.

### User Interface

The system requires a responsive web interface accessible via desktop and mobile browsers. Distinct dashboard views are necessary for four user roles: Owner, IT Officer, Secretary, and Customer. The Customer interface must support self-service tasks, including appointment scheduling, payment processing, and coursework progress tracking. Conversely, the Administrative interface requires tools for resource allocation, driver assignment, and report generation. The IT interface is restricted to account maintenance and security management functions.

---

## Assumptions

The system design is predicated on the availability of a persistent internet connection for all administrative transactions to ensure data integrity. It is assumed that the Department of Motor Vehicles maintains an accessible interface to facilitate the required automated content updates. Functionally, the architecture presumes that the cloud service provider manages all infrastructure-level security and backup protocols without requiring local configuration. Additionally, the design assumes that the user base possesses compatible hardware to access the web-based interface.

---

## Limitations

The primary functional limitation dictates that administrative data modification is restricted to online environments to prevent synchronization conflicts. Regarding scope, the initial release precludes the dynamic creation or customization of service packages, limiting administrative control to the activation or deactivation of existing inventory. Operationally, the system relies entirely on third-party cloud infrastructure for data redundancy and security, as the client lacks the internal resources to manage backend maintenance.

---

## Gantt Chart

*A Gantt chart was created using Lucidchart to illustrate the project timeline as described in the client interview.*
