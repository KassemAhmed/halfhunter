Technical Presales is the process by which we create estimates for new projects.

## Overview

The [> Technical Presales Trello board](https://trello.com/b/VDLFPRpQ/technical-presales) is set up to match our sales pipeline in [Base](/Tools_&_Apps/Base), our CRM.

This process has the following phases:

### Scoping

The scope is first broken down in a shared Google Sheet by James or another Ops team member. Sometimes designers and developers are asked to help scope out a project, but not always.

### Estimates

Estimates are then created in the Sheet. These are shared with a client, so keep it professional. When you're asked to estimate on a project, a link to the Sheet will be provided in the description of the card in Trello, along with any background information you need.

We do estimates in terms of hours. You'll be asked to fill in minimum and maximum hours on each task for your area of expertise (branding, design, development, etc.)

Communications and Quality Control estimates are automatically added using a formula of 5% of the subtotal of hours for each.

If you need more information to give an accurate estimate, don't be afraid to ask! If a project is particularly complex, James or an Ops team member will reach out to you to have a call to work on the estimate together.

### Negotiation/Review

Once the estimate is complete, James sends it off to the client for review.

### Paperwork/Scheduling

Once a project reaches this stage, it's almost ready to start. The Ops team puts together paperwork and schedules it into [Forecast](/Tools_&_Apps/Forecast).

### Won

Container for projects we won!

### Lost

Container for projects we lost, for whatever reason. Sometimes, a post-mortem is done on the sales process to see where we went wrong.

## RFPs

We also submit proposals to RFPs from time to time. There's a separate Trello board for [> RFPs](https://trello.com/b/xBmalmLL/rfps) because of the amount of communication they require.

## Creating Estimates

Here's an [example of a completed estimate spreadsheet for InfoSec Resources, a WordPress design and development project](https://docs.google.com/a/thephuse.com/spreadsheet/ccc?key=0Ak6kGttj7U7sdG9Qc2lUVVZfbEtoS3VWN3FkRW45SkE#gid=11).

A couple guidelines when creating estimates in the Technical Presales process

- If it's hard to imagine an estimate for something, it might be too big. Break it out into more granular tasks!
- Always provide a minimum and maximum hours estimate, and give yourself plenty of room on the high end.
- Base estimates off experience. If you ever want to see how long a previous project took, ask James to check Harvest reports!

## Avoiding Technical Debt

When you're quoting on the *development* portion of a project, be sure to pad your estimate quite a bit to account for any technical debt you might inherit (from an existing project). Also give yourself time at the end of a project to lint, hint, and document all the work you did so that any new developer doesn't inherit *your* technical debt. There is more about [technical debt and how to avoid it here](/Our_Process/Process_Phases/Development#Technical_Debt).

## A Checklist for Projects Requiring Integration

**Any project requiring third party integration must complete this checklist during the estimate process.**

Basic points:
1. Is your existing API/software documented? 50 
2. Is your existing API/software subject to change during Phuse's development cycle? 50
3. Is your existing API/software built using a framework? If so, what framework? 30
4. Do we need to write tests for our contribution to your API/software? 40
5. Does your application pass all of its unit tests? 0 (if yes or not applicable) to 10 (if no)
6. What languages occupy your stack? 0 to 30 (depending on Phuse's familiarity)
7. What template engines do you use? 5 hours per template engine
8. Must your API server be set up locally? 30
9. Can your API/software surface content for use in development? If not, this is one of our prerequisites (no hours added)
10. Do we need to use your staging environment or set up our own for you? 5-20
11. How many transpilers are being used? 10 per transpiler (unless we're familiar)

We can then score them and have a consistent basis on which to position our quotes for integration. Each project will be unique, but the numbers above correspond to average development estimates(in hours), and can be used by the dev team to create accurate estimates for these types of projects.

---

Now that we have our estimate in hand and the details taken care of, every new project begins with a [Kickoff Call&#8594;](/Our_Process/Kickoff_Calls).