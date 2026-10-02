# MyProject_Pet_Adoption_System

**Pet Adoption & Shelter Management System**
Problem Statement #57 | Media, Events & Community — SE Lab 1: Requirements Engineering & UML Use-Case Modelling

| | |
|---|---|
| Student | Nishit D B |
| SRN | PES1UG24CS303 |
| Course | Software Engineering, PES University (Dept. of CSE) |
| Problem statement | [57_SE_Lab1_SE_Problem_Statements.pdf](57_SE_Lab1_SE_Problem_Statements.pdf) |

## About the project

An animal shelter management portal that tracks rescue medical intake histories, screens prospective adopter questionnaires, and manages foster home placement timelines.

**Actors:** Adoption Applicant, Shelter Staff (plus Payment Gateway as an external supporting actor for fee payment).

## Repository structure

| Folder | Contents | Status |
|---|---|---|
| [1-RE](1-RE) | [Requirements table](1-RE/Requirements_Table.docx): 5 FRs and 2 NFRs | Done (RTM pending) |
| [2-Architectural-Diagram](2-Architectural-Diagram) | Architecture diagram | Pending |
| [3-Project-Creation](3-Project-Creation) | Jira screenshots: [Kanban board](3-Project-Creation/Kanban_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF), [Scrum backlog and Sprint 1](3-Project-Creation/Scrum_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF) | Done |
| [4-SRS-and-WBS](4-SRS-and-WBS) | [UC-02 use-case flow specification](4-SRS-and-WBS/UseCase_Flow_UC02.docx), [UC-02 exception flows](4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_%20Exception_Flow.pdf) | SRS and WBS pending |
| [5-GitHub-Copilot](5-GitHub-Copilot) | Copilot-generated code screenshots or repository link | Pending |
| [6-Software-Testing](6-Software-Testing) | [Jira bug tracking board](6-Software-Testing/Bug_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF) | Bug fix and retest pending |
| [7-UML-Diagrams](7-UML-Diagrams) | [Use-case diagram](7-UML-Diagrams/usecase_diagram.pdf) | Activity diagram pending |

## Requirements summary

Full table with type, priority, acceptance criteria and rationale: [1-RE/Requirements_Table.docx](1-RE/Requirements_Table.docx).

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Staff log vaccination and medical intake records; animal status becomes 'Ready for Adoption' | High |
| FR-002 | Applicants search and filter the pet catalog by species, age, breed and compatibility with children or other pets | High |
| FR-003 | Applicants submit an adopter questionnaire linked to a specific animal listing | High |
| FR-004 | Staff review questionnaires, record background/reference checks, and approve or reject applications | High |
| FR-005 | Staff schedule and track foster placements (start date, duration, caregiver) | Medium |
| NFR-001 | Performance & Security: multi-attribute catalog filtering with page response < 200 ms | High |
| NFR-002 | Security: medical-intake and background-check records restricted to authenticated Shelter Staff | High |

## Use cases

Diagram: [7-UML-Diagrams/usecase_diagram.pdf](7-UML-Diagrams/usecase_diagram.pdf)

| ID | Use case | Actor(s) |
|---|---|---|
| UC-01 | Search & Filter Pets | Adoption Applicant |
| UC-02 | Submit Adoption Application | Adoption Applicant |
| UC-03 | Screen Adopter Questionnaire | Shelter Staff |
| UC-04 | Verify Adopter Background | Shelter Staff |
| UC-05 | Log Animal Medical Intake | Shelter Staff |
| UC-06 | Schedule Foster Placement | Shelter Staff |
| UC-07 | Pay Adoption Fee | Adoption Applicant, Payment Gateway |
| UC-08 | Send Status Notification | System |

Relationships: UC-02 «include» UC-03, UC-03 «include» UC-04, UC-07 «extend» UC-02, UC-08 «extend» UC-04.

## Core use case: UC-02 Submit Adoption Application

- **Specification:** [4-SRS-and-WBS/UseCase_Flow_UC02.docx](4-SRS-and-WBS/UseCase_Flow_UC02.docx) covers preconditions, postconditions, the 10-step main success scenario and alternate flow 6a (application rejected).
- **Exception flows:** [4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_ Exception_Flow.pdf](4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_%20Exception_Flow.pdf) covers E1 (invalid or incomplete input) and E2 (system or connectivity failure).

## Project management

- Jira epic **"Animal Shelter Adoption System"** with the 7 FR/NFR items as children, plus Stories, Tasks and Subtasks.
- Scrum: native backlog and Sprint 1 with the 7 initial FR/NFR items.
- Kanban: To Do / In Progress / Done board.
- Bug tracking: 5 bugs logged (BUGBPS57-1 to -5).
