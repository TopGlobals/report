## **4.7. Software Object-Oriented Design**

This section presents the object-oriented design of the domain layer of CryoVigil's RESTful API, with a higher level of detail about how the components of each bounded context are implemented. The diagrams apply the tactical patterns of Domain-Driven Design (aggregate roots, entities, value objects, domain events and repositories) and follow the C# Coding Conventions: PascalCase names for types, properties and methods, and C# types such as `Guid`, `string`, `bool`, `DateTime`, `TimeSpan` and `decimal`. Every member shows its scope: the state of aggregate roots and entities is private and can only change through public methods that enforce the business rules; value objects and domain events expose public immutable properties; and aggregate roots and entities declare a protected parameterless constructor required by Entity Framework Core. Relationships are named and include their direction and multiplicity.

### **4.7.1. Class Diagrams**

CryoVigil's class diagram represents the static structure of the domain, detailing its fundamental types, their attributes, their behavior (methods) and the relationships that support the business logic. The design is organized following the boundaries of the bounded contexts identified in the Design-Level EventStorming, so that the technical implementation respects the ubiquitous language of each context.

The following class diagram has been designed applying the principles of Domain-Driven Design to model the business core of CryoVigil. Unlike a traditional data model (CRUD), it reflects the behavior and rules of a mission-critical monitoring system. The architecture is divided into highly decoupled bounded contexts that refer to each other by identifier and communicate through domain events. It makes a clear distinction between Aggregate Roots (which guarantee consistency), Entities (objects with an identity over time), Value Objects (immutable objects that describe characteristics), Domain Events (facts that other contexts react to) and Interfaces (the persistence contracts defined by the domain). The integrated diagram shows the domain model of all contexts, and the diagrams of each bounded context add their repository interfaces.

![Class Diagram](./assets/class-diagram.png)
Diagram elaborated in PlantUML.

#### Identity & Access Management

This context is responsible for access control. Its aggregate root, `User`, keeps its credentials and security state private (email, password hash, account status, two-factor authentication, failed sign-in attempts and password expiration) and exposes operations to register failed sign-ins, enable two-factor authentication, assign roles, lock sessions, deactivate the account and link the external identity used for corporate single sign-on. `Session` entities support the inactivity timeout through `IsIdle`, `ExternalIdentity` entities store the provider and subject of each corporate identity, and the `Role` value object groups the permissions of each `RoleType`. When a user signs up, the aggregate publishes `UserSignedUp`. The `IUserRepository` interface extends `IBaseRepository<User>` with searches by email and by external identity.

![Class Diagram: Identity & Access Management](./assets/class-diagram-1.png)
Diagram elaborated in PlantUML.

#### Profiles & Preferences

This context stores how each user prefers to work with the platform. Its aggregate root, `Profile`, references its user by `UserId` and manages the personal data, the interface `Language` (English `EnUs` or Spanish `Es419`), the `UiTheme` (including a high-contrast theme for accessibility), the `NotificationPreferences` value object that defines the alert channels and summary frequency, and the `DashboardLayout` value object with the widgets chosen by the user. The `IProfileRepository` interface finds the profile that belongs to a user.

![Class Diagram: Profiles & Preferences](./assets/class-diagram-2.png)
Diagram elaborated in PlantUML.

#### Subscriptions & Billing

This context models the commercial relationship with each laboratory. Its aggregate root, `Subscription`, follows a `Plan` value object that defines the plan type, the monthly price as `Money` and the maximum number of storage units and sensors covered, and is paid through `Payment` entities that can be confirmed or failed according to the Payment Gateway's response. The subscription moves through the `Pending`, `Active`, `Suspended` and `Cancelled` states. The `ISubscriptionRepository` interface finds the active subscription of an administrator and the subscription that matches a gateway reference.

![Class Diagram: Subscriptions & Billing](./assets/class-diagram-3.png)
Diagram elaborated in PlantUML.

#### Laboratory & Asset Management

This is the structural context of the domain. The aggregate root `Laboratory` contains its `StorageUnit` entities, each with its safe temperature range and divided into `Compartment` entities where biological assets are stored. `Sensor` is a separate aggregate root because it has its own lifecycle: it is linked to a storage unit by identifier, keeps its `CalibrationRecord` history and can be flagged when its calibration is due. The context publishes `StorageUnitRegistered`, `ThresholdsConfigured`, `SensorLinked` and `SensorCalibrated`, which keep Cold Chain Monitoring and Compliance & Audit up to date. The `ILaboratoryRepository` and `ISensorRepository` interfaces add searches by name, by serial number and for sensors with a calibration due.

![Class Diagram: Laboratory & Asset Management](./assets/class-diagram-4.png)
Diagram elaborated in PlantUML.

#### Cold Chain Monitoring

The telemetry engine of CryoVigil. Its aggregate root, `MonitoredStorageUnit`, is this context's own model of a storage unit: it keeps a copy of the safe range, the current `ThermalStatus` and the identifiers of its sensors. It records each `TelemetryReading`, discarding physically impossible values through `IsPhysicallyPossible`, and keeps a `TemperatureTrend` value object that detects when the temperature approaches a limit. From these rules it publishes `ThermalExcursionDetected` and `PreventiveTrendDetected`, which alert the rest of the system. The `IMonitoredStorageUnitRepository` interface finds a monitored unit by storage unit or by sensor.

![Class Diagram: Cold Chain Monitoring](./assets/class-diagram-5.png)
Diagram elaborated in PlantUML.



