Chapter 11. Documentation
---
**WORK IN PROGRESS**

//TODO intro

# The dividing line
The generation of documentation, as well as other non-executable artefacts associated with software, is among the most polarising aspects of software development methods, often used to compare Classical and Agile methodologies. Seemingly, one inundates developers with documentation while the other throws documentation out of the window.

Neither claim is true in its entirety. Many Classical methods take a risk-centric approach to elaborating artefacts of all forms, especially documentation. This approach is advocated heavily in both the Unified Process (and its variants) and Boehm's Spiral model. At the opposing end, Agile embraces documentation but, according to Highsmith, "not hundreds of pages of never-maintained and rarely-used tomes." (Beck et al., 2001.) Each approach tries to strike a balance that works for the _kinds of problems it aims to solve_.

Since practice has a tendency to diverge from theory, this point remains a scorched battleground. In practice, many method adopters avoid independent thought and choose to follow the herd instead, taking on the most commanding of dogmas. This further intensifies the polarisation: proponents of a method will gravitate towards the closest extremity in attempt to distance themselves from their ideological opposition. A three-year study into the adoption and tailoring of Agile methods in Intel highlighted inordinate emphasis on working software over comprehensive documentation, making it harder to scale Agile teams and maintain the software in the long run (Fitzgerald, Hartnett, & Conboy, 2006). Equivalently, many plan-driven adopters have disadvantaged themselves by taking the opposing stance, allowing documentation bureaucracy to stand in the way of progress<sup>1</sup>.

><sup>1 </sup>Sadly, the overwhelming majority of empirical studies compare Agile exclusively to Waterfall, making worthwhile comparisons with the broader class of Classical methodology difficult if not impossible.

# The many values of documenting
In Chapter 9, we considered software maintenance activities and their importance in their long-term support of software production. If one treats documentation purely as a production activity, its value relative to writing code is minuscule. Documentation doesn't compile or execute; at best, it might assist the end-user in navigating an unintuitive product (a problem in its own right) or help onboard a new starter. Is documentation, therefore, a grandiose waste of time? 

Not quite. The above assumes that the cost of software production dominates the total cost of ownership. Is that really the case?

According to Robert Glass (2002), maintenance typically accounts for 60 per cent of overall software costs. Studies by Lientz and Swanson (1980) have placed this figure at between 60 and 80 per cent. Thomas Pigoski (1996) has reported that maintenance can consume up to 90 per cent of the total cost of software. The precise ratio depends largely on the type of software project but we can safely assume that it will be north of 60 per cent for most projects. Furthermore, the longer the projected lifespan of a software system, the greater this ratio.

So, the table turns once documentation is recognised as an essential maintenance activity. Few paragraphs of concise documentation will arguably generate more long-term value than the source code of an average-sized function. Documentation of the stable parts of the system will also pay greater dividends compared to that of the fast-changing parts. 

Regardless of one's stance on the working software vs. documentation, the latter has incontrovertible long-term value. The question is not whether one should be preferred over another, but one of cost and resulting value. As we routinely question the amount of code one needs to solve a product problem — avoiding gold-plating and so forth, we should also challenge how much documentation one needs to solve a future maintenance problem. Sadly, there is no objective measure. We may attempt to position documentation within some risk framework but the prescribed effort will remain a largely subjective measure. So, what to do?

There is no good answer, just more questions. Consider the documentation's intended audience. It may be one of three distinct groups, listed here in the order of most apparent to least apparent.

1. Others, present and future.
2. Your future self.
3. Your present self.

The first audience group is one that most practitioners imagine when they begin writing documentation (or commission others for this task). We believe in the existence of some tacit knowledge that mustn't be withheld indefinitely; it must be shared for the continuity of the system. Presumably, it comprises nuanced insights that are apparent to the select minority but opaque to others. In the extreme case, that minority is the documentation's sole would-be author. The extreme case further compels the author to share their insights with others.

Software tends to accrue complexity as it evolves. On the other hand, the use of design patterns, off-the-shelf components, standards, conventions, and self-documenting elements, neutralises much of that complexity. The deliberation of what to document (and to what extent) becomes largely a function of separating the types of complexities that can be reasonably reconstructed by a trained professional from those that require a specific set of insights and context. In the former, given the same problem, most will come up with a similar solution or, in the worst case, identify the link between the presented solution and the problem. In the latter, most will fail to establish the link, let alone reconstruct an equivalent solution. It is specifically the latter case that benefits from documentation. Documenting the former is largely worthless; the latter, essential.

Naturally, there are risks with this thinking. The distinction between the cases is largely subjective and draws on one's own skills and experience; what is obvious to us is may not be to others. Employing oneself as a filter of one's own product is unwise. Donald Norman in the Design of Everyday Things stresses this very point. Nonetheless, some assumptions must be made to avoid wastage. Why not ask our peers? Exercises like code reviews and walkthroughs can be useful in distinguishing the obvious from the obscure. If our colleagues struggle understanding something "obvious" but do not otherwise contend the solution, it may be an indication of obscurity. It may also be that they lack the necessary skills. Either way, one must reorganise the solution or improve the documentation, or both in some cases.

The second audience group is what the most experienced and battle-hardened practitioners consider when contemplating documentation. They implicitly accept that things that appear obvious today may not be so in as little as three-months time. They imagine a conversation between their present and future selves, speculating over the sorts of questions that the future-they may ask. Human memory erodes with time and age often plays a cruel joke on us. With experience (and age) comes a degree of contempt for one's own ability to recall complex concepts.

Such practitioners might appear to act selfishly, using documentation to buttress their future successes. But it is this experience-induced "selfishness" that helps everyone. As they are less likely to mislabel the obscure as the obvious, the system will grow more approachable overall and easier to maintain in the long run. Engineering organisations could benefit greatly from such selfish individuals.

The third audience group is almost entirely ignored from the documentation rationale. Some readers will have previously engaged in professional writing or scientific research activities involving substantial written material. They will understand precisely what is being referred to. I will explain it best I can.

When we contemplate a problem, we feel it, we react to it. Much of the solution may be drawn from intuition — humans' innate ability to understand instinctively without involving conscious reasoning. For example, when a programmer is asked to print the first 100 natural numbers, she will naturally imagine the snippet `for (int i = 1; i <= 100...`; very little conscious thinking takes place.

Intuition is powerful because it enables us to solve complex problems without dwelling on the minutiae. It serves as a mental abstraction. Programming is challenging enough with intuition aiding us; if every line required meticulous deliberation and induced self-doubt, the process would be incredibly arduous. While it's typical for beginners with little command of a programming language to scrutinise every detail, it's unthinkable for seasoned programmers. This development of intuition significantly impacts productivity.

Like many powers, intuition is also dangerous. It can lead to decisions that lack rationale but appear sound and remain unquestioned in our minds. The programmer may inadvertently focus on the most complex parts of the program while churning out the rest on autopilot.

It is not only the trivial parts that are derived intuitively. Complex solutions may too be distorted by misguided intuition. A common example is ignoring edge cases when designing distributed applications. Many engineers gloss over the effects of failures on the state of the system, leading to inconsistencies that are difficult to identify and resolve.

It may have been Leslie Lamport who first said that "writing is nature's way of telling us how lousy our thinking is." When we write, we are forced to rationalise and explain to a virtual audience. We use language and images to convey our thoughts. Called to write on a topic, we often realise how flawed or incomplete our thinking had been. We summarily revisit the solution — fill the voids or redo it altogether. We then resume documenting. It is a structured, orderly process.

Writing isn't just communicating. Done with purpose, writing is an extension of the thinking process. The same is true of talking and of attempting to educate others. As it has been wisely said, you never really learn something until you teach it. (Or as in the case of documentation, explain it.) 

>Socrates, a relentless pursuer of clear understanding, engaged in dialogues to dissect ideas. He often emerged from these discussions with a newfound appreciation for the complexity of some fundamental concepts which appeared trivial at first.
>
>One may reasonably regard documentation to be a monologue because the audience is passive. On the other hand, if one views the author as playing the part of an active audience, reading and challenging what is being written in real-time, then documentation is a form of dialogue. One can ask a question, debate a point, and offer constructive criticism — to oneself.
>
>Documentation is, in some ways, a manifestation of the Socratic method, using the written medium as a proxy for self-reflection. It may not be as effective as debating a point with a (real) colleague but it is magnitudes better than relying solely on intuition. It is a form of thought. With consistent practice and dedication, many people have been able to cultivate this cognitive process.

Returning to the original question, how should one determine what to document and what not to? There may not be a simple answer that each of us craves. But in considering the interests of the three aforementioned audiences, we at least have the rough means of judging the adequacy of our documentation.

