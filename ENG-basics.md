# Engineering Basics

This document helps to ensure that our teams and the software they produce meet our Engineering Practices. As an engineering on a team get started here. 

It doesnt matter if you are a veteran engineering or a begineer. Everyone can benefit by following these guidelines

## Source Control

- [ ] The default target branch is locked.
- [ ] Merges are done through PRs.
- [ ] PRs reference related work items.
- [ ] Commit history is consistent and commit messages are informative (what, why).
- [ ] Consistent branch naming conventions.
- [ ] Clear documentation of repository structure.
- [ ] Secrets are not part of the commit history or made public.

More details on [source control](source-control.md)

## Work Item Tracking

- [ ] All work items are tracked (physical or digital, jira or excel. Doesnt matter what tool).
- [ ] The work is organized to reflect progress and drive engineering activities (swim lanes, feature tags, technology tags).
- [ ] The Dev Lead (+ PO/Others) are responsible for backlog management and refinement.
- [ ] A working agreement is established between team members and customer.


## Testing

- [ ] Unit tests cover the majority of all components (>90% if possible).
- [ ] Integration tests run to test the solution e2e.
- [ ] Testing is a part of Engineering. Test what you build. Write the Test before you build if possible.

More details on [test driven development](http://www.jamesshore.com/v2/books/aoad1/test_driven_development) and [Let's play TDD](http://www.jamesshore.com/v2/projects/lets-play-tdd)
More details on [automated testing](automated-testing.md)

## CI/CD

- [ ] Project runs CI with automated build and test on each PR.
- [ ] Project uses CD to manage deployments to a replica environment before PRs are merged.
- [ ] Main branch is always shippable.

More details on [continuous integration](continuous-integration.md) and [continuous delivery](continuous-delivery.md)

## Security

- [ ] Access is only granted on an as-needed basis
- [ ] Secrets are stored in secured locations and not checked in to code
- [ ] Data is encrypted in transit (and if necessary at rest) and passwords are hashed
- [ ] Is the system split into logical segments with separation of concerns? It should be. This helps limiting security vulnerabilities.
- [ ] Scan your external dependencies

More details on [security](security.md)

## Observability

- [ ] Significant business and functional events are tracked and related metrics collected.
- [ ] Application faults and errors are logged.
- [ ] Health of the system is monitored.
- [ ] The client and server side observability data can be differentiated.
- [ ] Logging configuration can be modified without code changes (eg: verbose mode).
- [ ] [Incoming tracing context](observability.md) is propagated to allow for production issue debugging purposes.
- [ ] GDPR compliance is ensured regarding PII (Personally Identifiable Information). This is good practice even if not in the EU.

More details on [observability](observability.md)

## Design Reviews

- [ ] Process for conducting design reviews is included in the way your team works.
- [ ] Design reviews for each major component of the solution are carried out and documented, including alternatives.
- [ ] Stories and/or PRs link to the design document.
- [ ] Each user story includes a task for design review by default, which is assigned or removed during sprint planning.
- [ ] Project advisors are invited to design reviews or asked to give feedback to the design decisions captured in documentation.
- [ ] Discover all the reviews that the customer's processes require and plan for them.
- [ ] Clear non-functional requirements captured (see [Non-Functional Requirements Guidance](non-functional-requirements-capture-guide.md))

More details on [design reviews](design-reviews.md)

## Code Reviews

- [ ] There is a clear agreement in the team as to function of code reviews.
- [ ] The team has a code review checklist or established process.
- [ ] A minimum number of reviewers (usually 2) for a PR merge is enforced by policy.
- [ ] Linters/Code Analyzers, unit tests and successful builds for PR merges are set up.
- [ ] There is a process to enforce a quick review turnaround.
- [ ] If you are following genuine code pairing, code review is happening as you write code. Consider it as 1 reviewer for policy.
- [ ] No code should go to production without the minimum number of reviewers. 

More details on [code reviews](code-reviews.md)

## Engineering Feedback

- [ ] The team submits feedback on business and technical blockers that prevent project success
- [ ] Suggestions for improvements are incorporated in the solution
- [ ] Feedback is detailed and repeatable
- [ ] Feedback is timely so leadership within or external to the team can action it


## Developer Experience (DevEx)

Developers on the team can:

- [ ] Build/Compile source to verify it is free of syntax errors and compiles.
- [ ] Execute all automated tests (unit, e2e, etc).
- [ ] Start/Launch end-to-end to simulate execution in a deployed environment.
- [ ] Attach a debugger to started solution or running automated tests, set breakpoints, step through code, and inspect variables.
- [ ] Automatically install dependencies by pressing F5 (or equivalent) in their IDE.
- [ ] Use local dev configuration values (i.e. .env, appsettings.development.json).

More details on [developer experience](developer-experience.md)

## Additional Advice for Engineering Leaders

[Building reliable systems](building-for-reliability.md)
[Book List](book-list.md)
[Technical Papers worth reading](technical-papers.md)