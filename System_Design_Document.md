# System Design Document

## UML Diagrams

### UML Use Case Diagram

The use case diagram illustrates all actors interacting with the DriverPass system and their associated use cases:

**Internal Actors:**
- Owner: Generate activity reports, disable packages
- IT Officer: Manage user accounts, reset passwords, block access
- Secretary: Schedule appointments, register users

**External Actors:**
- Customer: Login, view information, make/modify reservations, take practice tests, register
- DMV: Send updates on rules and policies

### UML Activity Diagrams

The activity diagrams document the step-by-step workflows for key system processes:

**Reservation Scheduling Process:**
1. Customer logs into system
2. Customer selects package (Package 1: 6 hours, Package 2: 8 hours, Package 3: 12 hours)
3. Customer chooses preferred date and time for two-hour lesson
4. System checks driver and car availability
5. If unavailable: Display message requesting different time selection
6. If available: Customer confirms pickup location
7. System saves reservation details
8. Driver and car schedules updated
9. Customer receives booking confirmation

### UML Sequence Diagram

The sequence diagram depicts the interaction between objects over time for key system operations, showing the message flow between:
- User interface components
- Authentication services
- Database systems
- External DMV integration

### UML Class Diagram

The class diagram defines the system's object-oriented structure, including:
- User classes (Owner, IT Officer, Secretary, Customer)
- Resource classes (Driver, Vehicle)
- Transaction classes (Reservation, Package, Payment)
- System classes (Course, Test, Report)

---

## Technical Requirements

### Hardware Requirements

To support the DriverPass system, the technical design requires a robust client-server architecture that leverages cloud-based resources while strictly defining the necessary virtualized hardware. The primary hardware requirement involves deploying virtualized web servers and database servers capable of handling concurrent connections from multiple user types, including the owner, IT staff, secretaries, and customers. These server instances must possess sufficient processing power (CPU) and memory (RAM) to manage real-time scheduling, transaction processing, and the "cloud" hosting environment requested by the client. On the client side, the system must support a variety of physical hardware, specifically desktop computers and mobile devices, ensuring the owner can access data and reports from any location.

### Software Requirements

The software landscape for the system is built around a web-based application interface that runs on the server infrastructure and renders in standard web browsers. To manage the complex data relationships (such as linking customers to specific packages, instructors, and vehicles) the system requires a relational Database Management System (DBMS). This database software is critical for preventing data redundancy and ensuring data integrity across the various tables defined in the design. Additionally, the software stack must include an Application Programming Interface (API) integration layer to maintain a persistent connection with the DMV for receiving automated updates on rules and policies.

### Infrastructure and Tools

Regarding infrastructure and tools, the system relies on a secure cloud network to manage data backups and security protocols automatically, as the client explicitly requested to offload these maintenance tasks. This infrastructure must implement Secure Sockets Layer (SSL) or Transport Layer Security (TLS) encryption to protect sensitive transmission data, particularly credit card numbers and security codes entered during registration. For internal tools, the system requires a reporting engine capable of tracking user activity and generating logs for the owner. Finally, to satisfy the requirement for offline analysis, the system must include export tools that format reports for compatibility with external software like Microsoft Excel.
