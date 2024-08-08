Chapter 10: Principled Decision-Making
===
**WORK IN PROGRESS**

# Into the 'Matrix'
We've all seen this before. The architect<sup>1</sup> is deliberating among several shortlisted solution options. She writes down their pros and cons:

* Solution 1: **API-driven order processing.**
    + **Pro**: Quick to implement, requiring few changes to the existing system.
    + **Con**: Doesn't scale to increased web traffic.
* Solution 2: **Event-driven order processing with broker-side pre-filtering and routing.**
    + **Pro**: Scales to increased loads and has no points of failure.
    + **Pro**: Quick to implement, requiring few changes to the existing system.
    + **Con**: Requires proprietary technology. Cannot be easily deployed on the public Cloud.
* Solution 3: **Event-driven order processing with consumer-side filtering.**
    + **Pro**: Scales to increased loads and has no points of failure.
    + **Pro**: Relies solely on open-source technology.
    + **Con**: High change impact, risking cost blow-outs and late delivery.

<sup>1 </sup>Architects are picked on here because they're responsible for more than their fair share of poor decisions. The example applies equally to all decision-makers.

The benefits and drawbacks of each solution are numerous and substantial; they do not seem to separate the good from the bad. A game of trade-offs is afoot. The architect responds by assigning weights to each factor; these have been gathered through consultation with various stakeholders — business and technical alike. Unsurprisingly, costs and schedules have attracted the most attention, followed by reliability and scalability. One technical stakeholder expressed concerns regarding the potential lock-in effects of adopting proprietary infrastructure. The stakeholders' collective opinions were encoded on a scale of one (least important) to five (most important).

The responses (i.e., the pros and cons) of each solution were also scored on a one—five scale, signifying their contribution to the factor in question, ranging from strongly negative to strongly positive. The weighted average score of each solution was then computed by taking the product of the factors' weights and the response scores and dividing by the number of product terms. The following table presents the weights, response scores, and the results of the calculations.

|Factor                  |Weight|Solution 1<br/>responses|Solution 2<br/>responses|Solution 3<br/>responses|
|:-----------------------|-----:|---------:|---------:|---------:|
|Reliability             |     4|         3|         5|         5|
|Scalability             |     4|         2|         5|         5|
|Cost & schedule impacts |     5|         4|         5|         2|
|Nonproprietary          |     2|         5|         1|         5|
|                        |      |          |          |          |
|**Weighted average**    |      |  **12.5**| **16.75**| **16.25**|

Solution 2 edges out Solution 3, while Solution 1 is obviously a no-go. However, the architect is unconvinced. There is an inkling that despite everyone's best efforts, the outcome is too close to call. So, she spends time elaborating each solution and presents her analysis to the stakeholders, along with her professional recommendation — Solution 2. It is voted in, almost unanimously. In discussing their choice, many panelists again stress the resourcing and scheduling angle.

While the example above is entirely fabricated, it is an incontrovertible fact that a myriad of analogous decision-making challenges bestands practitioners daily. Not just architects and, most certainly, not just technical people. You'll have seen it at work and at home, in the shops, in relationships, and many times over, I'll wager. In making important decisions, our confidence is boosted as the separation among decision options grows. The more the favoured option eclipses its competition on some scale, however subjective or arbitrary, the more comfort is instilled and the stronger the sense of decision integrity. 

When the solutions cannot be separated cleanly, we respond by tweaking. Minor adjustments are made to weights and scores to enhance separability. If that fails, we may revise the criteria entirely; perhaps there are other factors that we failed to consider. There is an infinite number of matrices of factor weights and response scores that yield adequate separation. And yet we only need one such matrix to reach a conclusive decision. With a bit of creativity and determination, it will be found.

It's not always smooth sailing, of course, and our scenario exemplifies this. When all else fails, we abdicate the decision-making responsibility. In other words, we pad out the solution with enough context and hand it over for our stakeholders to decide. And who better to make the final call? They are, after all, maximally impacted by it.

The above technique (sans the abdication part) is called a Weighted Decision Matrix. It is sometimes referred to as the Pugh Matrix, after its inventor — British product designer — Stuart Pugh (1981). It is among the most commonly used structured decision-making frameworks, appearing prominently in fields like Engineering, Information Technology, Product Development, and Project Management.

# The glitch
I'll state this now without any reservations or caveats: The Weighted Decision Matrix approach doesn't work in the real world and never has.

