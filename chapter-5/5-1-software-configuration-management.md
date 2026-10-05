# Chapter V: Product Implementation, Validation & Deployment

## 5.1. Software Configuration Management

### 5.1.1. Software Development Environment Configuration

<table>
	<thead>
		<tr>
			<th>Product</th>
			<th>Purpose</th>
			<th>Reference/Download Route</th>
			<th>Category</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Trello</td>
			<td>Used to manage the Sprint Backlogs, assign work-items, and track the status of tasks during the development lifecycle.</td>
			<td><a href="https://trello.com/">trello.com</a></td>
			<td>Project Management</td>
		</tr>
		<tr>
			<td>UXPressia</td>
			<td>Utilized to create and centralize Needfinding artifacts, including User Personas, Empathy Maps, and User Journey Maps.</td>
			<td><a href="https://uxpressia.com/">uxpressia.com</a></td>
			<td>Requirements Management</td>
		</tr>
		<tr>
			<td>Figma</td>
			<td>Used as the primary design tool to develop low-fidelity wireframes, high-fidelity mock-ups, and interactive prototypes.</td>
			<td><a href="https://www.figma.com/">figma.com</a></td>
			<td>Product UX/UI Design</td>
		</tr>
		<tr>
			<td>Structurizr</td>
			<td>Employed to design and visualize the Domain-Driven Software Architecture using the C4 Model (Context, Container, and Component levels).</td>
			<td><a href="https://structurizr.com/">structurizr.com</a></td>
			<td>Software Architecture</td>
		</tr>
		<tr>
			<td>PlantUML</td>
			<td>Used as a Diagram-as-Code tool to generate UML Class Diagrams for Object-Oriented Design and ERD (Entity-Relationship) diagrams for the database.</td>
			<td><a href="https://plantuml.com/">plantuml.com</a></td>
			<td>Software & Database Design</td>
		</tr>
		<tr>
			<td>WebStorm</td>
			<td>The official integrated development environment used by the team to code the Single Page Application (SPA) using HTML5, CSS3, and JavaScript.</td>
			<td><a href="https://www.jetbrains.com/webstorm/">jetbrains.com/webstorm</a></td>
			<td>Software Development</td>
		</tr>
		<tr>
			<td>JetBrains Rider</td>
			<td>The chosen IDE for coding the RESTful Web Services and business logic in C#.</td>
			<td><a href="https://www.jetbrains.com/rider/">jetbrains.com/rider</a></td>
			<td>Software Development</td>
		</tr>
		<tr>
			<td>Vue.js & PrimeVue</td>
			<td>Vue.js is used to build the web application, leveraging PrimeVue as the UI component library based on Material Design standards.</td>
			<td><a href="https://vuejs.org/">vuejs.org</a> / <a href="https://primevue.dev/">primevue.dev</a></td>
			<td>Software Development</td>
		</tr>
		<tr>
			<td>ASP.NET Core (C#)</td>
			<td>Utilized to develop the RESTful API architectural style, integrating Entity Framework Core for data access.</td>
			<td><a href="https://dotnet.microsoft.com/download">dotnet.microsoft.com/download</a></td>
			<td>Software Development</td>
		</tr>
		<tr>
			<td>MySQL Server</td>
			<td>The primary Relational Database Management System (RDBMS) used to persist the domain's bounded context data securely.</td>
			<td><a href="https://www.mysql.com/downloads/">mysql.com/downloads</a></td>
			<td>Software Development</td>
		</tr>
		<tr>
			<td>Swagger (OpenAPI)</td>
			<td>Integrated into the backend to generate interactive and standardized documentation for the RESTful API endpoints.</td>
			<td><a href="https://swagger.io/tools/swagger-ui/">swagger.io/tools/swagger-ui</a></td>
			<td>Software Documentation</td>
		</tr>
		<tr>
			<td>GitHub</td>
			<td>Serves as the central remote repository for version control, applying the GitFlow workflow and Conventional Commits.</td>
			<td><a href="https://github.com/">github.com</a></td>
			<td>Source Code Management</td>
		</tr>
		<tr>
			<td>Firebase</td>
			<td>Used as the cloud hosting service to deploy the static assets and the compiled Vue.js frontend applications quickly and securely.</td>
			<td><a href="https://firebase.google.com/">firebase.google.com</a></td>
			<td>Software Deployment</td>
		</tr>
		<tr>
			<td>Microsoft Azure</td>
			<td>Utilized as the primary cloud provider to deploy the compiled ASP.NET Core Web Services and host the MySQL Server.</td>
			<td><a href="https://azure.microsoft.com/">azure.microsoft.com</a></td>
			<td>Software Deployment</td>
		</tr>
	</tbody>
</table>

### 5.1.2. Source Code Management

**Repositories**

- **Landing Page:** [GitHub](https://github.com/TopGlobals/landing-page)
- **Frontend Web Application:** [GitHub](https://github.com/TopGlobals/frontend)
- **RESTful API Web Services:** 

**GitFlow Workflow**

The team applies the GitFlow branching model to structure and manage the product's development lifecycle. The repository maintains two permanent historical branches:
- `main`: Contains the production-ready code. Commits to this branch only occur when a release is finalized and fully tested.
- `develop`: Serves as the integration branch for all new features. It reflects the latest delivered development changes for the next release.

To manage parallel development, the following supporting branches and naming conventions are utilized:
- **Feature Branches:** Created from `develop` and merged back into `develop` once the feature is complete. 
	- *Convention:* `feature/<short-description>` (e.g., `feature/dashboard`).
- **Release Branches:** Created from `develop` when preparing for a new production release, allowing for minor bug fixes and metadata preparation. Once ready, they are merged into both `main` and `develop`.
	- *Convention:* `release/v<semantic-version>` (e.g., `release/v1.0.0`).

**Semantic Versioning**

Releases and tags are named following the Semantic Versioning 2.0.0 guidelines:
- **MAJOR:** Incompatible API changes or major new product iterations.
- **MINOR:** Added functionality in a backwards-compatible manner.
- **PATCH:** Backwards-compatible bug fixes.

**Conventional Commits**

To maintain a readable and automated project history, all commit messages strictly adhere to the Conventional Commits specification. The structure follows `<type>(<scope>): <description>`:
- `feat:` A new feature for the user.
- `fix:` A bug fix for the user.
- `docs:` Documentation-only changes.
- `style:` Changes that do not affect the meaning of the code (formatting, missing semicolons, etc.).
- `refactor:` A code change that neither fixes a bug nor adds a feature.
- `build:` Changes that affect the build system or external dependencies.
- `chore:` Changes to the build process or auxiliary tools and libraries.

### 5.1.3. Source Code Style Guide & Conventions

...

### 5.1.4. Software Deployment Configuration

...
