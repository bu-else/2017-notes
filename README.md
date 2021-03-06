# BU ELSE 2017 - Notes
Lecture notes for the Fall 2017 iteration.

## Overview of course topics

Throughout this course we will cover (and utilize within the context of ongoing projects) a variety of topics, concepts, and techniques. A rough enumeration is provided below.

* Design, development and implementation
  * Identification and assembly of requirements
  * Researching existing libraries, frameworks, and components
    * Choosing an appropriate license
    * Identifying open source components
      * Back-end/server-side
        * Registration/authentication
        * Storage and security
      * Front-end/client-side
        * Paradigms (e.g., MVC)
        * Frameworks
        * Platforms/environments and compatibility
  * Selection of development stack and tools
  * Specification
  * Project management
    * Planning
    * Lifecycle/workflow/team organization paradigms
      * Agile/scrum
  * Documentation
* Evaluation
  * Testing
  * Validation
  * Verification
  * Usability testing (think-aloud, alpha, beta)
  * Continuous integration
* Deployment
  * Adding to open source repositories
  * Posting on content distribution networks
  * Release planning
  * Staging and production environments
  * Phases (alpha, beta, etc.)
  * Continuous deployment
* Maintenance
  * Dependencies and compatibility
  * Updates
  * Feature requests

## Feasibility, requirements, and use cases

### Feasibility

* Usability
* Architecture
* Data
* Security
* Maintenance

### Functional requirements

* **Gathering**: Discuss with the client and end users (or collect via surveys, questionnaires, and so on) to understand their expectations of the software artifact(s) to be built.
* **Organizing**: Prioritize and arrange the requirements in order of importance, urgency, and convenience.
* **Negotiation and discussion**: If requirements are ambiguous or there are some conflicts in requirements of various stakeholders, it is then negotiated and discussed with stakeholders. Requirements may then be prioritized and reasonably compromised.
* **Documentation**: All formal & informal, functional and non-functional requirements are documented and made available for review.

### Non-functional requirements

* Logging
* Storage
* Configuration
* Performance
* Cost
* Interoperability: does it need to work with other services or frameworks
* Flexibility
* Accessibility
* Security
* Disaster recovery

### Use cases

Use cases are another way to organize requirements (grouped by the tasks with which they are associated from a user perspective). Thus, they usually deal with behaviors that are observable to the user. They can be functional or non-functional (e.g., performance).

* General characteristics/guidelines
  * As detailed as possible
  * Not the same as design criteria
  * Concrete actors and actions
  * Rich scenarios (skill level, motivation, condition)
  * Not likely to be exhaustive (focus on the main goal of a user)
  * Preferably few in number
  * Avoid nesting conditions
* Some links of interest
  * [Usability.gov -> Use Cases](https://www.usability.gov/how-to-and-tools/methods/use-cases.html)
  * [Another sample use case](http://tynerblain.com/blog/2007/04/09/sample-use-case-example/)
  * Tips for writing good use cases (ftp://ftp.software.ibm.com/software/rational/web/whitepapers/RAW14023-USEN-00.pdf)

Use cases should more closely match user acceptance or usability tests rather than unit tests.

A possible outline of a use case:
* Brief description
* Actors (primary and secondary)
* Flow of events
  * Basic flow
  * Alternative flows

## Design

There are three design stages for a user-facing software application that can be identified. Sometimes dedicated UI/UX designers take on these tasks.

* Wireframe
  * Low-fidelity representation of the design
  * Main content groups (what is visible)
  * Structure of information (where it appears)
  * User interaction (how it reacts/behaves in response to user actions)
  * Should be done quickly
* Mockup
  * Has visual representation and content
  * Demonstrates functionalities in a static way (need not be interactive)
  * Could include a storyboard-like walkthrough of use cases
  * Sometimes useful to promote idea or gain support to move further
  * Could be an iterative process to gather feedback/changes
* Prototype
  * Looks close to the final product (has visual representation and content)
  * Simulates user interaction (but actions need not be tied to one another)
  * Can be used for usability testing (e.g., a think-aloud study)

One possible tool that can be used for assembling designs during both the wireframe and mockup stages is [Balsamiq](https://balsamiq.com/).

## Notes on mobile development

Existing mobile app development frameworks can be broken up into a number of categories.

* Native
  * Direct access to all features within the OS (Android, iOS, and so on)
  * Effectively need to have two teams work on two different code bases
  * Need to manage synchronization issues between teams
* Cross-platform
  * Use a dedicated cross-platform framework
  * Compilation to native code
    * This may lead to "lowest common demoninator" features
  * Will not have too singificant performance impact
* Hybrid
  * Relies on web technologies (HTML, CSS, JavaScript, TypeScript)
  * Application is essentially running a web browser
  * App displays content that looks native but is a webpage in the browser
  * No native access to device capabilities unless bridges are built
  * Examples include Ionic framework
* Responsive Development
  * A website that renders itself accordingly depending on the device
  
Some factors might play a role in your decision about which type of framework is appropriate for your project.

* If speed is important or need device features, use a native framework
* If there is a tight budget or deadline, use non-native approach
* Assess the community around the framework
  - Absence of community support can be slow you down

## Version control systems and associated workflows

Below, we briefly enumerate some points of interest in the history of version control systems (VCSs).

* Source Code Control System (SCCS)
  * Developed in Bell Labs in 1972
* Revision Control System (RCS)
  * Only works on single files
  * Primarily useful as a locking mechanism
  * Version history can be edited by users
* Concurrent Versions System (CVS)
  * No new releases since 2008
  * Client-server with checkout of complete copies
  * Concurrent work possible; only changes to latest version of a file are accepted
  * Changes require an account and password
  * Support for branches
  * Delta compression to store changes
* SVN
  * Created to be mostly compatible with CVS
  * Support for binary files
  * Still used for some major open source projects
  * Many access control options
  * Support for branches exists (but is cumbersome and used sparingly)
  * Centralized model
    * One of the creator's stated goals: prevent "insecure programmers" from hiding their code
    * Only one copy of the complete history is present
      * Backups of the one central repository must be maintained independently
    * Users only need to keep a copy of files on which they are working
  * User interfaces more mature (and arguably easier to create)
* Git
  * Distributed architecture
    * Multiple redundant repositories
    * Every user has a complete copy of the repository stored locally
  * No centralized access control
    * Users individually decide from whom to merge changes
  * Users have their own local version control at all times
  * Branching is a standard and frequent part of the workflow
  * Merging is a standard and frequent part of the workflow
  * As repositories grow, storage cost of redundant copies can be an issue
    * Large projects sometimes slit their codebase into separate components, each with their own repository
* Mercurial
  * Distributed architecture
  * More user-friendly command line interface
* Version control systems are now being developed for professional target audiences in other domains (music, law, medicine, and so on).

In this course, we will use Git. Git offers a variety of features; its flexibility allows developers to use a variety of different workflows that are all compatible with Git. While there are many options, in this course we will adopt a branch-oriented Git workflow that is similar to the following one: [http://nvie.com/posts/a-successful-git-branching-model/](http://nvie.com/posts/a-successful-git-branching-model/). In addition to the branch management practices described, we will adopt a few additional practices:

  * Feature branch names should always begin with the prefix `feature-`
  * Feature branches should be added to `origin` in order to avoid loss of code
  * Every feature and hotfix branch must have exactly one corresponding GitHub issue.
