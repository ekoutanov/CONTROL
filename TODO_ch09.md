Chapter 9. Maintenance
---
**WORK IN PROGRESS**

A software system is widely considered to be a delivery platform for a business product or a suite of interconnected products. Initially, during the early stages of the build, most changes to a system directly support the delivery of products. They may be of both functional and nonfunctional nature, and CONTROL's requirements-gathering process advocates for both aspects to be represented equally. Almost every change marks a perceptible improvement to the functionality or quality of the system. As the system evolves and matures, however, the engineering effort shifts towards maintenance activities that loosely support the embedded product(s). This chapter explores the main sources of these changes.

>The German word "verschlimmbessern" means to make something worse in an honest but failed attempt to improve it. In English, we call that "software maintenance".

# Technical capabilities
The first hint that capabilities may not be directly supporting a product (feature or quality) was revealed in Chapter 3. The _Terminology_ section defines a technical capability as work that is "not immediately attributable to product needs but supports product delivery indirectly."

One immediate implication of this definition is that a technical capability may not always be chargeable to a specific department or stakeholder group or — to use a more generic term — a "sponsor". On the surface, this may not appear to matter much in small systems that revolve around one stakeholder or a cohesive group of stakeholders. The sole sponsor _should_ ensure the continuity of the entire project; it's in their best interests after all. However, even then in small projects, the business may prioritise product capabilities indefinitely, deferring technical capabilities until their absence begins to threaten the overall project.

Many large software projects are, in reality, ongoing programmes of work that fulfil the needs of several distinct groups of stakeholders in a multidepartmental organisation. The software system becomes a shared platform. The chances of a single sponsor prioritising technical work that benefits everyone are slim. We will revisit this issue in a moment.

The second encounter with technical capabilities occurred in Chapter 5 — example _Z_ — "a large-scale refactoring initiative used to boost the performance of the in-house transactional engine." _Z_ is considered to be a technical capability because it transcends individual products, acting as strategic foundation for the business. By enhancing existing capacity, it acts as a longevity booster for the entire system. In simpler terms, _Z_ lays the groundwork for future development and empowers current products to handle increased demands. While all this is well and good, CONTROL requires capability deliveries to associate with a sponsor. Ultimately, it is the sponsor who ensures that the capability meets the needs of the business and is economically worthwhile.

_Who should sponsor technical capabilities?_

At the highest level, it is the Office of the CTO that owns the organisation's technology vision. The CTO oversees both current operations and future advancements through research and development. By strategically evaluating short-term necessities and long-range goals, the CTO optimises resource allocation (financial and staffing) to ensure technology effectively drives the company towards its objectives.

The CTO is not part of the CONTROL delivery organisation. _How can the CTO make informed decisions at the system level?_

Either an Architect or an Engineering Manager will sponsor a technical capability on behalf of the CTO. The choice of Architect or EM comes down to the scope and span of the capability. 

Smallish capabilities that impact just one Engineering team will be sponsored directly by that team's EM. Recall that each team has a dedicated Technical Roadmap, containing a set of prioritised capabilities required to achieve a technical vision. Many roadmap entries will be straightforward refactoring activities, improvements to the supportability of the system, deprecation of outdated libraries, and so forth. The EM will also fill the role of the Architect and the PO.

Largish capabilities or those that impact multiple Engineering teams will be curated by members of the Architecture team. Once again, the capability definition is sourced from a Technical Roadmap; in this case, the roadmap is scoped to the system and maintained by the Architecture team.

Example _Z_ lacked an Ideation phase. This was purely circumstantial, however. Many technical capabilities can genuinely benefit from a concept-level study. The Technical Roadmap may lack the necessary detail or contain high-risk items with uncertain delivery prospects. A capability's economic benefits may not be entirely apparent at the outline level; they may disappear altogether when the capability is further distilled. Conversely, a capability may be completed quicker than originally budgeted in the roadmap or it may be delivered in discrete chunks. The Ideation phase can answer these questions for technical capabilities as effectively as it can for product capabilities.

In either case — capabilities bound to teams or cross-team capabilities — these lack dedicated business stakeholders or traditional Product Owners. Instead, technical sponsors assume a dual role, acting as both champions and informers. They define the capability in the Ideation and Abstraction phases, and ensure it aligns with business needs and delivers economic value. They accept the capability upon the conclusion of the Construction phase. Crucially, they represent the interests of the CTO in channelling the organisation's technology vision.