>On the occasions that I disagree with my colleagues on certain design decisions, I consider first whether these are well-prepared. If the solution must be explained verbally or comprises little more than a terse diagram, I don't always offer constructive criticism. I believe that the extent of constructiveness on my part should be commensurate with the effort on theirs. Yet, engineering ethics prevent me from inaction. Damn ethics.
>
>Instead, I may request that specific edge cases be documented and suggest which ones might be of interest. I expect little but the outcome often surprises me. The revised solution takes a more efficacious form, and comes documented as a bonus. It is as though writing has stimulated previously dormant parts of the brain.

Group one — others, present and future — is indispensable and should be at the forefront in almost every case. Software is rarely created in a vacuum; be it the end-users, other engineers, regulators, or support personnel, others will engage with the product of your thought. One must imagine themselves in others' shoes to perceive their unique needs and apportion documentation effort accordingly. If in doubt, create a situation where representatives of the target audience may ask direct questions. The nature of the questions and their answers should inform the documentation effort.

Group two — your future self — is too often disregarded through misplaced faith in one's own memory. Assume that a dozen other projects and hundreds of context switches will stand between your present and future selves. What are the things you are likely to lose track of?

Group three — your present self — is seldom given the attention it needs. Occasionally, it may be ignored: perhaps the solution was previously scrutinised or jointly developed, reducing the chance of misguided intuition. Otherwise, assume there are many falsi waiting to be debunked.

# Documentation principles
The previous section set the overall scene with a touch of the philosophical, positioning documentation as a worthwhile maintenance activity and identifying distinct audience groups. This section offers more practical advice in the form of a handful of lightweight principles. 

## Moderate the documentation effort based on stability
Rapidly changing aspects of the system suggest that the maintenance phase is yet to start for them. Since documentation largely supports maintainability, one may moderate the documentation efforts for those aspects that have yet to stabilise.

Documentation has a cost both in terms of effort and opportunity. The latter is important because documentation is often written by people who could otherwise be producing software; documentation and working software often contend directly for the same set of resources. Documenting fast-moving aspects will likely result in wasted effort whose benefits will not be realised fully. In that regard, documenting stable parts of the system yields more favourable cost-benefit ratios.

On the flip side, some documentation cannot be withheld completely, regardless of the state of maturity of the underlying software. It may be the essential user manuals or compliance documentation that need authoring regardless of the perceived payback. 

The needs of the third audience group must also be considered. Some things should be documented as a means of verifying their correctness, recognising that documentation is an extension of the thought process. Not everything needs thought enhancement, however. For example, in a set of programs collaborating using a distributed algorithm, one may want to document the algorithm and the possible execution paths, including those involving failures or timeouts. The testing strategy should also be documented. Self-reflection here can help identify critical gaps in the author's thinking. On the other hand, documenting the internal code structure, tooling and supporting scripts, and the CI pipelines, for example, yields little benefit if the software is being actively developed and frequently refactored.

The principle is to document early but moderate the effort according to the stability of the thing being documented. Within the thing itself, identify the parts that are relatively stable (e.g., the algorithm) and those that chop and change (e.g., the implementation), and apportion documentation efforts accordingly. Wait for overall stability before documenting the thing to the ideal level of completeness.

## The best documentation is the kind that doesn't have to be written
Documentation offers the greatest benefits when the aspects being described are otherwise difficult to understand by trained software professionals. (We focus on maintenance documentation here; user guides are separate concerns.) Difficulty of understanding is usually attributable to something novel or sufficiently different to what people have been exposed previously. While originality drives progress, not everything novel or different is beneficial or required.

The crux of this principle is in commoditising as much of the software as possible to minimise the documentation effort. To this point —

* **Prefer self-documenting code elements.** Classes, methods, and variables should be named with purpose, and constants should be favoured over "magic numbers".
* **Adopt idiomatic coding patterns and best-practices.** The maintainers of many technologies and programming languages, as well as the broader community of adopters, often advocate for consistent, if somewhat opinionated approaches to tackling common problems. Industry-standard approaches should be favoured over homebrew where possible.
* **Favour convention over configuration.** Code organised within a certain, well-known convention reduces the cognitive load on those attempting to decipher it.
* **Encourage the use of patterns and guidelines.** These are externally documented solutions to common problems that discourage people from reinventing the wheel. Solutions are also easier to understand where the use of patterns is apparent.

The principles above aren't just conducive to reducing documentation effort — they are beneficial in general. They lead to software that is easier to understand and maintain, and in many cases reduce the total amount of software that is produced.

## Convey the problem context where possible
The preservation of context is one of CONTROL's foundational principle, stating that those having a more complete appreciation of the problem context are more likely to arrive at an optimal solution. Equivalently, the propagation of context within documentation aids in the understanding of the solution being described. The audience will make same or similar conclusions to the author; the solution will seem less foreign once rationalised in the context of the original problem. 

## Written communication is not a substitute for face-to-face interaction
Written communication, while highly efficient, is not always a substitute for face-to-face interactions<sup>2</sup>. Documentation assumes some level of background knowledge and skills (language, technical, domain, etc.) on behalf of the audience. When writing, we usually target a specific audience with some but usually minimal variability in receptiveness. We could produce documentation with weaker assumptions — containing explanations of simpler topics and more overall redundancy, which may be frustrating to some readers. Equally, we acknowledge that stronger assumptions in documentation can alienate an audience that is less technically proficient or is unfamiliar with certain domain-specific terminology. We rarely have the luxury of targeting a truly diverse audience in technical documentation.

><sup>2 </sup>While this may sound suspiciously like a principle from the Agile canon, the latter takes a more extreme form, stating that face-to-face interactions are better unequivocally. Here, we are saying that only some face-to-face interactions may be more suitable.

Compromises must, therefore, be made. One shouldn't assume that a monologue with their audience will always suffice. While documentation can and should make the best attempt at conveying knowledge asynchronously, certain complex concepts or intricate details may require additional explanations that are more effectively conveyed in person. Like it or not, some things will need explaining, and some things will need it repeatedly.

This is not a call to minimise documentation; only to avoid the disillusionment that might ensue if it is relied upon as the sole carrier of knowledge.

## Documentation does not build relationships
The reliance on documentation, for all its benefits, is not without drawbacks. For example, people who document their work thoroughly and direct others' attention to it unyieldingly may be seen as unapproachable or, worse, condescending. In the long run, people may choose to withhold their queries if the documentation fails to answer them, rather than seeking clarification from the source. Or they may have unrelated queries that could be suppressed because of the perception of unapproachability. For example, they might have an idea to run by you, seeing that you are the expert — judging by your impeccable documentation — but a lack of relationship or biased perceptions may impede their approachment.

Where practical, it is best to balance comprehensive documentation with either follow-up activities or separate interactions aimed at establishing rapport with one's audience. Note, this is subtly different from the previous principle, which identified the occasional need to explain things. Here, we are discussing the forging of relationships between the producer and consumer parties, not resolving occasional misunderstandings. It may well be that the audience understands perfectly what has been documented, proving the documentation's effectiveness, but doing little in the way of relationship-building.

Interpersonal communication can foster collaboration and occasionally create mentoring opportunities, especially when knowledge transfer flows from more senior and experienced engineers to juniors. Such personal interactions can boost motivation and morale, making team members feel more connected and engaged with the rest of the organisation.

When a seemingly random question has been answered elsewhere, it is unquestionably better to direct the questioner's attention to the source than to answer directly. Otherwise, you are not only wasting time but encouraging further interrogation. But it may be worthwhile to follow up with them to ensure they are satisfied with the answer. This gesture will not go unappreciated and could mark the beginnings of a more fruitful working relationship.

## Feedback informs documentation
Referring to the "written communication is not a substitute for face-to-face interaction" principle, it is likely that many follow-up questions will be asked when the subject matter is complex or the audience is varied.

Be careful in answering questions in haste without understanding the reason for their asking:

1. If the question has been asked by someone who is not across the topic, then the best course of action may be to explain directly or refer the individual to some background reading. A face-to-face interaction may end up being the optimal course of action, depending on questioner's abilities.
2. If it is asked by someone who hasn't read the documentation properly, then it is best to refer them back to the source. As a token of courtesy, one should direct them to the relevant passage. The questioner may have missed the original point by accident, out of sheer laziness, or a contempt for reading. A hastily made assumption here may prove incorrect. Hanlon's Razor will serve you well: never assume malice where incompetence, or a simple oversight, or a momentary lapse of judgement, will do.
3. If the question is sensible but the answer to it is not documented, then consider revising the documentation before responding. In fact, it is better to respond with reference to the updated documentation and have the questioner confirm later that the updated documentation completes their understanding. This is

Point 3 is precisely the concept embodied by this principle. Stated otherwise, documentation should act as a medium for answering questions within a feedback loop. This is a highly effective method for verifying and enhancing the accuracy of documentation. Sadly, this method is rarely practiced in our industry.

