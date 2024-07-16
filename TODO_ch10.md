*Chapter 10. Recommendations
---
**WORK IN PROGRESS**

Non-core aspects of CONTROL.

# Documentation
* One of the most polarising aspects of software development models, often used to compare Agile and Classical methodologies
* Neither is at the extreme, although proponents of each argue that the other is at the extreme.
* Agile argues for moderate documentation. Classical (UP, Spiral) often takes a risk-centric approach to producing artefacts.

Relies on written communication over impromptu conversations.

//TODO

---
From Vanker:

As such Agile methods promote a paradigm shift in knowledge management strategies (Chandra Misra et al., 2010). From heavy document centric to that of tactile knowledge that resides within the development team (Chandra Misra et al., 2010).
While opponents of Agile methods argue that knowledge is transferred from people to people by writing it on paper, proponents on the other hand argue that “Tacit knowledge cannot be transferred by getting it out of people’s heads and onto paper” (Fowler & Highsmith, 2001: 1). As tacit knowledge does not only represent facts but it also represents the relationships between those facts (Fowler & Highsmith, 2001).
Critics on the other hand have further argued that the emphasis on tacit knowledge has made Agile methods dependent on experts (Turk, France & Rumpe, 2014). Adding to this is the real possibility of corporate memory loss that could inhibit an organisations ability to learn from its collective experience (Rubin & Rubin, 2011; Turk et al., 2014).

The traditionalist approach which emphasises document centeredness is not without its own challenges. Jansen et al., identified a set of challenges af- fecting architectural documentation (Jansen, Avgeriou & van der Ven, 2009):
1. Architectural documentation can be difficult to understand in large and complex systems.
2. A stakeholders understanding of the language and their background may hinder their ability to understand documentation.
3. It may be difficult to locate both formal and informal documentation on large projects.
4. It may be difficult to locate a specific set of knowledge in an archi- tectural documentation.
5. Documentation needs to be updated otherwise stakeholders will lose confidence in its credibility.
---

Documentation serves three sets of audiences, listed here in the order of most apparent to least apparent:

1. Others, present and future.
2. Your future self.
3. Your present self.

* Don't document too soon, before the feature is stabilised
* The best documentation is the kind that doesn't have to be written:
    + Self-documenting code
    + Standard and idiomatic design and coding practices
    + Convention over configuration
* Prefer high-level documentation to low-level. For an explorer who doesn't know where to start, a map of a county is better than a detailed map of one village.
* Written communication, while highly efficient, is not always a substitute for face-to-face interactions.
    + Documentation assumes some level of background knowledge and comprehension (language, technical, etc.) skills on behalf of the audience.
    + In practice, this varies greatly.
    + While documentation can and should make the best attempt at conveying knowledge asynchronously, certain complex concepts or intricate details may require additional explanation that is more effectively conveyed in person.
    + Reading of comprehensive documentation may generate additional follow-up questions, which are sometimes best explained in person. (Especially when the documentation covers these queries adequately but the reader may not be best-equipped to understand it.)
* Some knowledge will invariably remain in tacit form. It is, nonetheless, irresponsible to say that we should accept this as a factor beyond our control. There is more within our control than we care to admit. The question is one of priority. It may not be practical to document everything and do so exhaustively. One must, therefore, choose which aspects of the system should be documented and at what level of detail.
* Documentation does not build relationships. 
    + Interpersonal communication can foster collaboration and even create mentoring opportunities, especially when knowledge transfer flows from more senior and experienced engineers to the juniors. Personal interactions can boost motivation and morale, making team members feel more connected and engaged with the project.
    + Understanding Nuances: Non-verbal cues such as body language, facial expressions, and tone of voice play a significant role in communication and understanding, which are absent in written documentation.
    + Addressing Concerns: Non-verbal signals can also help identify when someone has concerns or is confused, allowing for immediate addressing of issues.
* Trick of not answering questions directly but updating the documentation instead

At minimum, the following should be documented:

* High-level architecture of the system:
    + The main components/subsystems that make up the overarching system and their relationships. Focus on visual representations: consider using diagrams whenever possible, accompanied by text to explain complex aspects.
    + List of technology (programming languages, infrastructure, etc.) used by the system, also identifying which parts of the system use that technology.
    + Functional ownership areas: which teams own (or are responsible for) which components/subsystems.
    + The architectural principles governing the system's evolution.
