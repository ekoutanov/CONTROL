Chapter 9. Maintenance
---
**WORK IN PROGRESS**

A software system is widely considered to be a delivery platform for a business product or a suite of interconnected products. Initially, during the early stages of the build, most changes to a system directly support the delivery of products. They may be of both functional and nonfunctional nature, and CONTROL's requirements-gathering process advocates for both aspects to be represented equally. Almost every change marks a perceptible improvement to the functionality or quality of the system. As the system evolves and matures, however, the engineering effort shifts towards maintenance activities that loosely support the embedded product(s). This chapter explores the main sources of these changes.

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
Business-as-usual activities include routine maintenance activities, bug-fixes, and minor enhancements that bring about small, barely perceptible changes to the system.

To deem BAU activities as non-product is perhaps inaccurate because some of them can be readily associated with specific product initiatives. Some BAU time and resources will be billable to specific cost centres within the business. These activities are nonetheless classified as maintenance because they are generally accepted to be an implicit element in the continuity of a software system.

BAU activities are generally small and very frequent. They are termed "business as usual" for that reason. They cannot incur the same overhead of planning that is accorded to fully-fledged capability deliveries. They must proceed without extensive stakeholder engagement. Nor should they take time from the PO, Architect, or PE. 

Only those changes that intersect one Engineering team may be termed BAU. This ensures that every BAU activity lands in exactly one team's backlog, where they are triaged by an accountable party — the EM. (The relevance of the accountability model will be clarified shortly.) Conversely, interconnected changes that impact multiple teams must be treated as capabilities and subjected to the rigours of the CONTROL process model.

Some BAU activities may appear to affect multiple teams but are actually multiple distinct BAU items that stem from a larger, overarching initiative. For example, Bookworm Inc. — a hypothetical software company — is transitioning from a legacy, on-premises build server to a Cloud-hosted CI/CD platform. Bookworm Inc. has four Engineering teams that have embraced the DevOps model; teams is empowered to evolve their pipelines as they see fit. The change requires each team to adapt its pipeline code within the cut-over period. Is this a cross-team BAU item?

While the CI/CD example of Bookworm Inc. impacts multiple teams, it can be modelled as four separate BAU items linked to the overarching "CI/CD upgrade" initiative. An instance of the BAU item is appended to each team's backlog, where it is assessed by the EM. Since each instance is linked to the overarching activity, there is no need for duplication. Anyone wishing to determine what the activity entails can consult the overarching initiative description. The latter contains, among other things, the cut-over date. This date will be used by the EMs to prioritise work within their teams. Every team within Bookworm Inc. will thus cut over to the new CI/CD platform on their own terms.





BAU items must avoid cross-team coordination. The contrary would deem them something other than "usual". It would also raise questions of accountability, since no person is singly responsible for their delivery. What happens when simple changes to the system require collaboration between two or more teams?

Suppose Bookworm Inc. wants to display the expected supply date for books that are out of stock. It's a straightforward change on the web-based storefront, and the dates are available in the back-end warehouse management system — but their API does not currently expose this. There are two small changes required: on the storefront, to display the data, and on the back-end API, to expose the data.

According to the CONTROL model, the change may be classed as capability delivery, albeit a simple one. It will ideally follow the same process model as any other change. In saying this, we bring to the forefront one of the takeaway themes of Chapter 5: _CONTROL phases can be as lightweight as the team allows them to be_. The Bookworm Inc. enhancement feels like a low-risk activity, so we treat it as such. The CONTROL phases will be largely expedited. The business will rubber-stamp the requirements during the Abstraction phase as they likely instigated the change to begin with. The Elaboration phase is led by a senior member of the storefront team, acting in the PE role<sub>2</sub>. Architecture will likely approve the API change proposed casually by the storefront team. Formation is as simple as assigning a ticket to one member from each team and ensuring that valuable context isn't lost. Construction is just completing the tickets at an opportune moment and coordinating the integration. The risks are so low that project tracking is purely by exception — in other words, should some incident occur (e.g., a blocker), the impacted developer will notify the accountable person in the storefront team — the quasi-PE — who will act accordingly to resolve the problem.

><sub>2 </sub>This approach offers a dual benefit. It not only reduces dependence on PEs but also equips employees with the skills needed to progress into more senior roles.

>The convenience of CONTROL's risk-centric approach cannot be overstated. There is no limit to how lightweight phases may be. (Or heavyweight, for matter.) Process is not a religious experience; absolution will not come from going through the motions. The point isn't to create vacuous commotion but provide a straightforward framework for orderly decision-making.
>
>The abstract requirements specification and the elaborated design artefacts could be a couple of pages on a wiki. Obtaining stakeholder sign-off may be as simple as sending an email or instant message. 

* Unless capacity is reserved up-front, BAU work will interfere with capability delivery. (No different in Agile and Classical.) It is best to budget for BAU allowance during delivery planning, bearing in mind that each team may have a different allowance for BAU.

Downscale activities based on risk.

# Chalk outlines
I discourage attempts to devise objective measures to compare product and technical capabilities for the benefit of their prioritisation. I believe such a pathway to be prospectless.

While I acknowledge the possibility of creating complex economic models to objectively compare technical and product initiatives for prioritisation, I believe this approach is unrealistic for most organisations, and many will not come close. Achieving true objectivity through such a model is admissible to a select few. And those who can wield such models probably have the wisdom to acknowledge their uncertainty. In these situations, informed judgment and pragmatism often prove more valuable than striving for a potentially misleading measure. This is precisely the case where a healthy dose of unpretentious subjectivity trumps misguided attempts at objectivity.