>As with all philosophical heuristics, Hanlon's Razor isn't always right but is right on average.
>
>I have witnessed many colleagues' behaviours that signalled contempt for reading documentation. Or so I felt at the time. Thereafter, my perceptions were disproved on numerous occasions. The same colleagues would later read other documentation, often my own. What gives?
>
>After long searching and the occasional doubting of Robert Hanlon's wisdom, I believe I now have a satisfactory explanation. The reason software engineers resent reading documentation is precisely the same reason they blindly copy Stack Overflow snippets and use large language models like Microsoft's Copilot to generate code that later blows up in production. That reason is two-pronged: _instant gratification_ and _deferring the inevitable_. 
>
>The effects of regulating gratification have been described in psychology for well over half a century, starting from the famous Stamford Marshmallow Experiment (Mischel & Ebbesen, 1970). We will revisit its findings later. Most readers will be familiar with the term; if not, instant gratification refers to "the temptation, and resulting tendency, to forego a future benefit in order to obtain a less rewarding but more immediate benefit." (Ackerman, 2018.)
>
>Consider the following example. Tao, a senior software developer, is stumped by an occasional deadlock in the order management database and doesn't know where to begin. Her best course of action is to read the "bible" on concurrency control theory by Phil Bernstein and colleagues. The first three chapters of Concurrency Control and Recovery in Database Systems offer a superb introductory understanding, which would likely make Tao's newfound knowledge put many of her colleagues to shame. Alternatively, many databases offer free and comprehensive documentation, including that of transaction semantics.
>
>Instead, Tao pokes around, asks the Internet, and consults a chat bot. She learns of a connection between transaction isolation levels and deadlocks. After little deliberation, Tao decides to lower the isolation level of some queries. The deadlocks seem to vanish.
>
>Three months down the line, the business has grown substantially. Many customers are reporting problems with their orders. Some are missing from the system despite the customers' accounts having been charged. Others are fulfilled in duplicate. Financial reports are showing incorrect figures. The problem was first noticed sometime after the deadlock fix and appears to be exacerbated by transaction volumes. The business is panicking. The CEO has sent several personal letters of apology.
>
>Tao is back on the case. She ends up reading introductory texts on concurrency control, discovering such concepts as transaction isolation, atomicity, serialisability, transaction histories, and scheduling. She also consults the database documentation. Eventually, Tao reverts the isolation level and carefully rearranges the order in which resources are accessed in certain queries. This eliminates transaction dependency cycles, resolving the deadlock condition without introducing consistency problems.
>
>There are two important issues at play here. The first issue is one of instant gratification. Tao was aware of how badly her knowledge was lacking but consciously chose a more expedient path that was later shown to be erroneous, as it so frequently is. The second issue is one of deferring the inevitable. Like it or not, the problem required a proper solution, which needed time investment on Tao's behalf. Often, those craving a "quick hit" will eventually realise their misstep and take more prudent actions. If not, those actions will be taken by others on their behalf.
>
>Returning to Mischel and Ebbesen's experiment. It involved a group of children, each seated in a private room with a marshmallow in front of them and a researcher present. A deal was offered: they could eat the marshmallow while the researcher stepped out, ending the experiment. But if they waited for the researcher to return, they'd be rewarded with a second marshmallow. So, one treat now or two later.
>
>Some children took to the marshmallow immediately. Others wiggled and fidgeted in an attempt to self-restrain but succumbed to the temptation eventually. Only a few had the patience to await the second marshmallow. The results were predictable and mostly unremarkable.
>
>The truly interesting part occurred years later, when the children matured. Follow up studies were conducted, tracking each child's progress. The youths who had delayed their gratification during the earlier experiment ended up having higher exam scores, lower levels of substance abuse, lower likelihood of obesity, better responses to stress, and better social skills. (Mischel, Shoda, & Peake, 1988, Mischel, Shoda, & Rodriguez, 1989, and Mischel, Shoda, & Peake, 1990.)
>
>The researchers tracked each child for more than forty years and, repeatedly, the group who waited patiently for the second marshmallow succeed in every measured capacity.
>
>In the same way that awaiting a second marshmallow increases our likelihood of success, taking the time to uplift our skills achieves the same.

Each of us has a role to play in ensuring that our colleagues and, in reciprocation, ourselves, are acting judiciously and not succumbing to perilous expediences. It is for their good and ours. Regarding documentation, the occasional need for verbal explanations notwithstanding, the questions that may be answered via documentation should be answered via documentation.

## Prefer breadth of documentation to depth
Assuming that the resources expendable on documentation are finite, it is better to strive for more high-level documentation covering diverse areas than to have a narrow concentration of low-level documentation.

Consider the analogy of a tourist in a foreign country. What would benefit them more, a map of the country showing the major urban areas and connecting routes or a detailed map of one town? Assume there is no access to mapping software and satellite positioning services.

One can get by without a town map; once they get to the town, they'll either ask directions or find someplace that sells local maps. Conversely, it's a lot harder to find a town without some topological reference, at minimum. The tourist cannot stop in the middle of nowhere to ask for directions.

Exploring a complex software system without high-level documentation is like trekking through unfamiliar terrain without a map. Where to begin? Whom to ask? Access to detailed component designs will not help those starting out. On the other hand, overview-level documentation can be used for further prompting. The audience can leverage their newfound knowledge of the coarse-grained elements and their relationships to drill into specific areas of the system that interest them most. Their queries may be answered by the owners of components or subsystems. Over time, the frequency and nature of the queries can empirically inform the optimum allocation of effort for subsequent documentation.

# What to document
Some knowledge will invariably remain in tacit form. It is, nonetheless, irresponsible to say that we should accept this as a factor beyond our control. There is more within our control than we care to admit. The question is one of priority. It may not be practical to document everything and do so exhaustively. One must, therefore, choose which aspects of the system should be documented and at what level of detail. Where do you begin?

Here, we consider the most important aspects of the system whose documentation cannot be neglected. The sections that follow outline the minimum recommended content that should be put to paper.

For each of the documents, there is specific recommendation on the document's owner(s). These are the roles responsible for producing the various sections and ensuring their completeness, accuracy, and currency — bearing in mind that some documents will be expansive, requiring multiple collaborating authors. While some documents will be relatively static, others will evolve periodically — their authors will change over time.

Each document will have an accountable party, ensuring its efficacy and continuity. This role also guarantees that the necessary document owners have been engaged and each is aware of their specific responsibilities. The documentation must ultimately see to the needs of the delivery organisation and appropriate resources must be expended on its upkeep. (Sufficient but not excessive.) And while multiple people will contribute to these objectives, precisely one role will be accountable — in line with CONTROL's foundational principles.

A document's owners may have divergent reporting lines (i.e., they report to different managers). Who should be accountable in this case? For simplicity and convenience, we assume it to be the Head of Engineering role; every prospective document owner is its direct or indirect subordinate. (This includes members of the Product, System Testing, and Infrastructure teams.) In practice, the Head of Engineering may be a dedicated role or a function fulfilled by the CTO, depending on the depth of the organisational hierarchy. This role is used as a surrogate when a more specific role cannot be identified.

## System architecture
Imagine the system as a complex puzzle. The high-level architecture is like the box of the puzzle that shows a simplified version of the completed image. It provides a broad overview of the system's structure and the principles guiding its evolution. It identifies the key components and their relationships, and explains how those components and the system as a whole may change over time. At a minimum, architectural documentation should contain the following elements.

* **Introduction**: Describes the purpose and sets the context, guiding the understanding of the other architectural elements that follow. Ideally, it should also bind the scope of the document and specify its target audience. A glossary of common terms may also reside here.
* **Subsystems and components**: These are the fundamental parts of the system described at a coarse level of granularity. 
    + In large systems, subsystems are generally the next level of decomposition. They are essentially smaller systems with interesting architectural elements of their own. Architecture documentation may comprise just the subsystems or both the subsystems and the underlying components, depending on the level of detail one is willing to convey. When describing two (or more) levels of decomposition, it is best to split documentation into multiple parts to not overwhelm the audience with excessive upfront detail.
    + In small systems, it is the components that generally make up the systems directly.
    + Diagrams are invaluable tools to communicate complex information effectively. Annotated component diagrams can convey much of the essential complexity without excessive verbosity.
* **Interactions**: The interactions between key components can be depicted using both static and dynamic views, showing not only their relationships but how the components collaborate during specific work flows.
    + Focus on the interactions between the components at the coarsest level of granularity; i.e., define how subsystems relate to and interact with each other.
    + Only once the coarse-grained interactions are captured should refinement occur.
    + Sequence diagrams, collaboration diagrams, and data flow diagrams are useful here.
