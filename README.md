# 👋 Hi, I'm Dmitriy!

### Junior Manual QA Engineer | AI-Assisted Testing

I am an aspiring QA Engineer who recently completed Manual QA courses at Hillel IT School. I actively practice testing web applications, finding Edge Cases, testing APIs, and working with databases. I am looking for my first Junior QA role where I can apply my skills and grow.

*   📫 Contact me: [Telegram](https://t.me/dmitriywalt) , [LinkedIn](*)
*   🛠 My Stack: Jira, TestRail/Testiny, Postman, DevTools, SQL, Agile/Scrum.

---

## 📁 My Cases & Practical Experience

Click on any folder below to expand the details. (All detailed files will be located in the `cases/` directory).

<details>
<summary>📂 <b>Folder 1: Educational Projects (Hillel IT School)</b></summary>
<br>

Assignments completed during the Manual QA course.

*   **[Requirements Review (Pet-App)](./cases/requirements-review-app-kittens.md)** — Static testing: found 12 logical flaws and ambiguities in the specification.
*   **[Test Design: Pairwise (Rent apartment)](./cases/test-design-pairwise-apartment-rental.md)** — Optimized test coverage for a rental app search form (reduced 72 test cases to 12).
*   **[State Transition Diagram (Craps Game)](./cases/state-transition-craps-game.md)** — Modeled game logic using State Transition testing. Found a critical inconsistency in the requirements (number 12).
*   **[Test Case Design & Traceability(Pet-App)](./cases/test-design-traceability-pet-app.md)** — Designed 27 test cases in TestLaba and built a Requirements Traceability Matrix (RTM) to ensure 100% coverage.
*   **[Checklist & Execution (Craps Game)](./cases/checklist-execution-craps.md)** — Created an 11-section checklist and executed it. Found critical UI/UX bugs on mobile devices.
*   **[Jira Filters & Dashboards](./cases/jira-dashboards-filtering.md)** — Created custom JQL filters and built a visual dashboard with Pie Charts to track bug statuses.
*   **[Checklist Execution & Jira Bug Reporting](./cases/bug-reporting-craps.md)** — Executed an 11-section checklist and logged 3 critical bugs in Jira (validation & game logic issues) with detailed Steps to Reproduce.
*   **[Teamwork & Test Execution (Auto App)](./cases/teamwork-test-execution.md)** — Managed test runs for Main Page, User Profiles, and Guest Profiles. Built a Jira Dashboard to visualize team progress.
*   **[Test Plan (qaAuto App)](./cases/test-plan-qa-auto.md)** — Created a comprehensive Test Plan covering scope, approach, entry/exit criteria, and risk management.
*   **[Full Test Execution & Bug Reporting (qaAuto)](./cases/test-execution-qa-auto.md)** — Executed 49 test cases in TestLaba and logged 15 bugs in Jira (including boundary value validation issues).
*   **[Git Basics & Version Control](./cases/git-basics.md)** — Practiced Git workflows: initialized repos, made commits, created branches, and pushed changes to GitHub.
*   **[HTML Structure & Web Basics](./cases/html-structure-and-Git-Branching.md)** — Created a multi-page "About Me" website using pure HTML5 (no CSS), strictly following the required folder hierarchy and Git branching workflow.
*   **[CSS Styling & Responsive Design](./cases/css-styling.md)** — Enhanced a multi-page website with external CSS3, implemented `id`/`class` targeting for the Box Model, typography, and layout styling.
*   **[API Testing & Automation with Postman](./cases/api-testing-postman.md)** — Developed an end-to-end Postman collection for user lifecycle management (CRUD), utilizing dynamic data generation, environment variables, and JavaScript assertions for JSON validation.
*   **[Database Design & DDL (SQL)](./cases/sql-database-creation.md)** — Designed a relational database schema for a car management system, implemented Primary/Foreign Keys, applied constraints (`NOT NULL`, `UNIQUE`, `DEFAULT`), and populated tables with test data.
*   **[SQL Data Manipulation (DML) & Data Retrieval](./cases/sql-dml-case-study.md)** — Practiced SQL data retrieval using `SELECT`, `WHERE`, `LIKE`, `JOIN`, aggregate functions (`COUNT`, `MAX`), and `GROUP BY`. Analyzed business data, calculated expenses, counted car models and owners, and validated query results.
</details>


<details>
<summary>📂 <b>Folder 2: Real Projects (Volunteer Testing)</b></summary>
<br>

Here are the bugs I found and my QA activities on live projects during volunteer testing.

*   **[Map Markers Testing (Commercial)](./cases/RealProject/map-markers-testing.md)** — Exploratory testing: found a boundary defect allowing marker creation outside the supported service area (anonymized due to NDA).
*   **[Map Markers Filtering (Commercial)](./cases/RealProject/map-filters-testing.md)** — Functional testing: discovered a data isolation bug where utility filters (power/water) displayed unrelated markers.
*   **[Geolocation Retest & UI Drift (Commercial)](./cases/RealProject/geolocation-accuracy-bug.md)** — Cross-platform testing (PC/Ethernet, Mobile/Wi-Fi): found a missing geolocation marker. During the retest of the fix, identified a new UI instability bug (map jitter).
*   **[Marker Cooldown Timer Bug (Commercial)](./cases/RealProject/marker-timer-reset-bug.md)** — Boundary value analysis & Business logic: uncovered a critical flaw where the rate limit timer reset incorrectly and deleted existing user markers (data loss).
*   **[Smoke Test: Marker Creation Blocker (Commercial)](./cases/RealProject/smoke-test-marker-creation-blocked.md)** — Smoke testing: identified a critical blocker that prevented core marker creation, halting further regression testing of the build.
*   **[Point Farming Vulnerability (Commercial)](./cases/RealProject/point-farming-abuse-case.md)** — Abuse case testing: discovered a critical business logic flaw allowing users to infinitely farm points by rapidly creating and deleting markers. Reported and fixed.
*   **[Geospatial Boundary Violation (Commercial)](./cases/RealProject/geospatial-boundary-bug.md)** — Geospatial testing: identified a logic flaw where map markers could be placed outside the designated service area due to incorrect coordinate validation.
</details>

<details>
<summary>📂 <b>Folder 3: SQL & Databases</b></summary>
<br>

*   **[Database Design & DDL (SQL)](./cases/sql-database-creation.md)** — Designed a relational database schema for a car management system, implemented Primary/Foreign Keys, applied constraints (`NOT NULL`, `UNIQUE`, `DEFAULT`), and populated tables with test data.
*   **[SQL Data Manipulation (DML) & Data Retrieval](./cases/sql-dml-case-study.md)** — Practiced SQL data retrieval using `SELECT`, `WHERE`, `LIKE`, `JOIN`, aggregate functions (`COUNT`, `MAX`), and `GROUP BY`. Analyzed business data, calculated expenses, counted car models and owners, and validated query results.

</details>

<details>
<summary>📂 <b>Folder 4: Tools & Test Design</b></summary>
<br>
  
*   **[Test Design: Pairwise (Rent apartment)](./cases/test-design-pairwise-apartment-rental.md)** — Optimized test coverage for a rental app search form (reduced 72 test cases to 12).
*   **[TestLaba](./cases/test-design-traceability-pet-app.md)** — Designed 27 test cases in TestLaba and built a Requirements Traceability Matrix (RTM) to ensure 100% coverage.
*   **[Jira Filters & Dashboards](./cases/jira-dashboards-filtering.md)** — Created custom JQL filters and built a visual dashboard with Pie Charts to track bug statuses.
*   **[API Testing & Automation with Postman](./cases/api-testing-postman.md)** — Developed an end-to-end Postman collection for user lifecycle management (CRUD), utilizing dynamic data generation, environment variables, and JavaScript assertions for JSON validation.
*   **[Test Plan (qaAuto App)](./cases/test-plan-qa-auto.md)** — Created a comprehensive Test Plan covering scope, approach, entry/exit criteria, and risk management.
*   **[Full Test Execution & Bug Reporting (qaAuto)](./cases/test-execution-qa-auto.md)** — Executed 49 test cases in TestLaba and logged 15 bugs in Jira (including boundary value validation issues).
*   **[Git Basics & Version Control](./cases/git-basics.md)** — Practiced Git workflows: initialized repos, made commits, created branches, and pushed changes to GitHub.
*   **[HTML Structure & Web Basics](./cases/html-structure-and-Git-Branching.md)** — Created a multi-page "About Me" website using pure HTML5 (no CSS), strictly following the required folder hierarchy and Git branching workflow.
*   **[Testiny](#)** — Executing test runs and documenting bugs in comments (with video evidence).

</details>

---

## 🧰 Tools & Skills
![Jira](https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=Jira&logoColor=white)
![Testiny](https://img.shields.io/badge/Testiny-3b82f6?style=for-the-badge&logo=testinglibrary&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=Postman&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
