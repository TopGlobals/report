## **4.6. Domain-Driven Software Architecture**

This section builds on the Big Picture EventStorming presented in section 2.4 and takes it down to a design level following Domain-Driven Design, until the bounded contexts, aggregates, events, commands and queries of **CryoVigil** are identified. It then presents the software architecture of the solution using the C4 Model in Structurizr, through the Software Architecture Context Diagram, the Software Architecture Container Diagram and the Software Architecture Component Diagrams.

### **4.6.1. Design-Level Event Storming**

At this stage, the team carried out a detailed technical immersion to refine the workflow of **CryoVigil**. Unlike the previous stage, the *Design-Level EventStorming* made it possible to identify not only what happens in the system (**Domain Events**), but also who starts each action (**Actors** and **External Systems**), the intention behind it (**Commands**), the rules that govern the behavior of the software (**Policies**), the information users consult (**Read Models**) and the consistency boundaries that process each command (**Aggregates**).

During a focused design session, the elements were organized following the subdomains of a SaaS platform for laboratory cold chain monitoring. The result is a model of eight bounded contexts: three core contexts that deliver CryoVigil's value proposition by combining thermal telemetry with RFID location traceability, two supporting contexts that sustain the laboratory operation and its regulatory obligations, and three generic contexts common to any SaaS platform. The contexts collaborate through domain events, so each one keeps its own model and ubiquitous language while taking part in end-to-end flows such as detecting a thermal excursion, alerting the on-duty staff and recording the corrective action for audits.


![Design-Level Event Storming](./assets/event-storming.png)
Diagram elaborated in Lucidchart.

### Explanation of the Identified Bounded Contexts

The eight bounded contexts that make up the architecture of the solution are described below:

#### 1. Identity & Access Management (Generic)

Manages who can enter CryoVigil and what each user is allowed to do. Its **User** aggregate processes commands such as Sign Up, Sign In, Enable Two-Factor Authentication, Assign Role and Deactivate Account, emitting events like User Signed Up and Role Assigned. A policy locks any session that stays idle past the timeout, and the Active Sessions read model supports the review of logins for security purposes. Its User Signed Up event triggers the creation of the user's profile in Profiles & Preferences.

| Element | Identified in this context |
|---|---|
| Aggregates | User |
| Commands | Sign Up, Sign In, Enable Two-Factor Authentication, Assign Role, Deactivate Account, Lock Session |
| Domain Events | User Signed Up, User Signed In, Two-Factor Authentication Enabled, Role Assigned, Account Deactivated, Session Locked |
| Queries (Read Models) | Active Sessions |
| Policies | Whenever a session stays idle past the timeout, lock the session |
| Actors / External Systems | Visitor, Lab Personnel, Lab Administrator |

*Related user stories: US04, US31, US32, US40, US41, US42, US43, US45, US46, US48.*

![Bounded Context 1: Identity & Access Management](./assets/bounded-context-1.png)
Diagram elaborated in Lucidchart.

#### 2. Profiles & Preferences (Generic)

Stores how each user prefers to work with the platform. When Identity & Access Management reports that a user signed up, a policy creates a default **Profile**. From then on, users update their personal data, switch the interface language between English (en-US) and Spanish (es-419), configure their alert channels and customize their dashboard layout. Each change emits an event, such as Language Changed or Notification Preferences Updated, that refreshes the User Preferences read model used by the rest of the application.

| Element | Identified in this context |
|---|---|
| Aggregates | Profile |
| Commands | Create Profile, Update Profile, Change Language (en-US / es-419), Configure Notification Channels, Customize Dashboard Layout |
| Domain Events | Profile Created, Profile Updated, Language Changed, Notification Preferences Updated, Dashboard Layout Customized |
| Queries (Read Models) | User Preferences |
| Policies | Whenever a user signs up (User Signed Up, from Identity & Access Management), create a default profile |
| Actors / External Systems | Lab Personnel |

*Related user stories: US30, US36, US38, US44, US47, US50.*

![Bounded Context 2: Profiles & Preferences](./assets/bounded-context-2.png)
Diagram elaborated in Lucidchart.

#### 3. Subscriptions & Billing (Generic)

Handles the commercial relationship between CryoVigil and each laboratory. Visitors consult the Plan Catalog and select a plan according to the volume of assets they need to protect. Laboratory administrators then subscribe, and a policy sends the payment request to the external Payment Gateway. The gateway's response either confirms the payment and activates the **Subscription**, or registers a failed payment that, by policy, suspends it. Administrators can also cancel their subscription at any time.

| Element | Identified in this context |
|---|---|
| Aggregates | Subscription |
| Commands | Select Plan, Subscribe, Request Payment, Confirm Payment, Register Failed Payment, Suspend Subscription, Cancel Subscription |
| Domain Events | Plan Selected, Subscription Requested, Subscription Activated, Payment Failed, Subscription Suspended, Subscription Cancelled |
| Queries (Read Models) | Plan Catalog |
| Policies | Whenever a subscription is requested, request the payment; whenever a payment fails, suspend the subscription |
| Actors / External Systems | Visitor, Lab Administrator, Payment Gateway |

*Related user stories: US02.*

![Bounded Context 3: Subscriptions & Billing](./assets/bounded-context-3.png)
Diagram elaborated in Lucidchart.

#### 4. Laboratory & Asset Management (Supporting)

Models the physical infrastructure that CryoVigil protects. Through the **Laboratory** and **Sensor** aggregates, technical staff register laboratories and their storage units, configure the safe temperature thresholds of each unit, link sensors to them and record sensor calibrations. A daily policy flags every sensor whose calibration is due. Its events feed other contexts: Storage Unit Registered, Sensor Linked and Thresholds Configured keep Cold Chain Monitoring up to date, and Sensor Calibrated is logged by Compliance & Audit. The Laboratory Directory read model supports searching and filtering laboratories.

| Element | Identified in this context |
|---|---|
| Aggregates | Laboratory, Sensor |
| Commands | Register Laboratory, Register Storage Unit, Configure Temperature Thresholds, Link Sensor to Storage Unit, Calibrate Sensor, Flag Calibration Due |
| Domain Events | Laboratory Registered, Storage Unit Registered, Thresholds Configured, Sensor Linked, Sensor Calibrated, Calibration Due Flagged |
| Queries (Read Models) | Laboratory Directory |
| Policies | Every day, whenever a sensor calibration is due, flag the sensor |
| Actors / External Systems | Technical Staff |

*Related user stories: US11, US12, US13, US14, US20, US21, US29, US33.*

![Bounded Context 4: Laboratory & Asset Management](./assets/bounded-context-4.png)
Diagram elaborated in Lucidchart.