* **Boundaries**: A system is rarely deployed in isolation; it often interfaces with other systems and end-users. Which other systems? Which users? How do they interact with the system? Via which interfaces? It is easy for an architect to assume that everyone knows such basics but these are the sorts of questions that an entry-level audience comes up with.
* **Team ownership**: Understanding who is responsible for each part of the system is essential for collaboration and accountability. Subsystems and components will be built and supported by engineering teams. Knowing which teams are responsible for specific parts of the system allows the audience to reach out to the teams in question in pursuit of further inquiries.
* **Architectural principles**: These are the guiding stars for the system's growth, setting the overall path for its future evolution. The architectural principles inform all those working on the system to make changes in line with the ideas and concepts upon which the system was founded. A set of well-defined architectural principles supports CONTROL's _conceptual integrity_ foundational principle, introduced in Chapter 4.
* **Handling of nonfunctional requirements**: Most systems will exhibit specific nonfunctional qualities, like scalability, reliability, etc. How these are met may not be immediately obvious when consulting the various architectural views. For example, it may be necessary to explain how the system behaves in the presence of failures, or how it responds to increased workloads.
* **Data**: Architectural overviews often disproportionately focus on components and connectors, and detailed interactions in some cases, neglecting the cardinal object being manipulated. Almost every component will refer to data in some way: some will parse, format, read, persist, and transform data, and many will perform a combination of the these. Furthermore, the proliferation of distributed systems has meant that data is no longer stored in one master location, and is seldom normalised. There's often too much of it to describe comprehensively. It thus makes sense to capture those aspects that convey the most amount of useful information to the audience:
    + The main business entities manipulated or referred to by the system. This includes their attributes and data types.
    + The relationships between the key entities including the associated cardinalities.
    + The flow of data between various subsystems and components, indicating how data is modified along its journey.
    + A common vocabulary for key entities. This ensures alignment across all members of the audience by promoting consistent use of terminology.
    + How data privacy concerns are handled, where applicable.
    + The retention and availability requirements of different types of data. This includes backup, redundancy, and recovery constraints.
    + Archival, deletion, and the broader data lifecycle concerns.
* **Deployment**: Much of architecture thrives in the land of abstractions and yet the real system will ultimately consist of processes and infrastructure resources that must be deployed in a physical sense. It may be worthwhile specifying —
    + A catalogue of environments; e.g., development, staging, and production.
    + A description of the network topologies and perimeter controls used; e.g., subnets, firewalls, and load-balancers.
    + Material differences between environments; e.g., development and staging use lower-spec hardware.
    + For applications that run on end-user devices, how they are deployed to their intended destination.

>The distinction between components and subsystems is purely notional in many texts. Each is a granule of functionality with well-defined boundaries. Nonetheless, I distinguish among them using the following heuristic: a subsystem is a type of component that represents system in its own right, albeit a smaller one. Being a system, it has architectural concerns that may vary greatly from its peer subsystems. Subsystems derive from the overall architectural principles of the overarching systems but may add principles of their own; those principles may be unique and highly specialised.
>
>Imagine, for example, a sports wagering system. In a very simplified form, it comprises 1) an _offering subsystem_ that processes various market feeds and calculates the betting odds, and 2) a _betting subsystem_ that takes customers' bets, assesses their exposure risk, and settles the winners. Each subsystem comprises multiple components; in other words, each is interesting architecturally. The two subsystems have very different nonfunctional characteristics. The offering subsystem must process large volumes of data with low latency, but it is unconcerned with transactions and may operate under relaxed consistency constraints. The betting subsystem deals with lower volumes but must preserve strict transactional semantics as it deals with customers' money. Each subsystem is heavily specialised. It is, therefore, conceivable that each requires a unique set of principles and guidelines. They may be built using different technologies, employing different skill sets, and are thus likely owned and operated by different engineering teams.
>
>In comparison, the components that make up one (sub)system will have much more in common. They are generally built using similar technology and follow identical principles.
>
>Since a subsystem is a type of component, the latter is more generalised. There may be other kinds of components too. For example, a class is a component of an object-orientated application. Therefore, when the term is used without further qualification, it may refer to any part of a larger whole.

The above is not a complete list of architectural aspects, but I believe it to be sufficient for most systems. Some architecture frameworks may require more viewpoints and advocate proprietary modelling notations. The Open Group Architecture Framework (TOGAF), for example, is keen on business process views (The Open Group, 2018), which are immensely useful for many kinds of business work flow systems.

The high-level architecture of the system is the equivalent of the national map in the "prefer breadth of documentation to depth" principle. It gives its explorers a place to start their journey.

**Document owner(s):** The Architecture team is responsible for producing the system architecture and ensuring its validity. 

**Accountable party:** The Architecture Manager (or equivalent). In the absence of this role, the Head of Engineering takes accountability.

## Engineering principles
While the overarching system will evolve according to a set of architectural principles, the implementation of its components will be subject to a further set of engineering principles. These are produced at varying levels of decomposition. At the top-most level, engineering principles govern the complete engineering organisation; in other words, they apply equally to all teams or practices that operate under the engineering umbrella. In turn, each engineering practice or team may have unique principles of their own.

Teams differ from practices. A team is a group of professionals working together to achieve specific goals. A practice is a grouping of people based on common characteristics, such as methods or ways of working. The cardinalities of the person-team and person-practice relationships also differ: while an engineer (or tester) will belong to exactly one team, they may simultaneously partake in zero or more practices. For example, a person may be a member of both mobile application development and DevOps practices.

Consider an example: A company has three cross-functional engineering teams, comprising both front-end and back-end developers. The teams look after three separate customer experience verticals: shopping cart, product catalogue, and account management. Simultaneously, the company operates separate practices for front-end and back-end technologies. The company has a common set of engineering principles, covering such crosscutting concerns as logging and security.

In addition, each practice lays down specific principles relating to their respective technology stacks and preferred ways of working. The front-end practice is mostly concerned with the development, versioning, and deployment of React components. Conversely, the back-end practice sets guidance for the development of Java applications, including the design of REST APIs and the use of object-relational mapping frameworks. Each drives consistency and excellence within the engineering aspects under its purview. They can incubate new ideas and techniques, and ensure that the organisation's technology portfolio evolves sustainably.

>Most engineering organisations feature multiple engineering teams but only few commit to engineering practices. I believe this to be a missed opportunity, especially considering the ease with which a practice may be spun up and their benefits relative to cost. For starters, it's an informal group that can be truly self-organising. While teams are managed by accountable individuals, practices may be run in more egalitarian ways. Individuals' participation in practices may take active or passive forms, depending on their interests and available time. In addition to the obvious benefits of driving consistency and promoting overall excellence, they offer a club-like experience for their members. Practices support their members and help smoothen the new-starter experience. They can heighten the individuals' sense of belonging and provide a platform for continuous learning, fostering a culture of collaboration. They can also set the scene for mentorship, allowing more experienced engineers to share their knowledge and help junior members grow.

Finally, some engineering teams may adopt principles of their own. For example, the account management team benefits from a consistent, if opinionated approach from its team members regarding the storage and transmission of personally identifiable information (PII). Crucially, principles local to teams and practices mustn't conflict with higher-level principles. In our example, the team's principled handling of PII must be in line with all security principles codified at the engineering and architecture levels. Remember, if a pair of principles contradict, one or both are incorrect or misinterpreted; clarifications or amendments may be required.

Principles should be documented close to their intended audience and readily accessible. When using a wiki, for example, the team principles should be contained in the team's local space. The responsibility and (in most cases) accountability for defining and maintaining principles rests with those managing the intended audience. For example, the Head of Engineering maintains the engineering principles, while the Engineering Manager handles the principles for their team. Delegation is possible and sometimes necessary. Practice-level principles are maintained by either the practice lead, the seniormost member, or the complete collective, depending on the chosen structure and conventions. There may not be a single person accountable for a practice. It is chiefly for that reason that engineering practices and centres of excellence are not part of the CONTROL delivery organisation, although their presence is encouraged.

**Document owner(s):** At the overarching level, the Engineering Managers and Principal Engineers collaborate on the definition of engineering principles, guided by the Head of Engineering. They may consult the Architecture team to ensure that engineering and architecture principles are not in contradiction. At the practice level, members of the practice or the practice lead will maintain the principles. At the team level, the principles will be maintained by Engineers, guided by their manager.

**Accountable party:** The Head of Engineering is accountable for the overarching principles, as well as ensuring that the practice-level principles are captured. At the team level, the accountability rests with the EMs.

## Requirements, standards, conventions, and guidelines
These are extensions of the engineering principles but are more specialised. They are rules prescribing the day-to-day activities of various team members — coding, testing, releasing, and deploying software, for example. They should be specified unambiguously where possible. Ideally, their use should be enforced programmatically (e.g., code coverage ratio) although this is not always achievable (e.g., code review guidelines).

Examples of these rules include:

* Language-specific coding conventions and best practices: style guides, linting rules, etc.
* Acceptable code coverage level, which may be specified at both the line and branch level.
* The use of specific standards; for example, the ISO-8601 standard for encoding dates and times in JSON payloads.
* Branching strategies, code review and merge policies.
* Where applicable, guidelines for selecting and adding new dependencies.
* Code and API documentation standards and guidelines. For example, "we encourage an API-first approach with OpenAPI 3.0 as the specification language, and Swagger as our interactive documentation tool."
* Conventions for writing integration and performance tests. The latter, in particular, are not frequently practiced by Agile organisations but are required by CONTROL's focus on nonfunctional requirements and its accountability model. The expectations on software engineers should thus be documented clearly.
* Error handling practices.
* Telemetry standards and guidelines: 
    + What to log and how to structure and organise logs. For example, some teams will format logs using JSON.
    + What should be captured in metrics; e.g., latency, retry rates, error rates, throughput, and queue depth. How should these be organised: whether metrics should be capturing scalar values or histogram-like distributions, and guidance on when one approach might be preferred over another.
    + What sort interactions should have traces associated with them. How should traces be stitched together in a distributed system.
    + Which telemetry libraries are preferred, and whether there is a preference for auto-instrumentation or hand-crafted production of telemetry.

Much like engineering principles, these specialised rules can be established different levels of the engineering organisation — refined by the team or practice dimension. Those in charge of the principles also curate the more specialised rules at the corresponding level.

**Document owner(s):** As per the engineering principles.

**Accountable party:** As per the engineering principles.

## Team inventory and as-builts
This comprises an enumeration of the intellectual assets of each engineering team, detailing the items under each team's care. Some of these assets may have already been captured by the system architecture at an outline level. The team-level documentation offers a more detailed account.

Design documentation tends to hover at the level of ideas, concepts, algorithms, and abstractions. This is great because it hides unnecessary detail and conveys an at-a-glance appreciation of a complex solution. When detail is sought, one may find it by consulting more specific documentation at the subsystem level. However, the risk with all design documentation is that it tends to be produced by those who envision an ideal system void of compromises.

A real system is built by engineers who seek compromises; these are not always aligned with the views of the designers — Architects, Principal and Staff Engineers, and others. While designs generally conceals the details, the compromises are not always in the details. The implementation may differ from the design from the outset, or it may diverge unnoticed over the course of the system's maintenance.

It is thus necessary for engineering teams to maintain an accurate account of their current state, also known as an as-built. As-builts, unlike conventional design documentation, do not guide the development of the system. Instead, they capture what has been developed. A set of as-builts may be more narrowly scoped than the initial design. This occurs during the early stages of a capability delivery, where some parts of the system may have been delivered. As-builts never capture aspirational aspects of a system that have not yet materialised or take a different form from the original design. Conversely, the scope of an as-built may grow to eclipse that of the original design with time, as more features are delivered or the system is refactored.

>The term "as-built" has its origins in civil engineering, referring to the final set of drawings and documents that reflect the actual construction of a structure, as opposed to what was initially planned, the latter termed "as-designed". 
>
>The practice of creating as-built drawings has been standard fare in construction for decades. These were traditionally created by marking up the original design using red ink, which produced the term "redline", eventually becoming synonymous with "as-built". This approach is tractable in buildings because the 1) deviation from the design is often highly constrained and 2) once a building is complete, it rarely evolves further. Redlining doesn't work in software because 1) the magnitude of the deviation may be arbitrarily large and 2) software is rarely finalised once delivered. 
>
>It is best to leave the original design documentation as-is, capturing the relevant parts of the system as they were initially conceived, and create a separate set of documents that represent the current state. This approach takes no additional effort; one can simply clone and repurpose the original documentation. The preservation of the originals also helps in the propagation of context. Suppose the system encountered substantial compromises along its delivery, owing to certain pragmatic constraints unbeknownst to its designers. It may be discovered (much) later that the system does not exhibit the nonfunctional characteristics originally envisaged. Having a clear distinction between the as-designed and as-built documentation enables one to determine where the gaps may lie.

**Document owner(s):** Engineers maintain as-builts, ensuring that all material changes to a team's intellectual assets are reflected in the documentation. Their managers provide guidance and feedback on the contents of the team inventory, ensuring that all of the essentials have been captured at a suitable level of detail.

**Accountable party:** The Engineering Manager is accountable for the continuity of knowledge and reduction of key personnel risks within the team. Team-level documentation is, therefore, the province of the Engineering Manager.

## Interface definitions
Continuing the topic of as-builts, among the most useful nuggets of knowledge is how a subsystem or component is meant to communicate with its peers or the outside world. This is particularly useful for integrators and other teams who don't want to know every detail about some component of a system, only how to talk to it.

By interfaces, we refer to not only the synchronous APIs that a component exposes but also the messaging contracts if the component communicates asynchronously, for example, over a message broker or an event streaming platform. Since there may be many such interfaces and associated schemas, the effort should be concentrated in documenting those interfaces that operate at the subsystem boundaries. If subsystems have not been formally defined, prioritise interfaces that govern cross-team interactions. Why should boundary contracts be prioritised?

Firstly, these contracts and the underlying services support cross-team collaboration, which is generally more taxing than collaboration among the members of one team. External teams may be unaware of your services catalogue because they were not part of its development; even minimal documentation here may well prove indispensable. Conversely, interfaces between the components belonging to one team may be discovered by its members with little effort by asking or poking around in a more familiar code base.

Secondly, boundary contracts typically act as direct or transitive supporters of functionality that exists elsewhere; these relationships being particularly difficult to trace in distributed systems. As Leslie Lamport famously said: "A distributed system is one in which the failure of a computer you didn't even know existed can render your own computer unusable." (Lamport, 1987.) Lamport is, of course, talking from the perspective of a consumer. Paraphrasing to suit our context: ... a failure of a service you didn't know existed rendered yours unusable. Thus, to help traceability and minimise surprises, all services provided by one team and consumed by another should be thoroughly documented.

Finally, teams will periodically refactor their components to improve some nonfunctional characteristic and prolong their life in general. Refactoring ideally avoids impacts to external parties; it is a localised activity. Conversely, changes to boundary contracts rarely have purely local effects. Boundary contracts thus tend to change less frequently compared to the internal ones. Taking a cost-benefit perspective on documentation, and in adherence to the "moderate the documentation effort based on stability" principle, boundary contracts should take priority.

**Document owner(s):** As per the team inventory and as-builts.

**Accountable party:** As per the team inventory and as-builts.

## Documentation of CI/CD artefacts, infrastructure, and processes
The documentation of the engineering aspects relating to continuous integration (CI) and continuous delivery (CD) paradigms tends to be overlooked. Perhaps it is because CI/CD infrastructure tends to be exercised daily (often multiple times a day), and that redundant tacit knowledge exists across many engineers within the organisation. There is little concern in the minds of the management that CD/CD represents a knowledge risk to the organisation.

It is no more difficult to argue against this thinking than it is to quiesce the opponents of documenting application code. After all, code is changed daily and yet we agree _in principle_ that knowledge continuity is critical when it comes to application code and intellectual assets in general. (In principle, we agree; in practice, we often neglect. But that is another matter.)

I believe the real reason is that management simply does not recognise CI/CD artefacts, infrastructure, and processes as intellectual assets. They are helpers for the final mile, if that. And helpers not in writing or debugging code, but in some menial automation activities; brain-dead tasks that up until only a few decades ago used to be done by hand.

If you have succumbed to this kind of thinking, ask yourself a couple of simple questions: Why does it take so long for our pipelines to run? And why are they so goddamn flaky? 

I suggest that the pipelines are often so hopelessly neglected because they've not been treated as engineering assets, despite being maintained by engineers. (In the best case, by engineers. In many others, by infrastructure personnel who have little awareness of automation concerns, often acting as proxies for engineers.)

Documenting the relevant aspects of CI/CD at both the overarching engineering and team levels will not solve the problem overnight. But it will position CI/CD as an engineering concern, at a minimum. The subsequent sharing of documentation may also encourage healthy debate. And the act of documenting in and of itself may provoke thought.

In the documentation, you may wish to consider the following.