* Engineering principles (for both the delivery organisation and the individual teams that compose it)
* Team-level coding requirements, standards, and guidelines:
    + Language-specific coding conventions and best practices: style guides, linting rules, etc.
    + Acceptable code coverage level, which may be specified at both the line and branch level.
    + Branching strategies, code review and merge policies.
    + Where applicable, guidelines for selecting and adding new dependencies.
    + Code and API documentation standards or guidelines. For example, "we encourage an API-first approach with OpenAPI 3.0 as the specification language, and Swagger as our interactive documentation tool."
    + Standards for writing integration and performance tests. The latter, in particular, are not frequently practiced by Agile organisations but are required by CONTROL's focus on nonfunctional requirements and its accountability model in general. The expectations on software engineers should thus be documented clearly.
    + Error handling practices.
    + Telemetry standards and guidelines: 
        + What to log and how to structure and organise logs. For example, some teams will format logs using JSON.
        + What should be captured in metrics; e.g., latency, retry rates, error rates, throughput, and queue depth. How should these be organised: whether metrics should be capturing scalar values or histogram-like distributions, and guidance on when one approach might be preferred over another.
        + What sort interactions should have traces associated with them. How traces should be stitched together in a distributed system.
        + Which telemetry libraries are preferred, and whether the team has a preference for auto-instrumentation or hand-crafted production of telemetry.
* Catalogues of components owned by each team and their interactions. These may be entire subsystems.
* Interactions of components (or subsystems) at team boundaries.
* Interface schemas (for both synchronous APIs and asynchronous events or messages).
    + Focus on those schemas that govern cross-team interactions, more so than intra-team.
    + Cross-team interfaces are inherently more stable. Their documentation is less likely to change.
* A deployment view of the complete system:
    + A catalogue of environments; e.g., development, staging, and production.
    + A description of the network topologies and perimeter controls used; e.g., subnets, firewalls, and load-balancers
    + Material differences between environments; e.g., development and staging use lower-spec hardware.
* Documentation of CI/CD pipelines and their development considerations:
    + Database upgrade strategies.
    + Deployment models: e.g., blue-green or rolling.
    + Rollback vs. roll-forward strategies.
* Incident management procedures:
    + Steps to follow during a system outage or security incident. For example, run sheets to help guide fault-finding and application support activities.
    + Who to contact and how to escalate issues.
* Backup and recovery procedures:
    + How and when data is backed up.
    + Steps to recover systems and data after a catastrophic failure.
* Security and compliance guidelines:
    + Data protection policies: How sensitive data is handled, stored, and transmitted.
    + Access control: Procedures for granting and revoking access to systems and data.
    + Best practices for managing sensitive information such as API keys and passwords.
    + Secure coding and logging practices, ensuring that code is secure and free from vulnerabilities.
    + Artefact scanning tooling and processes. This may be defined at both the source code and binary level.
* Onboarding documentation at varying levels:
    + At the organisation level: how do I make use of various corporate systems, email, time-sheeting, and so forth?
    + At the department level: what problems do we solve as a larger group?
    + At the system level: what are we building and where will my contributions fit in?
    + At the team level: how do I become an effective member of my team? A bare-bones guide on how to set up their development environment, access code repositories, and run the components locally.

Note that the detail of the onboarding documentation should be closer to a county map than to a village map. It should have links to more detailed documentation in specific areas. The immediate objective is to get a new team member to become aware to a point that they can discover on their own and ask for directions if necessary.

The above is not meant to be an exhaustive list. 

# Principle-led decision-making
Our approach to decision-making affects the quality of our decisions...

What often happens:

List solution options

Assess pros & cons

Resolve conflicts with the help of a committee

Problem 1: Objectivity of pros and cons
Problem 2: Committee-led design confuses agreement with correctness

A better way…

Involve only those who are genuinely impacted by the decision

Encourage bottom-up decision-making

Don’t look for people with opinions who have no skin in the game

Separate the accountable+responsible from the informed

Follow established principles

Pros/cons are irrelevant if an option contradicts a fundamental principle

Principles occasionally contradict

Principles can be used to reduce the set of options

An opening statement. Introduces principles and explains their importance.

_Our foundational principles are the essential elements of the product and engineering<sup>1</sup> culture. They help form a set of common values and beliefs that influence how we organise ourselves, collaborate, grow, develop sustainable solutions, reinforce behaviour and work with key stakeholders. Culture is a lot more than just a handful of principles, but we won't succeed without them._