The problem is not with the calculation method, which is mathematically sound and reasonably straightforward. It is with our inherent inability to satisfy the underlying assumptions; namely, that within some margin of error, the factors are complete, the weights are accurate, and the scores are objective. Consider the challenges:

* **Subjectivity of quantification**: Most of the factors being assessed are qualitative. Their quantification is a matter of opinion, and yet their effects are profound. For instance, reducing the "cost and schedule impacts" from five to four would have tied Solutions 2 and 3. Taking it down to three will have crowned Solution 3 as the victor.
* **Incomplete factor selection**: The selection of factors is biased by the analyst. Why was the earlier example limited to four factors? Maybe they were important to her. Maybe she was influenced by her stakeholders. Or maybe she simply overlooked them.
* **Tweaking**: We expect the method to yield an outcome; a tie or a handful of closely matched outcomes will not do. Because the analysts accept the subjectivity of quantification, there are no moral or ethical inhibitors preventing them from tweaking the numbers or moderating these tweaks in any way.
* **Confirmation bias**: Extrapolating from the previous point, we instill comfort into the separability of solutions. A clear and uncontested decision outcome creates instant satisfaction with the process, to the effect that we stop questioning the inputs. We accept the decision and move on. Challenging the inputs would likely muddy the weighted averages, decrease separability, and erode our confidence in the outcome.
* **Illusion of objectivity**: An _a priori_ subjective decision method telegraphs its limitations from the outset. Conversely, a process containing some maths and copious evidence of analysis may appear to stakeholders as objective; in reality it's a cook up.
* **Illusion of precision**: In our example, the weighted averages were precise to four significant figures. The numerical output
* **Assumption of independence**: The calculation is sound only when all factors are independent of each other, which is not always the case. Consider a pair of factors — change impact and maintainability. The former favours simpler solutions that impact fewer areas of an existing system. The latter is also negatively correlated with complexity. A simple solution will therefore score well against both factors, amplifying its score beyond reason; equivalently, complex solutions are doubly penalised. This can be mitigated by vetting factors for correlation<sup>2</sup>.
* **Waste of effort**: Illusion of objectivity doesn't come cheap. Each option must be analysed with enough rigour to permit the quantification of its response scores. Ultimately, one solution will be chosen; the others will be consigned to history.

><sup>2 </sup>Experience suggests that this is often gets neglected. Sadly, there are no 

In summarising the above, I suggest there are two congenital flaws with this method, both unmitigable:

1. **It's irreproducible.** The multiple sources of subjectivity and biases present in the application of the method imply a high likelihood of a pair analysts reaching different outcomes, even if equipped with similar knowledge, skills, and problem context.
2. **It's unstable.** Small changes in response scores and factor weights can lead to radically different outcomes.



# The red pill


Small weighing or scoring changes can swing the outcome from one solution to another. 

While the


While the solution options are entirely contrived, it is easy to imagine similar decisions faced by practitioners around the world. The benefits and drawbacks are numerous and substantial; they do not seem to demarcate the good and the bad solutions.

The architect responds by 



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

>The history of software patterns begins not with computers but with buildings. They come to us from the world of architecture, first described by Christopher Alexander, Sara Ishikawa, and Murray Silverstein in 1977. In their original definition, a pattern is a "recurring solution to a common problem in a given context and system of forces."
>
>Many authors have contributed to the evolution of patterns in software engineering and the definition itself has been reworded more than once. Brad Appleton (1998) defines a design pattern as "a named 'nugget' of insight which conveys the essence of a proven solution to a recurring problem within a certain context amidst competing concerns."

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

Regarding off-the-shelf patterns, Architects and Engineering Managers shouldn't assume that just because many patterns are commonly available and easily accessible, their use will be implied within the organisation. It is better to be explicit than to assume that Engineers will wilfully engage in research activities to determine the best tools for the job. (In theory, they will do precisely that. In practice, they won't.) Pick the most useful patterns that relate to your operating context and enrol them into the pattern catalogue. The same is said of guidelines.

If any pair of principles contradict, it is an indication that one or both are incorrect, or that their interpretation is incorrect.  

# Summary
//TODO

Patterns and guidelines serve different but complementary roles in software development. Patterns provide concrete solutions to specific problems and ensure consistent and efficient problem-solving approaches. Guidelines offer broader recommendations and best practices to improve overall software quality and consistency. Both are essential tools for efficient and predictable software delivery.