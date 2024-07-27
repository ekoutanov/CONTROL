*Chapter 10. Recommendations
---
**WORK IN PROGRESS**

//TODO intro
Non-core aspects of CONTROL.

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

The third audience group is almost entirely ignored from the documentation rationale. Those previously engaged in either professional writing or scientific research activities involving volumes of written material will understand precisely what that means. I will explain it best I can.

It may have been Leslie Lamport who first said that "writing is nature's way of telling us how lousy our thinking is." When we contemplate a problem, we feel it, we react to it. Much of the solution may be drawn from intuition — humans' innate ability to understand instinctively without involving conscious reasoning. For example, when a programmer is asked to print the first 100 natural numbers, she will naturally visualise the snippet `for (int i = 1; i <= 100...`; very little conscious thinking takes place.

Intuition is powerful because it enables us to solve complex problems without dwelling on the minutiae. It serves as a mental abstraction. Programming is challenging enough with intuition aiding us; if every line required meticulous deliberation and induced self-doubt, the process would be incredibly arduous. While it's typical for beginners with little command of a programming language to scrutinise every detail, it's unthinkable for seasoned programmers. This development of intuition significantly impacts productivity.

Like many powers, intuition is also dangerous. It can lead to decisions that lack rationale but appear sound and remain unquestioned in our minds. The programmer may inadvertently focus on the most complex parts of the program while churning out the rest on autopilot.

It is not only the trivial parts that are derived intuitively. Complex solutions may too be distorted by misguided intuition. A common example is ignoring edge cases when designing distributed applications. Many engineers gloss over the effects of failures on the state of the system, leading to inconsistencies that are difficult to identify and resolve.

When we write, we are forced to rationalise and explain to a virtual audience. We use language and images to convey our thoughts. Called to write on a topic, we often realise how flawed or incomplete our thinking had been. We summarily revisit the solution — fill the voids or redo it altogether. We then resume documenting. It is a structured, orderly process.

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
* **Adopt idiomatic designs and best-practices.** The maintainers of many technologies and programming languages, as well as the broader community of adopters, often advocate for consistent, if somewhat opinionated approaches to tackling common problems. Industry-standard approaches should be favoured over homebrew where possible.
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
Some knowledge will invariably remain in tacit form. It is, nonetheless, irresponsible to say that we should accept this as a factor beyond our control. There is more within our control than we care to admit. The question is one of priority. It may not be practical to document everything and do so exhaustively. One must, therefore, choose which aspects of the system should be documented and at what level of detail. Where should you begin?

Here, we consider the most important aspects of the system whose documentation cannot be neglected. At minimum, the following should be put to paper.

## System architecture
Imagine the system as a complex puzzle. The high-level architecture is like the box of the puzzle that shows a simplified version of the completed image. It provides a broad overview of the system's structure and the principles guiding its evolution. It identifies the key components and their relationships, and explains how those components and the system as a whole may change over time. At a minimum, architectural documentation should contain the following elements.

* **Introduction**: Describes the purpose and sets the context, guiding the understanding of the other architectural elements that follow. Ideally, it should also bind the scope of the document and specify its target audience. A glossary of common terms may also reside here.
* **Subsystems and components**: These are the fundamental parts of the system described at a coarse level of granularity. 
    + In large systems, subsystems are generally the next level of decomposition. They are essentially smaller systems with interesting architectural elements of their own. Architecture documentation may comprise just the subsystems or both the subsystems and the underlying components, depending on the level of detail one is willing to convey. When describing two (or more) levels of decomposition, it is best to split documentation into multiple parts to not overwhelm the audience with excessive upfront detail.
    + In small systems, it is the components that generally make up the systems directly.
    + Diagrams are invaluable tools to communicate complex information effectively. Annotated component diagrams can convey much of the essential complexity without excessive verbosity.
* **Interactions**: The interactions between key elements can be depicted using both static and dynamic views, showing not only their relationships but how the elements collaborate during specific work flows.
    + Focus on the interactions between the elements at the coarsest level of granularity; i.e., define how subsystems relate to and interact with each other.
    + Only once the coarse-grained interactions are captured should refinement occur.
    + Sequence diagrams, collaboration diagrams, and data flow diagrams are useful here.
* **Boundaries**: A system is rarely deployed in isolation; it often interfaces with other systems and end-users. Which other systems? Which users? How do they interact with the system? Via which interfaces? It is easy for an architect to assume that everyone knows such basics but these are the sorts of questions that an entry-level audience comes up with.
* **Team ownership**: Understanding who is responsible for each part of the system is essential for collaboration and accountability. Subsystems and components will be built and supported by engineering teams. Knowing which teams are responsible for specific elements of the system allows the audience to reach out to the teams in question in pursuit of further inquiries.
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

