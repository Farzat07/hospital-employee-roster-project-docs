# Work Breakdown Structure (WBS)

<!-- markdownlint-configure-file
{
    "MD013": { "tables": false }
}
-->

| **WBS ID** | **Task Name** | **Description** | **Owner** | **Estimated Duration** | **Dependencies** |
| :--------: | :-----------: | :-------------: | :-------: | :-: | :-: |
| **1.0** | **Project Planning** | Overall planning tasks | Project Manager | | |
| 1.1 | Define Scope | Clarify project boundaries | Business Analyst | | |
| 1.2 | Identify Stakeholders | List and categorize stakeholders | Business Analyst | | |
| 1.3 | Develop Charter (v1) | Create initial project charter | Project Manager | | 1.1, 1.2 |
| **2.0** | **Requirements & Analysis** | High-level requirements work | Business Analyst | | |
| 2.1 | Scenario Analysis | Review scenario needs & constraints | | | 1.0 |
| 2.2 | Requirements Draft | Functional + non-functional | | | 2.1 |
| 2.3 | Use Case Identification | Determine system interactions | | | 2.2 |
| **3.0** | **System Design** | Basic design tasks | Developer | | |
| 3.1 | Use Case Architecture Diagram | High-level view of actors & actions | | | 2.3 |
| 3.2 | Initial System Architecture | UI, backend, DB, network placement | Developer | 3 hours | 3.1 |
| 3.3 | Security Boundaries | Define initial security zones | Developer | 2 hours | 3.2 |
| **4.0** | **Prototype Development** | Early prototype work | Developer, UX/UI Designer | | |
| 4.1 | UI Wireframes | Simple mockups | UX/UI Designer | | 3.0 |
| 4.2 | Database Structure Draft | Tables/entities | Developer | 4 hours | 3.2 |
| 4.3 | Workflow Diagram | Basic logic flow | Developer | 4 hours | 3.2 |
| **5.0** | **MVP Development** | Developing the actual application | Developer, UX/UI Designer | | 4.0 |
| 5.1 | HTML+CSS templates | Translating wireframes to reusable HTML components | UX/UI Designer | | 4.1 |
| 5.2 | Database Schema | Design the SQL schema for the application | Developer | 5 hours | 4.2 |
| 5.3 | Draft Data | Prepare dummy data to fascilitate development | Developer | 4 hours | 5.2 |
| 5.4 | PostgreSQL container | Construct a docker-compose entry which builds the database server | Developer | 3 hours | 5.2 |
| 5.5 | Python back-end | Build the Flask back-end application that handles the logic and serves JSON APIs | Developer | 5 days | 5.3 |
| 5.6 | Back-end CI/CD | Build a CI/CD pipeline to automate back-end deployment | Developer | 4 hours | 5.5 |
| 5.7 | React.js app | Write the front-end react.js application | Developer | 3 days | 5.1, 5.5 |
| 5.8 | Front-end CI/CD | Build a CI/CD pipeline to automate front-end deployment | Developer | 3 hours | 5.7 |
| **6.0** | **Testing & Review** | Integration + feedback | Tester | | |
| 6.1 | Test Plan Creation | Define test cases & criteria | Tester | | 4.0 |
| 6.2 | Integration Testing | Connect components | Tester | | 5.1 |
| 6.3 | Issue Logging | Bug / issue documentation | Tester | | 5.2 |
| **7.0** | **Final Output** | Final deliverables | Whole Team | | |
| 7.1 | Final Documentation | Requirements + diagrams | | | 5.0 |
| 7.2 | Final Presentation | Project summary | | | 6.1 |
| 7.3 | Final Submission | All required artifacts | | | 6.2 |