Technical sponsors can abort the delivery of a capability at any suitable point. They may equally see the delivery of the capability through to its logical conclusion. In every notable respect, technical sponsors do not differ from business sponsors in the CONTROL model.

The next question is one of resource allocation. _How should we allocate Engineering resources among product and technical capabilities?_

This is a trivial question, as it turns out. Neither the CONTROL process model nor its delivery organisation materially distinguishes between the two capability types<sup>1</sup>. Both the process model and the delivery organisation generalise to deliver capabilities of either type within a unified framework: their delivery involves the same roles and follows the same process steps. To put it differently, _CONTROL is symmetric in the delivery of product and technical capabilities_. Building a software system is not a one-off activity with a well-defined end. The product of this activity is, in a manner of speaking, a living and breathing organism. It needs long-term care and attention for survival. With the symmetry of product and technical capabilities encoded into the model, CONTROL can promote a more sustainable software engineering practice.

><sup>1 </sup>The distinctions are largely in the mapping of roles to individuals. EMs and Architects may act as stakeholders and POs. Moreover, in EM-led capabilities, the EM also doubles as the Architect.

The real issue is not one of _who_ or _how_ will deliver technical capabilities, but rather _when_. The pertinent question is _how should technical capabilities be prioritised relative to product capabilities?_ 

This dilemma is the bane of many engineering organisations. It is a perennial question that gets asked frequently but is rarely answered precisely.

In commercial organisations, product capabilities will generally focus on revenue generation while technical capabilities address revenue protection. Both appear to be important. Should one always take priority or should the priorities change over time? Is it perhaps a complex function of some variables? Can they even be compared?

I strongly advise against any attempts to designate objective measures to discern among product and technical priorities. 

//TODO

# BAU
Business-as-usual activities include routine maintenance activities, bug-fixes, and minor enhancements that bring about small, often barely perceptible changes to the system.

To deem BAU activities as non-product is perhaps inaccurate because some of them can be readily associated with specific product initiatives. Some BAU time and resources will be billable to specific cost centres within the business. These activities are nonetheless classified as maintenance because they are generally accepted to be an implicit element in the continuity of a software system.

BAU activities are generally small and very frequent. They are termed "business as usual" for that reason. They cannot incur the same overhead of planning that is accorded to fully-fledged capability deliveries. They must proceed without extensive stakeholder engagement. Nor should they take time from the PO, Architect, or PE. 

Ideally, only those changes that intersect one Engineering team are termed BAU. This ensures that every BAU activity lands in exactly one team's backlog, where they are triaged by an accountable party — the EM. Conversely, interconnected changes that impact multiple teams must be treated as capabilities and subjected to the rigours of the CONTROL process model.

The EM has an important role to play in BAU. EMs are always accountable for the changes impacting their teams' intellectual assets (e.g., software, documentation, configuration, etc.) and for ensuring their continuity. Therefore, EMs must scrutinise all items appearing in their backlog. Items that appear to be something other than BAU should be referred back to the Product Team, who may choose to instantiate the CONTROL process model in their delivery.

A notable challenge of BAU is its effects on team capacity: namely, interference with conventional capability delivery. This problem is not specific to one methodology; it applies equally in Agile and Classical models, as it does with more a contemporary, accountability-driven method like CONTROL. While BAU items tend to be small on a relative scale, their combined effect is very perceptible, particularly in legacy systems with high accumulations of technical debt. BAU impacts the predictability of software delivery regardless of its treatment. The main difference among methodologies is that Agile generally doesn't distinguish between BAU and conventional capability delivery because predictability is not among its objectives.

It is easy to see that BAU work, particularly operational incidents and other unscheduled activities, directly impacts the people committed to capability delivery. In turn, this affects individual time estimates and overall delivery forecasts. There are only so many ways one can mitigate the effects of BAU:

