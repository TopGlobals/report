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

**Bounded Context 2**

<img src="./assets/bounded-context-2.png" alt="Bounded Context 2" style="max-width:100%; height:auto;">

...

### 4.6.2. Software Architecture Context Diagram

...

<img src="./assets/context-diagram.png" alt="Context Diagram" style="max-width:100%; height:auto;">

### 4.6.3. Software Architecture Container Diagram

...

<img src="./assets/container-diagram.png" alt="Container Diagram" style="max-width:100%; height:auto;">

### 4.6.4. Software Architecture Component Diagrams

**Bounded Context 1**

<img src="./assets/component-diagram-1.png" alt="Component Diagram 1" style="max-width:100%; height:auto;">

**Bounded Context 2**

<img src="./assets/component-diagram-2.png" alt="Component Diagram 2" style="max-width:100%; height:auto;">
