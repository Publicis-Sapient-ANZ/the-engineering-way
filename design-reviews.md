# Design Reviews

## Table of Contents

- [Goals](#goals)
- [Process](#design-review-process)
- [Measures](#measures)
- [Impact](#impact)
- [Participation](#participation)
- [Facilitation Guidance](#facilitation-guidance)
- [Technical Spike](#technical-spike)

## Goals

- Reduce technical debt for our customers
- Continue to effeciently iterate on design (documentation can go stale)
- Generate useful technical artifacts that can be referenced by future teams and/or customers

Design reviews should not feel like a burden. Design reviews can be easily incorporated into the dev crew process with minimal overhead.

- Only create design reviews when needed. Not every story or task requires a complete design review.
- Leverage this guidance to make changes that best fit in with the team. Every team works differently.
- Leverage subject-matter experts (SMEs) as needed during design reviews. Not every story needs SME or leadership sign-off. Most design reviews can be fully executed within an engineering team.
- Use diagrams to visualize concepts and architecture. Be consistent in your diagram style, tooling and layout.

## Design Review Process

Incorporate design reviews throughout the lifetime of an engagement. As an overall for the project you should have a high level architecture and design document. It Includes technologies, languages & products to complete engagement objective.

### Milestone / Epic Design Review
- Should be considered when an engagement contains multiple milestones or epics
- Design should be more detailed than game plan
- May require unique deployment, security and/or privacy characteristics from other milestones

### Feature/story design review
- Design for complex features or stories
- Will reuse deployment, security and other characteristics defined within high level architecture or milestone
- May require new libraries, OSS or patterns to accomplish goals

### Task design review
- Highly detailed design for a complex tasks with many unknowns
- Will integrate into higher level feature/component designs
- Explicit sessions for this level of design is uncommon on most projects, and happens on the fly between engineers or at code review stage.


## Measures

### Cost of Change

When incorporating design reviews as part of the engineering process, decisions are front-loaded before implementation begins. Making a decision of using Kubernetes instead of traditional hosting at the design phase likely only requires updating documentation. However, making this pivot after implementation has started or after a solution is in use is much more costly.

Are these changes occurring before or after implementation? How large of effort are they typically?

### Reviewer Participation

How many individuals participate across the designs created? Cumulatively if this is a larger number this would indicate a wider contribution of ideas and perspectives. A lower number (i.e. same 2 individuals only on every review) might indicate a limited set of perspectives. Is anyone participating from outside the core development team? Leverage the Capability leads, CoE's, and SMEs in the wider organisation.

### Time To Potential Solutions

How long does it typically take to go from requirements to solution options (multiple)?

There is a healthy balancing act between spending too much or too little time evaluating different potential solutions. Too little time puts higher risk of costly changes required after implementation. Too much time delays target value from being delivered; as well as subsequent features in queue. However, the faster the team can *identify the most critical information necessary to make an informed decision*, the faster value can be provided with lower risk of costly changes down the road.

### Time to Decisions

How long does it take to make a decision on which solution to implement?

There is also a healthy balancing act in supporting a healthy debate while not hindering the team's delivery. The ideal case is for a team to quickly digest the solution options presented, ask questions, and debate before finally reaching quorum on a particular approach. In cases where no quorum can be reached, the person with the most context on the problem (typically story owner) should make the final decision. Prioritize delivering value and learning. Disagree and commit!

Reminder: good decisions are usually made by people closest to the work and context. 

## Impact

- Solutions can be quickly be operated into customer's production environment
- Easier for other dev crews to leverage your teams work
- Easier for engineers to ramp up on projects
- Increase team velocity by front-loading changes and decisions when they cost the least
- Increased team engagement and transparency by soliciting wide reviewer participation

## Participation

### Engineering Crew

The engineering crew should always participate in all design review sessions. Its not just people who are _architects_.

### Domain Experts

Domain experts should participate in design review sessions as needed

- Capability leads for the Domain
- Technical subject-matter experts (SMEs)
- Senior Leadership

## Facilitation Guidance

### Sync Design Reviews via in-person / virtual meetings

Joint meetings with engineering team, subject-matter experts (SMEs) and customer engineers work better for big or critical review sessions.

### Async Design Reviews via Pull-Requests

See the [async design review recipe](async-design-reviews.md) for guidance on facilitating async design reviews. This can be useful for teams that are geographically distributed across different time-zones.

## Technical Spike

A technical spike is most often used for evaluating the impact new technology has on the current implementation. 

From [Wikipedia](<https://en.wikipedia.org/wiki/Spike_(software_development)>)...

A spike can be used in a number of ways:
- As a way to familiarize the team with new hardware or software
- To analyze a problem thoroughly and assist in properly dividing work among separate team members.
- Spike tests can also be used to mitigate future risk, and may uncover additional issues that have escaped notice.

A distinction can be made between technical spikes and functional spikes. The technical spike is used more often for evaluating the impact new technology has on the current implementation. A functional spike is used to determine the interaction with a new feature or implementation.

A techincal spike can also be conducted to de-risk an engagement and increase the team's understanding. In such cases the spike focuses on feasibility of the technology.

Generally the deliverable from a Technical Spike should be a document detailing what was evaluated and the outcome of that evaluation. Be sure to include a section that clearly details why an evaluation is being done and what the outcome of this evaluation should be. 

The goal of a spike should be fact-finding, not decision-making or recommendation. Ideally, the technology spike digs into a number of technical questions and gets answers so that the _broader project team_ can then come back together and agree on an appropriate course forward.

## Design Documentation

- Document and update the architecture design in the project design documentation
- Track and document design decisions in a [decision log](decision-log.md)
- Document decision process in when multiple solutions exist for the given problem, so the rationale followed is clear to future teams and the customer.

Early on in engagements, the team must decide where to land artifacts generated from design reviews.
Typically, we meet the customer where they are at (for example, using their Confluence instance to land documentation if that is their preferred process).
However, similar to storing decision logs, trade studies, etc. in the development repo, there are also large benefits to maintaining design review artifacts in the repo as well.
Usually these artifacts can be further added to root level documentation directory or even at the root of the corresponding project if the repo is monolithic.
In adding them to the project repo, these artifacts must similarly be reviewed in Pull Requests (typically preceding but sometimes accompanying implementation) which allows async review/discussion.
Furthermore, artifacts can then easily link to other sections of the repo and source code files.