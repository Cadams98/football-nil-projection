# College Football NIL Projection

## What the project does

This project will estimate the potential annual name, image, and likeness (NIL) value of college football players. NIL refers to opportunities for athletes to earn money from uses of their name, image, or likeness, such as endorsements.

The application will organize player profiles, performance statistics, position, school, playing time, and social media follower counts in one place. A basic documented formula will use those factors to produce an estimated dollar value that users can view on a dashboard.

## Purpose and problem

The purpose is to make player information easier to organize and compare when exploring potential NIL opportunities. Rather than requiring a user to combine separate statistics and follower counts manually, the software will present the inputs and a consistent estimate together.

The project will also explain how each selected factor contributes to the result. Its goal is to help users understand the calculation and ask better questions about a player's potential opportunities.

## Who it helps

- **Players:** See which factors contribute to their estimate and identify areas to explore, such as social media presence.
- **Businesses considering sponsorships:** Compare player profiles and estimates as a starting point for further research.
- **Fans and students:** Explore players, compare available information, and understand how the prototype calculates NIL estimates.
- **The project maintainer:** Keep player records organized and update them without rebuilding the entire dataset.

These are intended users of the finished concept; the semester version will demonstrate the core workflow with a small dataset.

## How the software helps

1. The maintainer enters a player's profile, season statistics, and follower count, along with the source and update date.
2. The application validates and saves the information.
3. A documented formula calculates an estimated annual NIL value.
4. Users search and filter the dashboard, then open a player to see the inputs and their contributions.
5. When saved inputs change, the previous projection is marked outdated until it is recalculated.

For example, a user could search for a quarterback, view the player's statistics and follower count, and see how those inputs affect the estimate. Player comparisons and temporary what-if previews could be added later.

## Semester scope

The first version will focus on player profiles, manually entered or sample data, validation, database storage, a basic projection formula, searching, and a dashboard with an explanation of each estimate.

If time allows, I can add comparisons, rankings, mobile layout, CSV import/export, and other usability improvements. Configurable weights, what-if previews, backups, accounts, and access control are later extensions.

Projections are estimates, not verified earnings or guaranteed sponsorship offers. The prototype formula will be chosen and documented during development; its output will not claim to establish a player's actual market value. The initial version will run locally. Authentication and maintainer access controls must be completed before maintainer tools are deployed publicly.

## Requirements backlog

[BACKLOG.md](BACKLOG.md) contains **24 proposed requirements** with IDs, types, priorities, statuses, dependencies, and acceptance criteria. High-priority requirements define the first version, while Medium and Low priorities identify optional improvements and later extensions.

This repository currently contains planning documents. Implementation has not started.

## LLM use

I used ChatGPT to generate an initial requirements backlog from my project idea, with this instruction:

> Create an initial requirements backlog for a semester project that estimates college football NIL values. Keep the scope manageable with manual data entry, player profiles, statistics, a simple projection calculation, and a dashboard. Tag each requirement with an ID, type, priority, status, and dependencies. Include brief acceptance criteria and identify assumptions and open questions.

I then requested an expanded backlog and a clearer explanation of the project:

> Can you add more requirements? Also, please on the read me include what and how the project helps and purpose

## Workflow

I plan to use Kanban with Backlog, Ready, In Progress, and Done columns. I will start with the high-priority requirements and limit work in progress to one task at a time.