>The distinction between components and subsystems is purely notional in many texts. They are a granule of functionality with well-defined boundaries. Nonetheless, I distinguish among them using the following heuristic: a subsystem is a system in its own right, albeit a smaller one. Being a system, it has architectural concerns that may vary greatly from its peer subsystems. Subsystems derive from the overall architectural principles of the overarching systems but may add principles of their own; those principles may be unique and highly specialised.
>
>Imagine, for example, a sports wagering system. In a very simplified form, it comprises 1) an _offering subsystem_ that processes various market feeds and calculates the betting odds, and 2) a _betting subsystem_ that takes customers' bets, assesses their exposure risk, and settles the winners. Each subsystem comprises multiple components; in other words, each is interesting architecturally. The two subsystems have very different nonfunctional characteristics. The offering subsystem must process large volumes of data with low latency, but it is unconcerned with transactions and may operate under relaxed consistency constraints. The betting subsystem deals with lower volumes but must preserve strict transactional semantics as it deals with customers' money. Each subsystem is heavily specialised. It is, therefore, conceivable that each requires a unique set of principles and guidelines. They may be built using different technologies, employing different skill sets, and are thus likely owned and operated by different engineering teams.
>
>In comparison, the components that make up one (sub)system will have much more in common. They are generally built using similar technology and follow identical principles.

The above is not a complete list of architectural aspects, but I believe it to be sufficient for most systems. Some architecture frameworks may require more viewpoints and advocate proprietary modelling notations. The Open Group Architecture Framework (TOGAF), for example, is keen on business process views (The Open Group, 2018), which are immensely useful for many kinds of business work flow systems.

The high-level architecture of the system is the equivalent of the national map in the "prefer breadth of documentation to depth" principle. It gives its explorers a place to start their journey.

## Engineering principles
While the overarching system will evolve according to a set of architectural principles, the implementation of elements will be subject to a further set of engineering principles. These are produced at varying levels of decomposition. At the top-most level, engineering principles govern the complete engineering organisation; in other words, they apply equally to all teams or practices that operate under the engineering umbrella. In turn, each engineering practice or team may have unique principles of their own.

Teams differ from practices. A team is a group of professionals working together to achieve specific goals. A practice is a grouping of people based on common characteristics, such as methods or ways of working.

Consider an example: A company has three cross-functional engineering teams, comprising both front-end and back-end developers. The teams look after three separate customer experience verticals: shopping cart, product catalogue, and account management. Simultaneously, the company operates separate practices for front-end and back-end technologies. The company has a common set of engineering principles, covering such crosscutting concerns as logging and security.

In addition, each practice lays down specific principles relating to their respective technology stacks and preferred ways of working. The front-end practice is mostly concerned with the development, versioning, and deployment of React components. Conversely, the back-end practice sets guidance for the development of Java applications, including the design of REST APIs and the use of object-relational mapping frameworks. Each drives consistency and excellence within the engineering aspects under its purview. They can incubate new ideas and techniques, and ensure that the organisation's technology portfolio evolves sustainably.

>Most engineering organisations feature multiple engineering teams but only few commit to engineering practices. I believe this to be a missed opportunity, especially considering the ease with which a practice may be spun up and their benefits relative to cost. For starters, it's an informal group that can be truly self-organising. While teams are managed by accountable individuals, practices may be run in more egalitarian ways. Individuals' participation in practices may take active or passive forms, depending on their interests and available time. In addition to the obvious benefits of driving consistency and promoting overall excellence, they offer a club-like experience for their members. Practices support their members and help smoothen the new-starter experience. They can heighten the individuals' sense of belonging and provide a platform for continuous learning, fostering a culture of collaboration. They can also set the scene for mentorship, allowing more experienced engineers to share their knowledge and help junior members grow.

Finally, some engineering teams may adopt principles of their own. For example, the account management team benefits from a consistent, if opinionated approach from its team members regarding the storage and transmission of personally identifiable information (PII). Crucially, principles local to teams and practices mustn't conflict with higher-level principles. In our example, the team's principled handling of PII must be in line with all security principles codified at the engineering and architecture levels. Remember, if a pair of principles contradict, one or both are incorrect or misinterpreted. Clarifications or amendments may be required.

Principles should be documented close to their intended audience and readily accessible. When using a wiki, for example, the team principles should be contained in the team's local space. The responsibility and (in most cases) accountability for defining and maintaining principles rests with those managing the intended audience. For example, the Head of Engineering maintains the engineering principles, while the Engineering Manager handles the principles for their team. Delegation is possible and sometimes necessary. Practice-level principles are maintained by either the practice lead, the seniormost member, or the complete collective, depending on the chosen structure and conventions. There may not be a single person accountable for a practice. It is chiefly for that reason that engineering practices and centres of excellence are not part of the CONTROL delivery organisation, although their presence is encouraged.

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

Much like engineering principles, these specialised rules can be established different levels of the engineering organisation and further refined by the team or practice dimension. Those in charge of the principles also curate the more specialised rules at the corresponding level.

## Team inventory and as-builts
Enumeration of the intellectual assets of each engineering team, detailing the items under each team's care. Some of these assets may have already been captured by the system architecture at an outline level. The team-level documentation offers a more detailed account.

Architecture documentation tends to hover at the level of ideas, concepts, and abstractions. This is great because it hides unnecessary detail and conveys an at-a-glance appreciation of a very broad landscape. When detail is sought, one may find it by consulting more specific documentation at the subsystem level. However, the risk with all architecture documentation is that it tends to be produced by those who envision an ideal design void of compromises.

 without the examination of the underlying detail.

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


Note that the detail of the onboarding documentation should be closer to a county map than to a village map. It should have links to more detailed documentation in specific areas. The immediate objective is to get a new team member to become aware to a point that they can discover on their own and ask for directions if necessary.

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

Principled Decision-Making
---
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