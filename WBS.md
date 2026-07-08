# Work Breakdown Structure (WBS)

<!-- markdownlint-configure-file
{
    "MD013": { "tables": false }
}
-->

| **WBS ID** | **Task Name** | **Description** | **Owner** | **Estimated Duration** | **Dependencies** |
| :--------: | :-----------: | :-------------: | :-------: | :-: | :-: |
| :green_circle: **1.0** | **Project Planning** | Overall planning tasks | Project Manager | 6 days | |
| :green_circle: 1.1 | Define Scope | Clarify project boundaries | Business Analyst | 2 days | |
| :green_circle: 1.2 | Identify Stakeholders | List and categorize stakeholders | Business Analyst | 1 day | |
| :green_circle: 1.3 | Develop Charter (v1) | Create initial project charter | Project Manager | 3 days | 1.1, 1.2 |
| :green_circle: **2.0** | **Requirements & Analysis** | High-level requirements work | Business Analyst | 6 days | |
| :green_circle: 2.1 | Scenario Analysis | Review scenario needs & constraints | Business Analyst | 2 days | 1.0 |
| :green_circle: 2.2 | Requirements Draft | Functional + non-functional | Business Analyst | 2 days | 2.1 |
| :green_circle: 2.3 | Use Case Identification | Determine system interactions | Business Analyst | 2 days | 2.2 |
| :green_circle: **3.0** | **System Design** | Basic design tasks | Developer | 2 days | |
| :green_circle: 3.1 | Use Case Architecture Diagram | High-level view of actors & actions | Business Analyst | 1 day | 2.3 |
| :green_circle: 3.2 | Initial System Architecture | UI, backend, DB, network placement | Developer | 3 hours | 3.1 |
| :green_circle: 3.3 | Security Boundaries | Define initial security zones | Developer | 2 hours | 3.2 |
| :black_circle: **4.0** | **Prototype Development** | Early prototype work | Developer, UX/UI Designer | 4 days | |
| :black_circle: 4.1 | UI Wireframes | Simple mockups | UX/UI Designer | 3 days | 3.0 |
| :green_circle: 4.2 | Database Structure Draft | Tables/entities | Developer | 4 hours | 3.2 |
| :black_circle: 4.3 | Workflow Diagram | Basic logic flow | Developer | 4 hours | 3.2 |
| :black_circle: **5.0** | **MVP Development** | Developing the actual application | Developer, UX/UI Designer | 14 days | 4.0 |
| :black_circle: 5.1 | HTML+CSS templates | Translating wireframes to reusable HTML components | UX/UI Designer | 3 days | 4.1 |
| :green_circle: 5.2 | Database Schema | Design the SQL schema for the application | Developer | 5 hours | 4.2 |
| :green_circle: 5.3 | Draft Data | Prepare dummy data to fascilitate development | Developer | 4 hours | 5.2 |
| :black_circle: 5.4 | PostgreSQL container | Construct a docker-compose entry which builds the database server | Developer | 3 hours | 5.2 |
| :black_circle: 5.5 | Python back-end | Build the Flask back-end application that handles the logic and serves JSON APIs | Developer | 5 days | 5.3 |
| :black_circle: 5.6 | Back-end CI/CD | Build a CI/CD pipeline to automate back-end deployment | Developer | 4 hours | 5.5 |
| :black_circle: 5.7 | React.js app | Write the front-end react.js application | Developer | 3 days | 5.1, 5.5 |
| :black_circle: 5.8 | Front-end CI/CD | Build a CI/CD pipeline to automate front-end deployment | Developer | 3 hours | 5.7 |
| :black_circle: **6.0** | **Testing & Review** | Integration + feedback | Tester | 8 days | |
| :black_circle: 6.1 | Test Plan Creation | Define test cases & criteria | Tester | 4 days | 5.0 |
| :black_circle: 6.2 | Integration Testing | Connect components | Tester | 2 days | 6.1 |
| :black_circle: 6.3 | Issue Logging | Bug / issue documentation | Tester | 2 days | 6.2 |
| :black_circle: **7.0** | **Final Output** | Final deliverables | Whole Team | 7 days | |
| :black_circle: 7.1 | Final Documentation | Requirements + diagrams | Business Analyst | 4 days | 6.0 |
| :black_circle: 7.2 | Final Presentation | Project summary | Project Manager | 2 days | 7.1 |
| :black_circle: 7.3 | Final Submission | All required artifacts | Whole Team | 1 day | 7.2 |