1. **Separate BAU and delivery resources**: This is the most concrete measure, where Engineering teams are effectively split into BAU and (capability) delivery personnel. People may be rotated so that they take turns at different activities, much like we rotate people on support rosters. The aim is to avoid committing people to delivery unless their time can be dedicated fully. In doing so, the BAU-induced variability can be largely eliminated from the forecasting equation. 
2. **Divide time between BAU and delivery**: In this approach, the same team members address both delivery and BAU concerns but split their time between the two activity types. For example, Friday may be BAU day. This has similar advantages to the first approach in significantly reducing BAU-induced variability from forecasting.
3. **Account for BAU in estimation**: This approach does not attempt to reserve capacity for BAU work; instead, it accounts for the BAU-induced variability in the estimates. For any given team, we can monitor their historical distribution of work between BAU and capability delivery activities and make informed projections for the future. For example, a team's capability delivery capacity may be 85 per cent of their total with a standard deviation of seven per cent. Those metrics could then be reflected

The main drawback of the first approach is its inflexibility. The BAU stream may not be a steady one, in which case those on BAU may need to source extra work elsewhere. (Most likely from the team's Technical Roadmap.) Alternatively, the BAU stream may be heavier than expected, perhaps due to a string of production incidents. In the latter, people committed to delivery may need to be temporarily seconded to BAU duties.

Another challenge with the first approach is that the rotation schedule may not be entirely fair in the short term, in that the people committed to longer capability deliveries may spend less time on BAU duty. This can be leveled in the long run by tracking how much time each team member has spent on BAU and moderating rotations accordingly.

One of the challenges with the second approach is the impact on the delivery squad interactions if the BAU time allotments are not synchronised across teams. Imagine if one team chooses Tuesday for BAU work while another takes Wednesday and the third picks Thursday. Then a delivery squad intersecting those teams will only benefit from close collaboration for two of the five weekdays. For that reason, the time-sharing approach should be implemented consistently throughout the delivery organisation or not at all.

A further problem arises when one allows different teams to have varying amounts of BAU work to get through. The first approach handles this well because each team can rotate its members independently of others. The second approach means over- or under-committing some teams to BAU streams.

The third approach takes a more probabilistic, statistically-derived approach to the problem. It does not eliminate variability but conveys it instead. The main problem with this approach is in educating the stakeholders but it may also be a remedy in disguise. When pressed, people acknowledge that an estimate means something rough and inaccurate, and yet they routinely convert estimates to deadlines. The reason: an estimate is a date and so is a deadline. These appear interchangeable. Adding a variability measure to the estimates may further complicate their comprehension but it may also help signal to the stakeholders that an estimate is not a concrete quantity but a probabilistic value that varies within some range.

>The idea of quoting uncertain estimates has been around since the Program Evaluation and Review Technique (PERT), originally developed by Charles Clark for the United States Navy in 1958 (Miller, 1963).
>
>Among the numerous innovations that underpin most project management frameworks to this day, PERT has gifted us with a simple but effective technique called the _three-point estimation_ method. Given three variables: _a_ = the best-case estimate, _m_ = the most likely estimate, and _b_ = the worst-case estimate, the weighted-average estimate is given by _e_ = (_a_ + 4 _m_ + _b_) / 6. The standard deviation is given by _s_ = (_b_ – _a_) / 6.
>
>The estimators of the method are additive, allowing us to estimate the entire critical path of project by either summing the _e_ and _s_ values of the individual components or by summing the _a_, _b_, and _c_ parameters of the components first and then computing _e_ and _s_ over their sums.
>
>The great thing about the three-point method is that its parameters don't require a statistics major to interpret; they can be understood by virtually anyone. Okay, one needs some mathematical basis to understand the weighted average and standard deviation estimators, _e_ and _s_. However, we don't have to communicate _e_ and _s_ directly. Instead, we can communicate _a_, _m_, and _b_ to the stakeholders and project managers. Most people will have an intuitive understanding of worst-case and best-case estimates, and can circle some dates in their calendars or draw a Gantt chart accordingly. Those who wish to take it a little further can determine _e_ and _s_ over the top, in a manner of speaking, without confusing their less maths-savvy colleagues. These values can then be used to convert the estimates to confidence intervals as follows:
>
>The 68% confidence interval is approximately _e_ ± _s_.
>
>The 90% confidence interval is approximately _e_ ± 1.645 _s_.
>
>The 95% confidence interval is approximately _e_ ± 2 _s_.
>
>The 99.7% confidence interval is approximately _e_ ± 3 _s_.
>
>The three-point method is just one example of estimation based on risk and uncertainty. One can adopt others or communicate some kind of a confidence interval or an uncertainty measure. Either way, stakeholders will come to appreciate the inherently uncertain nature of the estimates.
>
>There is a strong argument that _all_ estimates should be quoted as ranges or distributions. Communicating uncertainty is generally a prudent thing to do, and I fail to see any major drawbacks with this approach. Many authors have corroborated this view (Kravcenko, 2003, McConnell, 2006, Griffiths, 2008, and Erickson, 2023).

Some BAU activities may appear to affect multiple teams but are actually multiple distinct BAU items that stem from a larger, overarching initiative. For example, Bookworm Inc. — a fictional software company — is transitioning from a legacy, on-premises build server to a Cloud-hosted CI/CD platform. Bookworm Inc. has four Engineering teams that have embraced the DevOps model; teams is empowered to evolve their pipelines as they see fit. The change requires each team to adapt its pipeline code within the cut-over period. Is this a cross-team BAU item?

While the CI/CD example of Bookworm Inc. impacts multiple teams, it can be modelled as four separate BAU items linked to the overarching "CI/CD upgrade" initiative. An instance of the BAU item is appended to each team's backlog, where it is assessed by the EM. Since each instance is linked to the overarching activity, there is no need for duplication. Anyone wishing to determine what the activity entails can consult the overarching initiative description. The latter contains, among other things, the cut-over date. This date will be used by the EMs to prioritise work within their teams. Every team within Bookworm Inc. will thus cut over to the new CI/CD platform on their own terms.

BAU items should ideally avoid cross-team coordination. The contrary would deem them something other than "usual". It would also raise questions of accountability, since no person is singly responsible for their delivery. What happens when simple changes to the system require collaboration between two or more teams?

Suppose Bookworm Inc. wants to display the expected supply date for books that are out of stock. It's a straightforward change on the web-based storefront, and the dates are available in the back-end warehouse management system — but their API does not currently expose this. The product team has assigned a very low priority to this request — a nice-to-have, at a stretch. There are two minor changes required: on the storefront, to display the data, and on the back-end API, to expose the data. We consider two approaches that may be used to deliver this change request.

The first approach is to directly leverage CONTROL. The change may be classed as capability delivery, albeit a simple one. It will ideally follow the same process model as any other change. In saying this, we bring to the forefront one of the takeaway themes of Chapter 5: _CONTROL phases can be as lightweight as the team allows them to be_. The Bookworm Inc. enhancement feels like a low-risk activity, so we treat it as such. The CONTROL phases will be largely expedited. The business will rubber-stamp the requirements during the Abstraction phase as they likely instigated the change to begin with. The Elaboration phase is led by a senior member of the storefront team, acting in a PE-like role<sub>2</sub>. Architecture will likely approve the API change proposed casually by the storefront team. Formation is as simple as assigning a ticket to one member from each team and ensuring that valuable context isn't lost. Construction is just completing the tickets at an opportune moment and coordinating the integration. The risks are so low that project tracking is purely by exception — in other words, should some incident occur (e.g., a blocker), the impacted developer will notify the accountable person in the storefront team — the quasi-PE — who will act accordingly to resolve the problem.

><sub>2 </sub>This approach offers a dual benefit. It not only reduces dependence on PEs but also equips employees with the skills needed to progress into more senior roles.

>The convenience of CONTROL's risk-centric approach cannot be overstated. There is no limit to how lightweight phases may be. (Or heavyweight, for matter.) Process is not a religious experience; absolution will not come from going through the motions. The point isn't to create commotion but provide a straightforward framework for orderly decision-making.
>
>The abstract requirements specification and the elaborated design artefacts could be a couple of pages on a wiki. Obtaining stakeholder sign-off may be as simple as sending an email or instant message. In general, any of CONTROL's activities can be downscaled based on risk.

The second approach is to weaken the coupling between the work items and deliver the work independently and asynchronously as conventional BAU. Bookworm Inc. could adopt an API-first approach: define the contracts between the two parties and have them implement the producer and consumer sides of the API contract at their own pace. 

A minor challenge with this approach is the absence of coordination in an otherwise integration-rich activity. In this case, it can be solved without much difficulty. The implementation is straightforward on the producer end and may be deployed at any time; it has no dependencies. The consumer-side implementation will require a mock API endpoint during development, and could use a feature flag to keep the capability disabled until both parties are ready to test. Once both parties are ready, the feature is toggled on in a staging environment. After the behaviour is verified, the feature is toggled on in production.

The second option sidesteps the traditional CONTROL process model, turning a lightly-coordinated activity into an uncoordinated one. Whether the first option should be preferred or the second hinges on several factors:

* **Process maturity**: Those with substantial CONTROL (or similar) experience may find instantiating a lightweight process to be second nature. The CONTROL process model may be instantiated frequently — several times a day, with little ceremony. Some of its phases may take an hour or less. Teams with high process maturity may, therefore, favour CONTROL even for simple cross-team activities. Conversely, less experienced teams may strive to reposition simpler cross-team changes as BAU.
* **Risk**: CONTROL's main purpose is to improve the predictability of software development through a structured, repeatable, and risk-centric approach. Some cross-team deliverables may have a low perceived level of risk or relaxed scheduling constraints, like the Bookworm Inc. case. Note that in this example, like in every cross-team BAU split, there is clear accountability for each of the two deliverables but no overarching accountability. The organisation may be willing to compromise on the timing of the delivery and allow for some rework if the implementation goes sour.
* **Expediency**: We have so far considered discretionary changes. Some changes may be a result of production defects that need urgent attention and expedient remediation, with possible follow-up work to address the problem properly later. Hotfixes and various operational incidents should be treated within the BAU stream, albeit with heightened urgency and increased oversight. The follow-up work should be assessed independently.
* **Degree of coupling**: We have assumed that the overall deliverable may be subdivided and its constituents decoupled. This may not always be possible or feasible. In the latter, the cost of decoupling exceeds the cost of coordination. An example is a breaking API change within a rapidly evolving system that isn't in production, or one operating in an environment with maintenance windows. Ordinarily, API producers would be required to either version their APIs or ensure backward compatibility. This carries a significant cost but in a production environment with little downtime tolerance, this may be the only available avenue. Conversely, in systems where downtime is tolerable, it may be quicker and simpler to coordinate a breaking change across several teams and collectively transition to the next API contract version than to have the teams work to different contract versions.

There is a nonzero upfront cost to instantiating a process model but the benefits are often tangible; it —

* Encourages a unified approach to problem-solving. Unification is generally preferable for securing repeatable outcomes, which is why we have principles — yet another form of unification. There is, however, risk that unification may lead to unquestioned acceptance and robotic thinking<sub>3</sub>. 
* Lets you practice CONTROL so that its use becomes second nature.
* Gives the delivery organisation a chance to experiment with subscale processes and tweak the process model according to their needs.
* Offers senior engineers an opportunity to take on delivery ownership in low-risk, low-pressure environments, so that they may someday take on more challenging projects in PE roles.

><sub>3 </sub>This is yet another reason for strong personal accountability. Even with a polished process, clear goals and priorities, and a jelled team, accountable people are ultimately at the helm. Process is a means to an end; helmsmen may choose to follow it to the letter or deviate entirely without affecting their accountability.

# Chalk outlines
I discourage attempts to devise objective measures to compare product and technical capabilities for the benefit of their prioritisation. I believe such a pathway to be prospectless.

While I acknowledge the possibility of creating complex economic models to objectively compare technical and product initiatives for prioritisation, I believe this approach is unrealistic for most organisations, and many will not come close. Achieving true objectivity through such a model is admissible to a select few. And those who can wield such models probably have the wisdom to acknowledge their uncertainty. In these situations, informed judgment and pragmatism often prove more valuable than striving for a potentially misleading measure. This is precisely the case where a healthy dose of unpretentious subjectivity trumps misguided attempts at objectivity.

Regarding cross-team BAU vs. instantiating a process, I do not strongly advocate one approach over the other here, not least because of the natural bias formed through working in chaotic environments.

CONTROL is not possessive and shouldn't be adopted with zeal. As demonstrated earlier, it doesn't require every deliverable churning through the process "meat grinder", even if the latter can be made arbitrarily low-touch. Personal accountability is, however, a nonnegotiable aspect. An organisation may choose to bypass CONTROL for some activities (due to low perceived risk or other reasons entirely); it nonetheless benefits from much of CONTROL fundamentals. The CONTROL accountability model ensures that even BAU items have a well-defined home and an accountable party.