* **Tooling**, including the infrastructure, programming languages, libraries, and frameworks used to define and execute CI/CD artefacts. The tooling documentation should support existing engineers and new starters alike. For the latter, it could be seen as a landing pad — a place to begin the self-onboarding process.
* **Coding and configuration guidelines**, ensuring that CI/CD artefacts meet agreed quality requirements, analogously to their contemporaries in the application development sphere. Good documentation in this area can save considerable effort in debating the nuances of coding style, and can minimise frustration and productivity bottlenecks.
* **Pipeline stages**, including the detailed description of each stage (e.g., build, test, deploy) where necessary. Workflow diagrams can aid in the representation of the pipeline stages and their sequences, as well as any conditional logic used to trigger or bypass stages.
* **Database upgrade strategies**, involving the planning and execution of updates to the database schema and data. These upgrades need to be carefully considered and documented to allow for smooth transitions without disruptions or manual intervention. 
* **Deployment models**; e.g., blue-green or rolling. These specify how new code changes are rolled out across environment. Effective documentation of these models can ensure consistency and reliability in deployments.
* **Failure handling strategies**; e.g., rollback or roll-forward strategies. These specify what happens when an application, for whatever reason, could not be deployed to its target environment.
* **Troubleshooting guidance**, comprising a list of common problems and their solutions.
* **Roles and responsibilities**, outlining which teams are responsible for various aspects of the CI/CD process. For example, the infrastructure team is the designated custodian of the infrastructure, the application developers are responsible for writing and supporting the pipeline code, and the environment owners are responsible for approving deployments to their respective environments.
* **Change management**, specifying how changes to CI/CD artefacts and deployment environments are administered. Change management documentation may overlap with the roles and responsibilities documentation, as it specifies the approval process for changes to the pipeline and deployment to specific environments. It is often missed or treated implicitly in many organisations. The importance of explicitly defined change management processes is elevated substantially for systems operating in highly regulated industries. 
* **Security**, detailing the methods used to secure the CI/CD pipeline and ensure only authorised personnel can make changes. Security documentation may also include auditing controls, ensuring that all changes to the pipeline and deployments to high-assurance environments are irrevocably recorded and associated with the appropriate user principal. Whether this sort of documentation is required depends heavily on the operating environment.

**Document owner(s):** Depends on the separation of infrastructure and software development roles within the organisation. This document covers a broad scope: Some of its aspects (e.g., tooling, security, change management) may be filled by the infrastructure team. Other aspects may be owned by software developers. The Head of Engineering is the ultimate owner of the document, allocating responsibilities for its completeness to the appropriate parties. He is also responsible for defining the roles and responsibilities; ideally, this occurs before the rest of the document is compiled.

**Accountable party:** The Head of Engineering.

## Incident management processes
These are essential for ensuring that incidents are handled efficiently and their impact on business operations is minimised. Documenting them provides clear guidelines and ensures consistency in how incidents are managed. This reduces the level of chaos that is often associated with incidents and improves (mainly by de-stressing) the lives of support personnel and rostered engineers.

Consider documenting the following.

* **Definition and classification**, specifying unambiguously what constitutes an incident and criteria for assessing its severity (e.g., critical, high, medium, low). A critical incident, for instance, may prevent the business from operating entirely with no workarounds possible. Incident classification helps avoid undue kerfuffle during minor events and enables more effective prioritisation of actions, particularly when multiple issues are being observed concurrently. It is also important to define when an incident can be deemed resolved, which is ideally distinguished from any follow-up postmortem activities that may take place later.
* **Logging and reporting**, specifying how incidents should be reported (e.g., via a ticketing system, email, or group chat). The most useful thing that can be done once an incident has been identified is to log it and ensure that the relevant context (timestamps, environments, application versions, error messages, reproduction steps, etc.) has been attached to the incident record. A well-honed incident management process always records the problem before attempting to solve it.
* **Roles and responsibilities**, outlining the teams or individual roles responsible for overseeing the incident as well as those acting in a supporting capacity. It may include guidelines on when and how to escalate an incident to a higher authority. Defining expectations at a role level has the advantage of making team members interchangeable. If someone is familiar with a specific role, they can step into that role for any incident, allowing for flexibility and ensuring continuity in response efforts.
* **Response procedures**. These are specific steps that should be followed to diagnose and troubleshoot faults or mitigate their effects. Comprehensive root cause analysis may be the only method available in some cases, and not all faults may be dealt with a run sheet. But for many kinds of faults, mitigation processes should be defined.
* **Communication plan**, specifying how and when to communicate with internal stakeholders (e.g., staff, management, compliance officers, C-suite) and external stakeholders (e.g., customers, integration partners, the media, law enforcement, the general public). Guidance may be offered on the frequency and content of status updates during the incident. 

If you recall Jackman's five workplace toxins in Chapter 6, a frenzied work environment was among them. Proper incident management documentation can act as an effective remedy. It offers clear, predefined steps for handling incidents, thereby reducing stress and confusion during the most inopportune moments.

**Document owner(s):** Depends on the availability of a dedicated application support team (or equivalent) and their structure. Areas relating to the classification of incidents, their logging and reporting, and the broader communication aspects will generally be handled by a dedicated "frontline" team. The response procedures will require significant involvement from Engineering.

**Accountable party:** The Head of Engineering. He should begin with documenting the roles and responsibilities, as they relate to the incident management processes.

## Backup and recovery procedures
Without a well-defined and tested backup and recovery process, an organisation is exposed to a very significant risk of losing data and, in some cases, operational ability. The following aspects should be documented:

* **Requirements and policies**, consisting of the types of data to be backed up, frequency of the backups, and the backup retention period. Requirements should be stated in measurable terms, for example, using recovery point (defined as the maximum amount of data — as measured by time) and recovery time (defined as the maximum duration of the disruption) objectives. The number of redundant copies should also be specified, as well as any constraints on their storage locations. Businesses rarely attribute the same value to all of their data; it is thus necessary to distinguish among them when stipulating their backup requirements.
* **Procedures**, specifying using clear, step-by-step instructions how data should be backed up and restored. This section should also encompass all of the tooling used during backup and recovery actions, as well as the relevant configuration. Backup schedules should also be specified, as well as the effects on the system during backups. Snapshot files may need to be verified post-backup and encrypted; such follow-up actions should also be detailed in the backup procedures.
* **Testing strategy**. This is probably the most important part of the documentation, aimed at ensuring that backups actually work. The importance of testing cannot be overstated: according to Avast (2017), around 60 per cent of backups are incomplete and around half of restores fail. The implications are profound: of the companies that have experienced a data-related outage for more than ten consecutive days, 93 per cent have filed for bankruptcy within twelve months of the incident. Ensuring that testing processes have been defined and comprehensively documented (and thereafter practiced regularly) can prevent a catastrophe.

The formation of data backup and recovery processes mustn't be left to chance, particularly when one considers that ad-hoc or vaguely defined processes cannot be effectively tested. For more information on defining the backup and recovery processes, and contingency planning in general, consult the NIST-800-34 special publication (Swanson et al., 2010).

**Document owner(s):** There are several roles involved in defining and verifying (testing and rehearsing) backup and recovery procedures:

* Retention requirements will mainly originate from various data owners, potentially spanning multiple departments. The definition of specific backup policies should be based on these requirements, as well as overarching policies that apply at the organisation level. CONTROL doesn't prescribe the parties responsible for defining requirements and policies; in practice, these roles will vary significantly among organisations. Furthermore, this role is not a technical one; it requires an understanding stakeholders' needs and the value of different types of data within the business. The elicitation of backup requirements should ideally happen during the Abstraction phase of capability delivery, and is the responsibility of POs. Deferring backup requirements post-delivery is not recommended unless the business is tolerant of data loss.
* Backup and recovery procedures are specified at a deeply technical level, requiring a solid understanding of the system's components and various sources of data. If requirements and policies are be treated as a problem, then the backup and recovery procedures form the technical solution. Engineering teams are responsible for designing and implementing the backup and recovery procedures, with guidance from Infrastructure and Architecture. Ideally, this would take place during Elaboration (the design of backups) and Construction (the definition of procedures and backup scripts), particularly for mission critical data. Once implemented, the Engineering teams ensure the currency of the backup and recovery documentation relating to their components.
* Testing of backup and recovery procedures may occur at varying levels. Engineering teams will want to ensure that the persistent state of their components can be backed up and restored. Not all parts of the system will be attributable to a specific Engineering team; there may be common infrastructure with persistence concerns — such as message brokers — that can only by backed up and restored by the infrastructure custodians. Furthermore, the System Testing team will want to conduct an independent appraisal of the procedures, verifying that the overarching recovery point and time objectives are being met.

**Accountable party:** The main challenge with this document is that it refers to high-value assets that keep changing as the system evolves and its functional scope expands. And while the Head of Engineering takes accountability for the document, he cannot possibly keep abreast of the changes. Even the occurrence of a material change may not be obvious to anyone outside the delivery organisation, let alone its details. He should, therefore, disseminate the accountabilities among the aware parties; for example, making the POs accountable for specifying data retention requirements.


## Disaster recovery plan
A distant cousin of (data) backup and recovery, disaster recovery (DR) is concerned with the restoration of a business's operation (or part thereof) at an alternate facility in response to a major failure. The failure may be due to problems with software, hardware, or the facilities 
themselves. (We focus on failures relating to — affecting or affected by — engineering.) The following aspects should be documented:

