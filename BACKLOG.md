# Initial Requirements Backlog

This is a first pass of requirements elicitation for the College Football NIL Projection project, generated with ChatGPT. Requirements may change as the project develops.

**Users:** A project maintainer enters player data; viewers browse projections.

**Priority:** High = needed for the first version; Medium = add if time allows.

**Dependencies:** Listed requirements must be completed before the dependent requirement can be finished. All requirements currently have Backlog status.

| ID | Requirement | Type | Priority | Status | Dependencies |
|---|---|---|---|---|---|
| REQ-001 | The system shall allow the maintainer to add, edit, and delete player profiles containing name, school, position, and class year. | Functional | High | Backlog | None |
| REQ-002 | The system shall store season performance statistics and playing-time information for each player. | Functional | High | Backlog | REQ-001 |
| REQ-003 | The system shall store a social media follower count for each player. | Functional | High | Backlog | REQ-001 |
| REQ-004 | The system shall reject missing required fields and negative statistics or follower counts. | Functional | High | Backlog | REQ-001, REQ-002, REQ-003 |
| REQ-005 | The system shall preserve player data in a database between application sessions. | Data | High | Backlog | REQ-001, REQ-002, REQ-003 |
| REQ-006 | The system shall calculate an estimated annual NIL dollar value using a documented formula and the selected player factors. | Functional | High | Backlog | REQ-004, REQ-005 |
| REQ-007 | The system shall display a dashboard listing players and their projected NIL values. | Functional | High | Backlog | REQ-006 |
| REQ-008 | Users shall be able to search players by name and filter by school or position. | Functional | High | Backlog | REQ-007 |
| REQ-009 | Each projection shall be labeled as an estimate and show the formula's inputs and contributions. | Functional | High | Backlog | REQ-006 |
| REQ-010 | Users shall be able to compare two players' projections and contributing factors. | Functional | Medium | Backlog | REQ-009 |
| REQ-011 | Users shall be able to sort players from highest to lowest projected NIL value. | Functional | Medium | Backlog | REQ-007 |
| REQ-012 | The dashboard shall remain usable on desktop and mobile screens. | Non-functional | Medium | Backlog | REQ-007 |

## Acceptance criteria

| ID | Completion check |
|---|---|
| REQ-001 | A sample player can be created, edited, and deleted, with changes reflected in the player list. |
| REQ-002 | Season, games played, starts, and selected position-specific statistics can be saved and retrieved for a player. |
| REQ-003 | A nonnegative follower count can be saved and retrieved; zero is allowed. |
| REQ-004 | Invalid entries show a clear error and are not saved. |
| REQ-005 | Saved records remain available after restarting the application. |
| REQ-006 | The same inputs produce the same result, and a sample calculation matches the documented formula. |
| REQ-007 | Each listed player shows a name, school, position, and projected annual dollar value. |
| REQ-008 | A name search and each filter return matching players; no matches show an empty-results message. |
| REQ-009 | A player detail view shows the estimate label, inputs, and contributions that reconcile to the displayed total. |
| REQ-010 | Selecting two players displays their values and contributing factors side by side. |
| REQ-011 | Sorting places a higher projection above a lower one. |
| REQ-012 | At 375-pixel and 1280-pixel widths, search controls and projection values are readable and usable without overlap. |

## Assumptions and open questions

- The first version uses sample or manually entered data and one season per player.
- A simple documented formula is sufficient for the prototype; real-world accuracy is not an initial requirement.
- Before REQ-006, decide the factor weights, dollar scale, school factor, and how statistics will be normalized across positions.
- Confirm which positions and statistics the first version will support and which sample dataset will be used.
- Maintainer access is local for the prototype. Public deployment and account authentication require later requirements.
- Automatic imports, machine learning, and historical projections are outside the first version.