><sup>1 </sup>Engineering may include application development, data engineering, quant and analytics, architecture, and infrastructure operations.

(Overarching principles)

### Primacy of principles
Principles are the prevailing decision-making criteria within the organisation.

* An outcome supported by an established principle is favoured over an outcome that is neutral to, or contradicts a principle.
* Sometimes principles may appear contradictory (e.g., security and compliance vs customer experience). Product and engineering compromises will be necessary.
* A robust set of core principles mitigates the challenges of decentralised decision-making.
* Without principles, we will not maintain conceptual integrity and will struggle with consistent and repeatable decision-making.



(Behavioural principles)

### Empowerment of individuals and teams
The technical decision-making process is bottom-up.

* Accountability and decision-making power are inseparable.
* Engineering teams are responsible for local decision-making, delivering their part of the solution in the manner they see fit.
* Responsibility split: the business specifies requirements (incl. non-functional), while the engineering team determines the optimal technology solution within the given constraints.

### Clear ownership demarcation
Teams are responsible for the functionality, security and performance of all components that are wholly or jointly in their purview.

* Where possible and practical, ownership of single responsibility solution components is reduced to single teams.
* Each team is responsible for a specific bounded context, ensuring clear ownership of that part of the system.
* Teams work closely with domain experts to understand and model the business domain.
* Teams are empowered to make technical decisions that best suit the domain requirements.
* Shared solution components (libraries, cross-cutting BFFs, etc.) should have de facto custodians.
* Custodianship extends to the data persisted by the solution components. Those who own stateful components also own the underlying state and are responsible for its quality, integrity and safekeeping.
* Ownership comes with implied warranty.

### Avoid knowledge siloing
Key knowledge should not be concentrated in the minds of the few.

* Within a team, knowledge of specific solution elements must be spread across team members.
* The degree of knowledge redundancy is left to team leads; critical components should be accorded a greater knowledge spread.
* Team members should have an appreciation of the overall system architecture and the responsibilities of peer teams. Team leads will have a broader knowledge than their subordinates.
* A common vocabulary goes a long way both within teams and across teams.

### Avoid centralised communication
Do not delegate communication; bypass middlemen where possible.

* Don't ask your development manager or your friendly architect to have robust conversations with other teams on your behalf.
* Built rapport with your peers, particularly your direct suppliers and customers. (I.e., teams and individuals who depend on your work and whose work you and your team depend on.)

### Permission to be wrong
We don't always get things right nor do we dwell on them.

* Quality is the engineers' prerogative: engineering teams designate, monitor and uphold quality objectives.
* Sometimes quality is intentionally relaxed; for example, for a proof-of-concept, to unblock a downstream team, to expedite feature delivery or to meet a regulatory deadline. In every case, time and resources must be budgeted for follow-up work.
* Sometimes we get things wrong or discover better ways of doing things. We must give ourselves permission to be wrong. The role of the leadership team is to provide a safe space to evolve in.
* We don't throw each other and our stakeholders under the bus. We take responsibility for our actions. If something didn't turn out the way we hoped, excuses like "we were told to get it out quickly" will not do.

### Avoid false alignment
Teams should be aligned internally based on their common objectives; namely, decisions that are essential to meeting those objectives. They shouldn't align to artificial constraints for-the-sake-of, unless these are provably required to achieve our goals.

For example, Engineering teams will be internally aligned to ensure we're all delivering on the one goal of building a market-leading product. They need not align on non-contradictory aspects, for example, technology stacks: the teams use a mixture of JavaScript, Rust, Python and Java. Despite their diversity, each team is effective in their delivery, and their deliverables are carefully aligned to a common goal.

Alignment across disparate teams should be limited to those collaborative areas that genuinely assist all parties in reaching their objectives. Done without due consideration, indiscriminate alignment robs teams of precious time and hurts morale; it does little to aid them in achieving their goals.

### Avoid design by committee
We've made some significant organisational and technology decisions already, and we have more decisions ahead of us. We must ensure that forthcoming decisions adequately support our system in the long term.

It may sound counterintuitive to some, but adding people does not necessarily lead to a better decision. There should be one key decision-maker who preserves the conceptual integrity of the overall system, supported by (and only by) —

* Those who are materially impacted by the decision.
* Those with the relevant subject matter expertise.