* **Trigger criteria**, define unambiguously the conditions under which the DR plan will be activated. There may be specific events (e.g., unrecoverable hardware failure) or leading indicators (e.g., performance degradation, observed failure rate) that enact the transition.
* **Roles and responsibilities**, outlining the teams or individual roles responsible for coordinating DR procedures and ensuring the readiness of software systems, engineering and support staff.
* **Cutover procedures**, specifying using step-by-step instructions how functionality should be transitioned from one site to another.
* **Communication plan**, specifying how and when to communicate with (predominantly) internal stakeholders.
* **Testing strategy**, detailing how the DR plan should be verified for fitness. This may include the scheduling of "fire drills" to practice live or simulated cutover activities.
* **Training and awareness**. While activities like data restoration impact a relative minority of engineering staff, a DR-initiating event may impact a much larger contingent. Training manuals may need to be issued to all staff likely impacted by a DR event.

**Document owner(s):** Similar to that of the backup and recovery procedures: 

* The specific capabilities requiring enhanced availability (via DR) is specified by POs during Abstraction, through consultation with the relevant stakeholders. 
* The design and implementation proceed within Elaboration and Construction. Once implemented, the Engineering teams ensure the currency of the DR documentation relating to their components.
* The System Testing team is responsible for verifying the overall efficacy of the DR plan and maintaining the testing-related aspects of the documentation.
* Engineering broadly owns the training and communication aspects as they relate to the system. Ownership responsibilities will be farmed out by the Head of Engineering.

**Accountable party:** The Head of Engineering takes accountability for the overarching document, disseminating accountability among the various document owners as appropriate. 

## Security and compliance guidelines
Not all stakeholders of a system will seek feature delivery; some are more concerned with nonfunctional qualities of a system such as security and compliance with specific controls (e.g., standards, regulation). The aspects requiring documentation include —

* **Requirements and policies**: How sensitive data is handled, stored, and transmitted.
* **Access control**: Procedures for granting and revoking access to systems and data.
* **Practices for managing sensitive information**, such as API keys and passwords.
* **Secure coding and logging practices**, ensuring that code is secure and free from vulnerabilities.
* **Artefact scanning tooling and processes**. This may be defined at both the source code and binary level.

**Document owner(s):** The requirements and policies for protecting data are sourced from stakeholders as well as overarching policies that apply at the organisation level, elicited by POs during the Abstraction phase. Engineering is responsible for implementing the abovementioned controls; the EMs must ensure that the security and compliance documentation relating to their teams' assets is current. Some security and compliance guidelines may also be defined at the practice level.

**Accountable party:** The Head of Engineering is ultimately accountable for the system meeting security and compliance controls, and for the completeness and accuracy of documents and other artefacts that demonstrate this.

## Onboarding guides
Much effort is routinely expended on assisting new starters in navigating an unfamiliar environment. While some of it is unavoidable, many activities can be streamlined through high-quality documentation that is kept up to date and readily on hand. Looking at onboarding from the viewpoint of a new starter, a handful of typical questions can be quickly answered with little more than a one-pager:

* At the organisation level: how do I make use of various corporate systems, email, VPN, time-sheeting, and so forth? This is almost entirely generic and typically provided by the corporate IT mob, along with the usual disclaimers. Engineering normally shouldn't be concerned with producing documentation of this nature, with the exception of small companies lacking a dedicated IT department.
* At the department level: what problems do we solve as a larger group? Again, documentation of this type will likely already be available in some form. It may include the usual history, mission, vision, values, and culture. There is little for Engineering to take ownership of here.
* At the system level: what are we building and where will my contributions fit in? This documentation may be furnished by multiple groups within the greater Engineering community:
    + The architects, responsible for system architecture documentation.
    + The engineering management, responsible for engineering principles, requirements, standards, conventions, and guidelines. This group includes testing and architecture managers, as new starters are not always developers.
    + The product team, responsible for the outline-level definition of the products supported by the system and how they dovetail into the organisation's broader product portfolio.
* At the practice level (if applicable): how will my contributions be guided by our choice of technology and ways of working? Technology-specific principles maintained by the relevant practice(s) will be useful here.
* At the team level: how do I become an effective member of my team? A bare-bones guide on how to set up their development environment, access code repositories and various tooling (e.g., CI/CD, log aggregators, team dashboards), and run the components locally will be useful.

Note that the detail of the onboarding documentation should be closer to a county map than to a village map. It should have links to more detailed documentation in specific areas. The immediate objective is to get a new team member to become aware to a point that they can discover on their own and ask for directions if necessary.

**Document owner(s):** The EMs and Head of Engineering for the engineering-level concerns; the Architects for the system architecture definition (a separate document discussed earlier); and the POs for product definitions.

**Accountable party:** The Head of Engineering.

## Software testing strategy
There is a saying that anything worth doing is worth doing right. To paraphrase within an engineering milieu: anything worth doing is worth testing.

Many of the preceding sections contained a point on testing strategy. And indeed, every process that is remotely important to the business should have some verification mechanism. How do we know that our backups work? Or that our disaster recovery processes can be trusted? You won't, not until you've tried them.

A clear, well-structured software testing strategy is essential for ensuring software quality. Ideally, it should be formed before major software development activities take place, even if the initial strategy may be defined at an outline level. A proactive approach allows for the identification and mitigation of potential risks early in the development cycle, ensuring that testing efforts are aligned with project goals and timelines. Additionally, a robust testing strategy facilitates better communication among team members, and ultimately contributes to a more predictable software development process.

Testing strategies are well outside the scope of this book. Many useful insights on software quality are offered by Ian Sommerville (2016) and Roger Pressman (2020). Also, the International Software Testing Qualifications Board (2018), IEEE 829-2008 (2008), and ISO/IEC 29119-1:2013 (2013) offer comprehensive guidance on the topic.

We only scrape the surface here, covering the bare essentials at an outline level. A software testing strategy may comprise the following elements:

* **Scope and priorities**. Not all aspects of the software may be tested rigorously, and some may only be covered at a surface level. Conversely, the critical aspects may require exhaustive testing. The functional areas that fall under the testing scope and their level of criticality should be assessed as part of forming the testing strategy. Testing incurs a measurable cost but the value it generates is often difficult to quantify. At minimum, the test strategy should justify itself qualitatively, demonstrating how testing resources and effort are attributed based on the relative importance of various functionalities to the business.
* **Separation of responsibilities**. Everything that will be built will be tested to a varying extent and by different people. At minimum, the engineering teams will be testing code at unit and component level, ensuring that both the functional and nonfunctional requirements of their deliverables are met. There will often be additional testing required at the integration level — attributable to delivery squads. However, the testing of the final product on behalf of its stakeholders will be conducted by a separate team. The testing strategy should explicitly define each of the roles in the quality assurance process, so that the expectations are clear and misunderstandings are avoided.
* **Test environments**, defining the needs of testing regime with respect to (physically or logically) isolated deployment environments and their infrastructure specifications:
    + For example, from an infrastructure standpoint, it may be that a test environment is a precise replica of production. This approach is certainly representative but it may fail to reveal the complete picture, especially when testing nonfunctional characteristics. What happens when the system has fewer resources at its disposal? Alternatively, how far can the system scale when pushed well beyond the workloads currently observed in production?
    + Certain "golden" data or configuration may need to exist in the test environments to allow for more representative testing. How will these data and/or configuration be reconciled with production as the two drift apart? Are they synchronised wholesale automatically or copied manually and selectively?
    + There may be multiple test environments required with different specifications. For example, functional testing typically does not require the same level of resource provisioning as nonfunctional testing. Also, user acceptance testing may be conducted in an entirely isolated environment to avoid conflicts and confusion among the two parties (dedicated system testers vs. users acting as acceptance testers).
* **Test design techniques**, specifying how the various parts of the system will be exercised:
    + For example, synthetic inputs may be fed to components and their responses asserted. This is a fairly conventional and battle-hardened method; it allows for an arbitrarily flexible test structure and maximises coverage, but makes many assumptions and may not be entirely representative of how a system is or will be used in production. Alternatively, instead of using fabricated data, previously observed production inputs may be sanitised before being fed to components. While this approach is inflexible and may limit test coverage, it is _a priori_ representative of a system's production use. A combined approach may also be used.
    + Some aspects of a system may be sufficiently critical to warrant more formal verification techniques, such as model checking or automated theorem proving. These types of activities require highly specialised professionals, are very resource intensive (people and time), and must be planned well in advance.
    + Some nonfunctional testing may require fault injection, repeatably simulating events that are rarely seen in production.
    + The test strategy should specify which approaches are used and where. It should be tied to specific objectives and explain how these are met by the chosen testing approach.
* **Tooling** used by those involved in the quality process, which may vary substantially between roles:
    + Software engineers typically use unit testing frameworks, microbenchmarks, and custom test harnesses because testing at this level follows a white-box approach. System testers will often exercise external APIs using standard load generation tools, treating the system as a black box. Security testing may take a middle ground, treating the system as a semi-obscure whole with some known internal details — the aptly named grey-box approach. Security testers typically use a standard array of tools targeting the system at various levels of decomposition, emulating both external and internal threat vectors.
    + Not everything is worth documenting, especially when standard tooling is employed. Everyone knows that Java developers will use JUnit, for instance. But if there are specific tools that need to be licensed or require additional skills training, the testing strategy should call them out.
    + Automated testing tools will likely be integrated with the CI/CD pipelines at some point. The details of the integration and the trigger points (e.g., push to feature branch, merge with master branch) should be documented.
