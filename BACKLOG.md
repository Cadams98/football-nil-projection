# Initial Requirements Backlog

This is a first pass of requirements elicitation for the College Football NIL Projection project, generated with ChatGPT. Requirements may change as the project develops.

**Users:** A project maintainer enters player data; viewers browse projections.

**Priority:** High = needed for the first version; Medium = add if time allows; Low = later extension.

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

| REQ-013 | The system shall record the source and last-updated date of player data, including whether it is sample data. | Data | High | Backlog | REQ-005 |
| REQ-014 | The system shall mark a saved projection as outdated when its player inputs change and allow it to be recalculated. | Functional | High | Backlog | REQ-006, REQ-009 |
| REQ-015 | The maintainer shall be able to import player data from a CSV file using a documented format. | Functional | Medium | Backlog | REQ-004, REQ-005, REQ-013 |
| REQ-016 | Users shall be able to export the currently filtered projection list as a CSV file. | Functional | Medium | Backlog | REQ-008, REQ-009 |
| REQ-017 | The maintainer shall be able to adjust supported factor weights and save a version of the projection formula. | Functional | Low | Backlog | REQ-006, REQ-014 |
| REQ-018 | Users shall be able to preview how changes to a player's statistics or follower count affect the estimate without changing saved player data. | Functional | Low | Backlog | REQ-009, REQ-017 |
| REQ-019 | The system shall ask for confirmation before deleting a player and remove that player's related records after confirmation. | Functional | Medium | Backlog | REQ-001, REQ-005 |
| REQ-020 | Users shall be able to operate dashboard search and filter controls with a keyboard and identify each control through a text label. | Non-functional | Medium | Backlog | REQ-008 |
| REQ-021 | The dashboard shall finish loading and filtering 100 sample players within two seconds in the documented test environment. | Non-functional | Medium | Backlog | REQ-007, REQ-008 |
| REQ-022 | The maintainer shall be able to back up and restore player data and saved projections. | Data | Low | Backlog | REQ-005, REQ-006 |
| REQ-023 | The system shall support account sign-in and sign-out before maintainer tools are deployed publicly. | Functional | Low | Backlog | None |
| REQ-024 | The system shall restrict player and formula changes to authenticated maintainers in the publicly deployed version. | Security | Low | Backlog | REQ-001, REQ-017, REQ-023 |

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

| REQ-013 | A player detail view shows the data source, last-updated date, and a sample-data label when applicable. |
| REQ-014 | Editing an input marks the previous result outdated; recalculation updates the value and clears the outdated label. An outdated result is not presented as current. |
| REQ-015 | A valid sample CSV is imported; an invalid CSV identifies the affected rows and makes no database changes. The import does not silently overwrite existing players. |
| REQ-016 | The exported file contains only the filtered players, with name, school, position, projected annual value, estimate label, and current/outdated status. |
| REQ-017 | A valid weight change creates a new formula version; saved projections retain their original formula version and are marked outdated until recalculated with the new version. |
| REQ-018 | Changing a preview input updates the preview estimate; leaving the preview keeps the saved inputs and projection unchanged. |
| REQ-019 | Canceling preserves the player; confirming removes the player and associated statistics, social data, and saved projections. |
| REQ-020 | A user can reach, operate, and exit every search/filter control with a keyboard, see the focused control, and identify controls from their labels. |
| REQ-021 | For a documented device/browser and dataset of 100 players, five consecutive dashboard loads and filter operations each finish within two seconds. |
| REQ-022 | Restoring a test backup recovers the same player records, inputs, projection values, and formula versions. |
| REQ-023 | Valid credentials allow sign-in, invalid credentials are rejected, and sign-out ends the session. Passwords are handled by an authentication library using secure hashing and are not stored as readable text. |
| REQ-024 | A signed-out user and a viewer account cannot create, edit, or delete records or change weights, including through direct backend requests; a maintainer account can. |

## Release scope

- **First version:** High-priority requirements REQ-001 through REQ-009, plus REQ-013 and REQ-014.
- **If time allows:** Medium-priority requirements for comparisons, sorting, mobile layout, CSV import/export, deletion confirmation, keyboard access, and performance.
- **Later extensions:** Low-priority requirements for configurable weights, what-if previews, backups, accounts, and access control.
- All 24 requirements are proposed outcomes of initial elicitation; their presence in the backlog does not mean every feature must be implemented this semester.
- REQ-023 and REQ-024 become required before exposing maintainer tools publicly. The first version remains a local prototype.

## Assumptions and open questions

- The first version uses sample or manually entered data and one season per player.
- A simple documented formula is sufficient for the prototype; real-world accuracy is not an initial requirement.
- Before REQ-006, decide the factor weights, dollar scale, school factor, and how statistics will be normalized across positions.
- Confirm which positions and statistics the first version will support and which sample dataset will be used.
- Each player receives a unique internal ID; names alone do not identify records. Before CSV import, define the matching policy and required columns.
- Choose the test device/browser before implementing REQ-021.
- Define a backup format that includes formula versions before implementing REQ-022.
- Confirm the authentication library and role setup before implementing REQ-023 and REQ-024.
- Automatic data collection, machine learning, historical projection charts, and real NIL contract tracking are outside the initial scope.