### Design and build iteratively
Building a market-leading product is an evolutionary process. By overplanning and overbuilding, we risk venturing down the wrong path while wasting precious time in doing so. 

The challenge is to produce just enough architecture up-front so that design gaps will not haunt us later, but not so much that we dwell in hypothetical scenarios that are unlikely to materialise, and lose track of the tangibles as a result.

* Certain critical design decisions must be made at the outset, as they unlock initial progress and set the foundation for the rest of the system.
* Beware of drawing on assumptions that cannot be validated up-front. Parts of a design can only be fully validated once it is implemented in working software.
* There might be a tendency to provision for features that later turn out to be unneeded. (The YAGNI principle.)
* Work done later can draw upon the skills, experience and wisdom obtained earlier in the project. More of the problem space is uncovered as the work progresses; deferred design decisions can take advantage of these greater learnings.
* The cost of under-design is refactoring down the track. Be prepared for these costs.

### Designs aren't the be-all and end-all
We accept that designs are loose guidelines intended to inform the build process, and deliverables may deviate from the specification within reasonable bounds. There are many uncertainties in the Engineering process and those building the software know their job best.

Ongoing dialogue, trust and mutual respect between the design and delivery teams are favoured over documents and specifications. Engagement starts well before we commence the build and does not end until the product or capability is effectively decommissioned.


(Product principles)

### Build products, not projects
We value long-term commitment over short-term engagement.

* The capabilities we build will serve the business for years and decades. Those involved (engineers, product and experience, designers, etc.) must take a long-term view.
* Some of our most successful competitors would have adopted the product mindset and numerous successful organisations in other industries have done the same.
* Products, unlike projects, don't have a well-defined end date. They evolve in response to market changes and business needs.
* Subject matter expertise takes a long time to build; we cannot afford to shuffle people in and out.

### Product decoupled from CRM
The product is independent of the customer (relationship management) platform.

* We already operate several customer platforms and this number may grow through acquisitions.
* The platforms fulfil distinct needs and must be allowed to evolve separately.
* Product scope is constrained by the customer platform. Where these platforms differ, a dependency on a proprietary (customer platform) capability limits the product's portability. Global products mustn't rely on proprietary/unique capabilities of customer platforms.
* The product's design is decoupled from the nuances of the customer platform as per the (Liskov) substitution principle.

### Robustness over flexibility
Do not bake flexibility into a product's operational configuration unless it is essential or yields a competitive advantage. (Configurability here refers to operational parameters, rather than deployment, localisation, look and feel, content, and so forth.)

* Excessive flexibility complicates product design, implementation and use. And in many cases can lead to improper use.
* Decisions to alter a product's control surface should be based on empirical evidence.
* With time, most elements of the product's operation will be automated. This reduces the need for certain kinds of flexibility down the line.


(Technology principles)

### Commoditise technology
Favour open, standards-compliant, accessible and fungible technology and skills to reduce delivery cost and risk.

* Open-source solutions are preferred over commercial analogues, unless the competitive advantage offered by the latter exceeds their cost.
* Generalised tooling is preferred over niche tooling (languages, frameworks, infrastructure, etc.) unless the latter is essential to fulfil specific functional and/or performance objectives.
* Operational (and other) costs and risks of maintaining prospective technology must be factored into the cost-benefit analysis. For example, an on-premises message broker requires numerous infrastructure personnel that are suitably skilled. This presents a personnel risk.
* Prefer platform/vendor-neutral solutions over platform/vendor-specific solutions. For example, certain serverless solutions (e.g., AWS Lambda), while not without their advantages, may limit our deployment options.
* Control technical diversity. Where a proposed technology is closely interchangeable with existing and the latter is well-supported, prefer the latter. I.e., "new" or "different" not just for the sake of.

### Strongly event-driven
Our system is a substantial producer of data with many internal and external consumers. We have adopted the Event-Driven Architecture paradigm, ensuring that producers are minimally coupled to consumers.

* An event is a notification of something that might be of material significance; it is not a direct instruction to do something. (I.e., not a command.) A consumer is free to interpret and process an event as it chooses.
* Events are complete, correct and timely. Where the producer is a system of record, all material entity updates should be accompanied by the publishing of an event.
* Producers determine the message contract and warrant that all published messages conform to the contract.
* Producers preserve causality by ensuring that the partitioning scheme captures the causal order of events.
* Messages are versioned. Versioning should be non-breaking if possible; breaking versions will require "double publishing" to support legacy consumers.
* Consumers should be idempotent. An event may be received multiple times and should not cause adverse effects on the consumer.