* **Entry and exit criteria**. Some aspects of the system will be tested continuously, on every versioned change. These include units and components, typically running on developers' local environments as well as CI/CD. Integration tests and some performance tests fall under the same category, as they reside chiefly within the developers' province. Other testing may be conducted by specialists outside the engineering teams; for example, system testers, security testers, usability testers, and ultimately, the internal acceptance testing team, comprising business representatives. Where the software is developed contractually, the client may also have a dedicated (external) acceptance team, who will assess the system independently of the delivery organisation. Given the multitude of roles involved in the quality process, the following may require additional consideration:
    + When should testing commence? As a given, engineers will integrate and test continuously. Other teams may not be adequately resourced to attend every versioned change to the system, bearing in mind that not all changes are released individually. (Most releases comprise a set of changes; the can be tested as an atomic unit.) The idealistic approach of always testing everything may be infeasible. In some cases, resources may need to be booked in advance; e.g., penetration testing or the client's external acceptance team. Therefore, some testing steps may need to be serialised, contingent upon the outcomes of the previous step. The most expensive and laborious testing will generally come last. 
    + Specific criteria must be defined to guard the entry to each step. For example, third-party penetration testing should not be scheduled until every reported major defect is rectified.
    + The exit criteria for each step must also be defined. These criteria are generally a lot more straightforward for functional testing; for nonfunctional testing, a tolerance may need to be applied. For example, performance testing will be subject to variability, owing to a multitude of factors outside of our (reasonable) control. The acceptance criteria must be tuned to minimise the likelihood of false positives (rejecting adequately performing systems) without adversely impacting the likelihood of false negatives (accepting underperforming systems).
* **Change management**, specifying how changes to test artefacts (e.g., plans, scripts, pass/fail thresholds) are administered. Change management may remain largely informal in most commercial systems; the testing manager may selectively review and sign off on some of the larger and more impactful changes. Conversely, systems whose incorrect operation may incur loss of life, injury, or unmitigable losses of other kinds, will require more stringent change controls. Unvetted changes to the the acceptance criteria of a computed tomography machine, for instance, may have serious consequences for the patients.
* **Deliverables and communication**, identifying the expected outputs from the testing process, such as test plans, test cases, test reports, and defect reports, and how these are communicated to various stakeholders:
    + Developer-led testing (unit, component, integration, etc.) is exempt from explicit reporting requirements. If software fails a test, it will be changed until the test passes. (Not always; in some legitimate cases, it is the test that needs changing.) The metric that interests most stakeholders is the rate of development progress.
    + Testing administered outside of the engineering teams will generally report on its outcomes. This is not just to appease management and stakeholders; it forms an asynchronous feedback loop back to the engineering teams

**Document owner(s):** The delivered capabilities and the overall system will be tested by different people at different times. This includes Engineers, System Testers, Information Security, Compliance, as well as the system's end-users and customers. The testing concerns local to the delivery organisation will naturally be documented by the corresponding roles within. (E.g., EMs, System Testers.) External (to the delivery organisation) testing concerns will be documented by the Head of Engineering, who may delegate as appropriate.

**Accountable party:** The Head of Engineering.

## Responsibilities and accountabilities
Those who care about the efficiency and repeatable of the software engineering process may well find this to be the most important documentation of all. And they'd be right; it is the one that cannot be ignored, deferred, or substituted with a face-to-face interaction. It serves as an irrefutable contract between each member of the delivery organisation and their manager.

Responsibilities and accountabilities may be captured in a manner similar to how they were described in Chapter 6. One may even use this book as a staring point and elaborate from there. However, that mightn't be enough. A comprehensive set of "accountability contracts" should be supported by the following.

* **Clarifying the extent of their remit**: What each role is permitted to do and forbidden from doing should be called out explicitly; any grey areas will require coordination with their manager. Some of this may be implied in the responsibilities section. But not everything can be easily inferred:
    + For example, the "responsible for hiring and performance management" expectation from an Engineering Manager carries certain implications, but their extent may not be entirely clear. The details of performance management aren't within CONTROL's direct sphere of influence, although the overarching need for it has been highlighted repeatedly. The adopting organisation will likely impose specific constraints on performance management activities; some of these may be derived from legislation, others from internal policy.
    + Do not assume that if CONTROL omits some aspect of a role's expectation, then it is unimportant. Selective omissions (like the one in the previous example) avoid the overspecification of the method. Some effort on behalf of the adopting organisation will still be required.
* **Defining the means of assessing performance**: As per Chapter 4, accountability is ineffective if it cannot be assessed. Specific metrics or a qualitative approach will be needed to determine how a person is tracking according to the accountabilities defined by their role. The specific methods used to assess an individual's performance must be made transparent. These methods may well be subjective; nonetheless, team members should be given 
* **A negotiation process**: Accountability cannot be bestowed upon an individual without their acceptance of it. 
    + Some expectations may be defined in the employment contract; these tend to be highly generalised, fitting every employee. For example, ensuring the safety of a company's intellectual assets. In fairness, these are obligations<sup>3</sup> more so than accountabilities, but despite the distinctions their effects are similar. Engineering documentation shouldn't attempt to duplicate generic obligations, nor mimic the approach.
    + Many expectations are specific to a role. These should be communicated explicitly and documented for subsequent reference. It is little use agreeing to something when the basis of the agreement may later be contested by either party (those accepting accountability and those assigning it). This form of documentation should be subject to stringent change control measures; it cannot be altered without a bilateral agreement.

><sup>3 </sup>Obligations are legally binding and are defined in contracts or legislature. Also, unlike accountabilities, obligations are bidirectional. It is not only the employee who has obligations towards the employer; the reverse also holds. By comparison, accountabilities tend to compose hierarchically.

**Document owner(s):** The Head of Engineering.

**Accountable party:** The Head of Engineering.

* Interface schemas (for both synchronous APIs and asynchronous events or messages).
    + Focus on those schemas that govern cross-team interactions, more so than intra-team.
    + Cross-team interfaces are inherently more stable. Their documentation is less likely to change.
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
* Change management
* As-builts vs designs
* Testing strategy
* Roles and accountabilities

* Don't document too soon, before the feature is stabilised
* The best documentation is the kind that doesn't have to be written:
    + Self-documenting code
    + Standard and idiomatic design and coding practices
    + Convention over configuration
    + Patterns and guidelines
    + Use of off-the-shelf libraries or components
* Prefer high-level documentation to low-level. For an explorer who doesn't know where to start, a map of a county is better than a detailed map of one village.
* Convey the context where possible.
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



The above is not meant to be an exhaustive list.

# Chalk outlines
There are three recommendations in this chapter that do not conform to mainstream thinking. At least, it does not conform to mainstream acting.

The first recommendation is that documentation ought to address the "third audience" — the present self. The general consensus within the software community is that documentation should elucidate others and the future self. Within the majority opinion, documentation is a form of communication, no more, no less.

Writing fosters a process of self-reflection, identifying gaps in our subconscious reasoning; subtle gaps that are our intuition may be oblivious to. Writers have known this for centuries and philosophers for longer still, and yet there are many engineers who fail to recognise writing as an extension of thinking.

Documentation is an essential artefact in the software engineering process. It is also a distinguishing factor between software engineering and mere programming. If one were to treat software engineering as a structured process rooted in a scientific discipline, then repeatability would presumably be a factor of some importance. Especially if one subscribes to Newell and Simon's viewpoint (1975) that each new piece of software is an experiment. It is hard to imagine experimental repeatability without some form of documentation.

Yet I do not indulge in documentation and do not expect others to. The topic is nonetheless close to my heart. As a part-time author, it is the writing that I find constructive. Having written several books, and peer-reviewed academic papers on various computer science topics, not to mention random blogs and work-related pieces for my clients, I can attest to the effectiveness of introspection via the written word. The same applies to my journal-keeping experience; many of my thoughts have never been shared (which is perhaps a good thing) but in their writing they have been scrutinised. (And some debunked.) I am, without doubt, my most formidable critic.

The second recommendation is that documentation should be used as a medium for answering questions.//TODO

The third recommendation is to never delay studying a topic whose understanding is pivotal to your future success. Do not fall into the trap of instant gratification. Don't ask a question before you have convinced yourself that the answer is not already at your disposal. Read the friggin' manual. Taking the time to study a subject thoroughly will offer answers to many questions not yet asked.

Everyone learns from their mistakes eventually but the more intelligent learn from the mistakes of others.

# Summary
The goal is to create a clear and concise overview that sets the stage for understanding the system in more detail. It's about providing enough information to get a sense of the system without getting bogged down in specifics.
