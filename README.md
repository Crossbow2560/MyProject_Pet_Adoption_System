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

**Actors:** Adoption Applicant, Shelter Staff. Adoption fees are paid at the shelter and are outside the system's scope.

## Repository structure

| Folder | Contents | Status |
|---|---|---|
| [1-RE](1-RE) | [Requirements table](1-RE/Requirements_Table.pdf) ([docx](1-RE/Requirements_Table.docx)) (5 FRs, 2 NFRs) and [RTM](1-RE/RTM.xlsx) | Done |
| [2-Architectural-Diagram](2-Architectural-Diagram) | [Architecture diagram](2-Architectural-Diagram/Architecture_Diagram.png) ([PDF](2-Architectural-Diagram/Architecture_Diagram.pdf)): three-tier web architecture with one service per requirement area | Done |
| [3-Project-Creation](3-Project-Creation) | Jira screenshots: [Kanban board](3-Project-Creation/Kanban_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF), [Scrum backlog and Sprint 1](3-Project-Creation/Scrum_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF) | Done |
| [4-SRS-and-WBS](4-SRS-and-WBS) | [SRS](4-SRS-and-WBS/SRS.pdf) ([docx](4-SRS-and-WBS/SRS.docx)), [UC-02 use-case flow specification](4-SRS-and-WBS/UseCase_Flow_UC02.pdf) ([docx](4-SRS-and-WBS/UseCase_Flow_UC02.docx)), [UC-02 exception flows](4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_Exception_Flow.pdf), [WBS](4-SRS-and-WBS/WBS.xlsx) ([diagram](4-SRS-and-WBS/WBS.png)) | Done |
| [5-GitHub-Copilot](5-GitHub-Copilot) | Copilot-generated code screenshots or repository link | Pending |
| [6-Software-Testing](6-Software-Testing) | [Jira bug tracking board](6-Software-Testing/Bug_Project-NishitDB_PES1UG24CS303-BPS%2357.PDF) | Bug fix and retest pending |
| [7-UML-Diagrams](7-UML-Diagrams) | [Use-case diagram](7-UML-Diagrams/Use_Case_Diagram.png) ([PDF](7-UML-Diagrams/Use_Case_Diagram.pdf)), [activity diagram for UC-02](7-UML-Diagrams/Activity_Diagram.png) ([PDF](7-UML-Diagrams/Activity_Diagram.pdf)) | Done |

## Requirements summary

Full table with type, priority, acceptance criteria and rationale: [1-RE/Requirements_Table.pdf](1-RE/Requirements_Table.pdf). Traceability in both directions: [1-RE/RTM.xlsx](1-RE/RTM.xlsx).

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Staff log vaccination and medical intake records; a complete record with no open quarantine flag makes the animal 'Ready for Adoption' | High |
| FR-002 | Applicants search and filter the pet catalog by species, age, breed and compatibility with children or other pets | Medium |
| FR-003 | Logged-in applicants submit a complete adopter questionnaire for a 'Ready for Adoption' animal (one open application per animal) | High |
| FR-004 | Staff record background checks and move applications through Pending Review → Approved / Rejected → Completed, with one approved application per animal and applicant notifications | High |
| FR-005 | Staff manage foster placements: start date, expected end date (after the start date), caregiver, overdue flagging, and ending a placement to restore the animal's previous status | Medium |
| NFR-001 | Performance & Security: catalog filtering with 95th-percentile response < 200 ms at 200 concurrent users; only public animal fields exposed | Medium |
| NFR-002 | Security & Privacy: login for all non-catalog functions (401); medical and background-check data staff-only, questionnaires visible to staff and their own applicant (403) | High |

Priority basis: High is needed for a safe, working adoption cycle; Medium improves usability or operations but the cycle still works without it.

## Use cases

Diagram: [7-UML-Diagrams/Use_Case_Diagram.png](7-UML-Diagrams/Use_Case_Diagram.png)

| ID | Use case | Actor(s) |
|---|---|---|
| UC-01 | Search & Filter Pets | Adoption Applicant |
| UC-02 | Submit Adoption Application | Adoption Applicant |
| UC-03 | Screen Adopter Questionnaire | Shelter Staff |
| UC-04 | Verify Adopter Background | Included by UC-03 |
| UC-05 | Log Animal Medical Intake | Shelter Staff |
| UC-06 | Manage Foster Placement | Shelter Staff |
| UC-07 | Complete Adoption | Shelter Staff |
| UC-08 | Send Status Notification | Included by UC-07 and UC-09 |
| UC-09 | Decide Application | Shelter Staff |
| UC-10 | Log In | Adoption Applicant, Shelter Staff |
| UC-11 | Place Animal in Quarantine | Extends UC-05 |

Relationships: UC-03 «include» UC-04, UC-09 «include» UC-08, UC-07 «include» UC-08, UC-11 «extend» UC-05 (extension point: the intake examination finds a condition needing isolation).

## Core use case: UC-02 Submit Adoption Application

- **Specification:** [4-SRS-and-WBS/UseCase_Flow_UC02.pdf](4-SRS-and-WBS/UseCase_Flow_UC02.pdf) covers preconditions, postconditions, the 7-step main success scenario and alternate flow 4a (animal no longer available, or a duplicate application).
- **Exception flows:** [4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_Exception_Flow.pdf](4-SRS-and-WBS/PES1UG24CS303_Nishit_DB_Exception_Flow.pdf) covers E1 (invalid or incomplete input) and E2 (system or connectivity failure, with the answers kept as a local browser draft).

## Project management

- Jira epic **"Animal Shelter Adoption System"** with the 7 FR/NFR items as children, plus Stories, Tasks and Subtasks.
- Scrum: native backlog and Sprint 1 with the 7 initial FR/NFR items.
- Kanban: To Do / In Progress / Done board.
- Bug tracking: 5 bugs logged (BUGBPS57-1 to -5), each traced to the requirement it violates in the [RTM](1-RE/RTM.xlsx).