### Infrastructure as code
Favour the management of infrastructure through code instead of manual processes.

* Teams can provision and manage their own infrastructure using code.
* Teams manage the state of their infrastructure, including updates and rollbacks.
* Teams are responsible for the code that defines their infrastructure, ensuring it aligns with their service requirements.
* Code ensures that environments are consistent across different stages of development.


# Patterns and guidelines
//TODO

* While principles are generally stated at a very high level of abstraction, patterns and guidelines tend to be more refined.
    + A principle can be a embodied in one paragraph, yet it could be entirely unambiguous. An example is the "primary of principles" principle, which simply states that all decisions must refer to a principle where one exits.
    + Patterns are reusable solutions to common problems. They offer well-defined, scrutinised, and time-tested instructions that are effective in specific contexts.
    + Guidelines are recommendations or best practices intended to influence how certain tasks should be performed. They are not ready-made solutions, unlike patterns. However, following a guideline should simplify the solutioning process and lead to higher quality (e.g., more robust) solutions.
    + Patterns and guidelines have specific instructions that guide their implementation.
* Unlike principles, patterns and guidelines are rarely mandatory. In some ways, people ought to treat patterns and guidelines as tools in a toolbox. They don't have to use these tools to solve problems, however, they are encouraged to do so where it is practical, to avoid reinventing the wheel, and drive consistency within the engineering organisation. Engineers may deviate from this advice on some occasions, although they may be expected to justify their decision to do so. On the other hand, principles must be followed at all times.
* Many patterns are sourced from the industry and often reflect specific technology choices. For example, object-orientated design patterns apply to specific programming languages.
* Patterns and guidelines can be derived internally, especially for highly niche application domains where industry knowledge is hard to come by and is rarely shared. In many cases, internal patterns and guidelines can form the core intellectual property of an organisation; their leakage is highly undesirable.
* Both patterns and guidelines serve common purposes. They aim improve the overall quality and maintainability of software. They ensure consistency in how problems are solved and tasks are performed across teams and software projects.

Some commonly used patterns include:

* **Repository**: Encapsulate the logic needed to access data sources, making data access easier and more consistent.
* **Circuit breaker**: Prevent an application from repeatedly trying to execute an operation that is likely to fail, allowing it to fail fast and recover gracefully.
* **Command query responsibility segregation (CQRS)**: Separate read and write operations into different models to optimise performance, scalability, and security.
* **Event sourcing**: Store the state of a system as a sequence of events, allowing the state to be reconstructed by replaying these events.
* **Service mesh**: Use a dedicated infrastructure layer for managing service-to-service communication, often involving proxies deployed alongside each service instance.
* **Feature toggle**: Enable or disable specific features or behaviour dynamically without deploying new code.
* **Backpressure**: Manage the flow of data between systems to prevent overwhelming receivers with more data than they can process.
* **Retry**: Automatically retry failed operations a set number of times before giving up.
* **Strangler fig**: Incrementally replace an old system by gradually creating a new system around it, then slowly migrating functionalities.

Patterns will typically offer more than a one-paragraph description. There will be references to problem contexts to which the patterns are ideally suited. Diagrammatic representations will frequently be used. And examples may be provided to guide the pattern's implementation. For example, the _strangler fig_ pattern would //TODO

* How do guidelines differ from patterns?
* Guidelines are more verbose and even more technology- or process-specific.
    - Code review and merging guidelines
    - Telemetry guidelines (covering the structure, organisation and best-practices relating logging, metrics, and traces.)

Regarding off-the-shelf patterns, Architects and Engineering Managers shouldn't assume that just because many patterns are commonly available and easily accessible, their use will be implied within the organisation. It is better to be explicit than to assume that Engineers will wilfully engage in research activities to determine the best tools for the job. (In theory, they will do precisely that. In practice, they don't.) Pick the most useful patterns that relate to your operating context and enrol them into the pattern catalogue. The same is said of guidelines.

# Summary
//TODO

Patterns and guidelines serve different but complementary roles in software development. Patterns provide concrete solutions to specific problems and ensure consistent and efficient problem-solving approaches. Guidelines offer broader recommendations and best practices to improve overall software quality and consistency. Both are essential tools for efficient and predictable software delivery.