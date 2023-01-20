---
title: DevOps
subtitle: This explain how to use DevOps
author: batisa@unhcr.org
tags: [devops]
---

# Diagrams

# Work Item Definitions

## Portfolio Backlog
- **Epic**: An Epic is a large user story that is so big that it is impossible to estimate its effort or even a user story that is too large to fit into a single sprint. Usually, it represents a business initiative to be accomplished.
- **Feature**: A feature represents a shippable software component and reflects a service that fulfills some critical stakeholder needs.
## Requirements Backlog
- **User Story / PBI or Requirements:** A user story is an informal, short requirement (usually three sentences) written from an end user’s perspective by the stakeholders (managers, end-users, project sponsors, etc.). The purpose of the user story is to articulate how a workpiece will deliver a particular value to the software
- **PRIMES Reports:** Refer to the technical specifications for the creation of the a Report or Dashboard
- **Data Correction:** Refer to the technical specification for the execution of the a data correction activity.
- Task: Work items that are SMART (Specific, Measurable, Achievable, Relevant and Time-boxed). Tasks should ideally require less than a day’s worth of work.
## Bug Backlog
- **Bug**. When a bug is founded during the test phase, it is tracked by a bug work item that describes its repro steps, which should provide what you need to reproduce the bug and its behavior.

## Test Backlog
- **Test Plan:** Test Plans works by allowing you to create a container (Test Plan) to group your Test Suites.
- **Test Suites:** A Test Suite is a collection of Test Cases
- **Test Cases:** Represent steps that allow the validation of a requirement 
## Other Backlog
- **Change Request**: Refers to a change request work item used to track all changes that deviate from the original requirement’s baseline.
- **RAID:** The work item is used to describe an event in which outcome varies from the desired result or required a decision. This work item provides fields to define the probability of occurrence, mitigate the impact, and contingency plans for recovery in the event of an occurrence.
- **Impediment or Issue**: Issues (Agile) and impediments (Scrum) are unplanned activities that may block work from getting done


# Iterations
An iteration in agile is a time-box during which development takes place. The duration may vary, usually between 1-4 weeks, and in most cases, it's fixed for the duration of a particular project. A crucial aspect of the agile approach is the underlying assumption that a project is exclusively made of a sequence of iterations, maybe except for a very brief "planning and vision" phase before the development process takes place.

## Iteration Naming Conventions
The iteration are divided into two main paths, and the main path are split into Sprint, MMR, HT
- Central Enhancements
  - Sprint Name (SPRINT XX - YYYY - Name - Major Version Number)
- BAU Support
   - Year
      - Monthly Maintenance Release (MMR - XXX)
      - Hot Fix (HF - Date(MMDD) Hotfix Version Number)
   - Pending CR
   - Pending Bugs
   - Pending Data Corrections
   - Pending Reports

Examples:
- Central Enhancements \ SPRINT 01 - 2022 - Kobo Updates Part 1 - 5.1.0.000
- Central Enhancements \ SPRINT 02 - 2022 - Field Security Profiles Update - 5.2.0.000
- Support \ 2022 \ MMR-001
- Support \ 2022 \ HF \ HF-001
# Areas
You add areas to support your team's trace-ability and security requirements. Use areas to represent logical or physical components, and then create child areas to represent specific features.

Add areas when you have these requirements:

- Filter queries based on a product or feature area
- Organize or group work items by team or sub teams
- Restrict access to work items based on their area.

Each team can create a hierarchy of areas under which the team can organize their backlog items, user stories, requirements, tasks, and bugs.

Avoid creating an area structure that is too complex. You can create areas to partition permissions on work items, but complex trees require significant overhead for permission management. You might find that it's too much work to duplicate the structure and permissions in other projects.

# [Work link types](https://docs.microsoft.com/en-us/azure/devops/boards/queries/link-work-items-support-traceability?view=azure-devops&tabs=browser)
Work link types are system-defined, process-defined, or user-defined (custom). The links listed in the following table are system defined.

Each work link type defines the link labels, topology type, and restrictions that are used when links between work items are constructed. For example, the parent-child link type defines two labels: Parent and Child. The link type also supports a hierarchical or tree topology, and prevents circular references from being created between work items.

<IMG  src="https://docs.microsoft.com/en-us/azure/devops/boards/queries/media/link-type-reference/linkscontrol-work-item-link-types.png?view=azure-devops"  alt="Work item link types, conceptual image"/>

# Test Plan Naming Convention
For the test plans we will follow the following convention
{Type of Release} - {Application Name} - {Year} - {Development Cycle} - {Type of Test}?

- MR: Maintenance Releases
MR - {APP NAME} - {YY} - {DEV CYCLE} - {UAT/RT/ST}
- HF: Hot Fixes
HF - {APP NAME} - {YY} - {DEV CYCLE} - {UAT/RT/ST}
- SP: Sprints
SP - {APP NAME} - {YY} - {DEV CYCLE} - {UAT/RT/ST}
- RP: Reports
RP - {APP NAME} - {YY} - {DEV CYCLE} 
- DC: Data Correction
DC - {APP NAME} - {YY} - {DEV CYCLE}



# Development Hierarchy 

The work items will use the following hierarchy:

- Epic -> Feature -> User Stories -> Tasks / Bugs 
- Epic -> Feature -> Product Backlog Item -> Tasks / Bugs 
- Epic -> Feature -> Requirements -> Tasks / Bugs 
- Epic -> Feature -> DTC Request -> Tasks / Bugs 
- Epic -> Feature -> Report Request -> Tasks / Bugs 
- Epic -> Feature -> Change Request
- Epic -> Feature -> RAID
- Test Plan -> Test Suite -> Test Case

# Communication
Any interaction regarding the work item should be done in the discussion section of the work item, no communication on emails

# Version Naming Convention

For proGres M2C the base in Semantic Versioning 2.0.0
Example: **5.1.1.000 Release 2022 Wave 1**

- **Major Version: 5.X;** this represented any new major development that were release into production.
- **Minor Version: 5.1.X;** this represent the monthly maintenance  that were release into production.
- **Hot Fix Version: 5.1.1.XXX;** this represent a hotfix that were release into production

