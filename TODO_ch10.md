Chapter 10: Principled Decision-Making
===
**WORK IN PROGRESS**

# Into the 'Matrix'
We've all seen this before. The architect<sup>1</sup> is deliberating among several shortlisted solution options. She writes down their pros and cons:

|                          |Solution 1        |Solution 2        |Solution 3        |
|:-------------------------|:-----------------|:-----------------|:-----------------|
|Description               |API-driven order processing.|Event-driven order processing with broker-side pre-filtering and routing.|Event-driven order processing with consumer-side filtering.
|Pros                      |• Quick to implement, requiring few changes to the existing system.|• Scales to increased loads and has no points of failure.<br/>• Quick to implement, requiring few changes to the existing system.|• Scales to increased loads and has no points of failure.<br/>• Relies solely on open-source technology.
|Cons                      |• Doesn't scale to increased web traffic.|• Requires proprietary technology.<br/>• Cannot be easily deployed on the public Cloud.|• High change impact, risking cost blow-outs and late delivery.

<sup>1 </sup>Architects are picked on here because they're responsible for more than their fair share of poor decisions. The example applies equally to all decision-makers.

The benefits and drawbacks of each solution are numerous and substantial; they do not seem to separate the good from the bad. A game of trade-offs is afoot. The architect responds by assigning weights to each factor; these have been gathered through consultation with various stakeholders — business and technical alike. Unsurprisingly, costs and schedules have attracted the most attention, followed by reliability and scalability. One technical stakeholder expressed concerns regarding the potential lock-in effects of adopting proprietary infrastructure. The stakeholders' collective opinions were encoded on an ordinal scale of one (least important) to five (most important).

The responses (i.e., the pros and cons) of each solution were also scored on an ordinal five-point scale (1–5), signifying their contribution to the factor in question, ranging from strongly negative to strongly positive. The weighted average score of each solution was then computed by taking the product of the factors' weights and the response scores and dividing by the number of product terms. The following table presents the weights, response scores, and the results of the calculations.

|Factor                  |Weight|Solution 1<br/>responses|Solution 2<br/>responses|Solution 3<br/>responses|
|:-----------------------|-----:|---------:|---------:|---------:|
|Reliability             |     4|         3|         5|         5|
|Scalability             |     4|         2|         5|         5|
|Cost & schedule impacts |     5|         4|         5|         2|
|Nonproprietary          |     2|         5|         1|         5|
|                        |      |          |          |          |
|**Weighted average**    |      |  **12.5**| **16.75**| **16.25**|

Solution 2 edges out Solution 3, while Solution 1 is obviously a no-go. However, the architect is unconvinced. There is an inkling that despite everyone's best efforts, the outcome is too close to call. So, she spends time elaborating each solution and presents her analysis to the stakeholders, along with her professional recommendation — Solution 2. It is voted in, almost unanimously. In discussing their choice, many panelists again stress the resourcing and scheduling angle.

While the example above is entirely fabricated, it is an incontrovertible fact that a myriad of analogous decision-making challenges bestands practitioners daily. Not just architects and, most certainly, not just technical people. You'll have seen it at work and at home. And many times over, I'll wager. In making important decisions, our confidence is boosted as the separation among decision options grows. The more the favoured option eclipses its competition on some scale, however subjective or arbitrary, the more comfort is instilled and the stronger the sense of decision integrity. 

When the solutions cannot be separated cleanly, we respond by tweaking. Minor adjustments are made to weights and scores to enhance separability. If that fails, we may revise the criteria entirely; perhaps there are other factors that we failed to consider. There is an infinite number of matrices of factor weights and response scores that yield adequate separation. And yet we only need one such matrix to reach a conclusive decision. With a bit of creativity and determination, it will be found.

It's not always smooth sailing, of course, and our scenario exemplifies this. When all else fails, we abdicate the decision-making responsibility. In other words, we pad out the solution with enough context and hand it over for our stakeholders to decide. And who better to make the final call? They are, after all, maximally impacted by it.

The above technique (sans the abdication part) is called a Weighted Decision Matrix (WDM). It is sometimes referred to as the Pugh Matrix, after its inventor — British product designer — Stuart Pugh (1981). It is among the most commonly used structured decision-making frameworks, appearing prominently in fields like Engineering, Information Technology, Product Development, and Project Management.

The sorts of weighted scoring methods like WDM are easy to formulate and teach. They are also easy to practice and explain to stakeholders. It is thus unsurprising that they have become widespread. Large and established organisations like the U.S. Army (van Vactor, 2009) and the U.S. Department of Health and Human Services (2007) have also indicated their use in decision-making.


# The glitch
I'll state this now without any reservations or caveats: Pugh's method doesn't work in the real world<sup>2</sup> and never has.

><sup>2</sup>There are many other methods within the multiple-criteria decision analysis (MCDA) family but the Pugh/WDM approach seems to dominate practical applications outside of scientific research (Evans & Hubbard, 2010). We discuss it here because of its prevalence and the dangers of its use.

The problem is not with the calculation method, which is mathematically sound and _appears to be_ straightforward. It is with our inherent inability to satisfy the underlying assumptions; namely, that within some margin of error, the factors are complete, their weights are accurate and uncorrelated, and the scores are objective. Consider the challenges:

* **Subjectivity of quantification**: Most of the factors being assessed are qualitative. Their quantification is a matter of opinion, and yet their effects are profound. For instance, reducing the "cost and schedule impacts" from five to four would have tied Solutions 2 and 3. Taking it down to three will have crowned Solution 3 as the victor.
* **Incomplete factor selection**: The selection of factors is biased by the analyst. Why was the earlier example limited to four factors? Maybe they were important to her. Maybe she was influenced by her stakeholders. Or maybe she simply overlooked them.
* **Tweaking**: We expect the method to yield an outcome; a tie or a handful of closely matched outcomes will not do. Because the analysts accept the subjectivity of quantification, there are no moral or ethical inhibitors stopping them from tweaking the numbers or moderating these tweaks in any way.
* **Confirmation bias**: Extrapolating from the previous point, we instill comfort into the separability of solutions. A clear and uncontested decision outcome creates instant satisfaction with the process, to the effect that we stop questioning the inputs. We accept the decision and move on. Challenging the inputs would likely muddy the weighted averages, decrease separability, and erode our confidence in the outcome.
* **Illusion of objectivity**: An _a priori_ subjective decision method telegraphs its limitations from the outset. Conversely, a process containing some maths and copious evidence of analysis may appear to stakeholders as objective; in reality it may be cook up.
* **Illusion of precision**: In our example, the weighted averages were precise to four significant figures for two of the solution options. However, the least precise factor in the calculation had only one significant figure. According to the rules for calculations with limited precision, the final outputs should have also been presented to one significant figure. The three options would have scored 10, 20, and 20, respectively, making the last two inseparable. In practice, however, hardly anyone considers the limitations of precision when performing such calculations<sup>3</sup>. And most people interpreting the results will not question the calculations because of how simple they appear to be.
* **Assumption of independence**: The calculation is sound only when all factors are independent of each other, which is not always the case. Consider a pair of factors — "change impact" and "maintainability". The former favours simpler solutions that impact fewer areas of an existing system. The latter is also negatively correlated with complexity. Simple solutions score well against both factors, amplifying their scores beyond reason; equivalently, complex solutions are doubly penalised. This problem can be mitigated by vetting factors for correlation<sup>4</sup>.
* **Waste of effort**: Illusion of objectivity doesn't come cheap. Each option must be analysed with enough rigour to permit the quantification of its response scores. Ultimately, one solution will be chosen; the others will be consigned to history.
* **Permissiveness**: The solutions are not eliminated, only graded. The method will, therefore, find one solution to be superior to the rest (although some tweaking may be required for separability). What if they're all bad? This tendency to accept all solutions may be mitigated by assigning cutoff tolerances to each of the factors, rejecting "bad" solutions from the outset.

><sup>3 </sup>The process can also be gamed. Instead of quoting scores and weights to one significant figure, an extra decimal or two of precision can be added; for example, writing the "scalability" weight as 4.00 instead of 4. For enhanced legitimacy, the factors and weights can be tweaked slightly, like 4.25 instead of 4.00.

><sup>4 </sup>Experience suggests that this is often gets neglected. Sadly, there are no good empirical data reporting the effects of poor decisions resulting from correlations in decision weighing.

In distilling the above, I suggest there are two congenital flaws with this method, both unmitigable:

1. **It's irreproducible.** The multiple sources of subjectivity and cognitive biases present in the application of the method imply a high likelihood of a pair analysts reaching different outcomes, even if equipped with similar knowledge, skills, and problem context.
2. **It's unstable.** Small changes in response scores and factor weights can lead to radically different outcomes.

In a study of risk assessment methods, Dylan Evans and Douglas Hubbard have expressed concerns on the mainstream use of techniques that rely on scoring and ordinal scales, such as WDM. According to the authors (Evans & Hubbard, 2010), "The widespread use of scoring methods in real-world settings is still a serious problem that needs addressing, and these methods are beset by many flaws aside from the mathematical ones." The only "evidence" that exists in their favour comprises testimonials from satisfied users. The authors suggest that these methods have likely proliferated based solely on their perceived benefits and, in fact, have no objective value. These methods are rarely evaluated rigorously and "persist despite their uselessness and even harmfulness." (Evans & Hubbard, 2010)

>If Pugh's method breaks down in the real world (of human fallibility), where does it work?
>
>As stated earlier, the challenges are mostly in satisfying its assumptions. When factors and scores are complete and can be quantified accurately and precisely, the method is useful. Variations of it are, in fact, employed in the applications of machine learning and neural networks. These are heavily reliant on linear algebra (vectors and matrices); internal weights and biases are learned progressively through objective calibration (e.g., training) and scores are readily quantifiable model inputs (e.g., pixels).
>
>Well... To be pedantic, it is the other way round. Classification methods based on linear combinations of weighted factors and inputs have been been known for many decades before Pugh took them to problems involving ordinal scoring. In machine learning specifically, these algorithms existed since 1943, invented by Warren McCulloch and Walter Pitts. (They were not implemented in hardware until 1957, however.)

It is also worth remarking on the involvement of nontechnical stakeholders in technical decision-making. Although this practice is not, strictly speaking, formally a part of the Pugh/WDM approach, it is commonplace regardless. The typical reason is the lack of confidence in the would-be decision, and the resulting need to have that decision (or another) legitimised by people with skin in the game. This seems prudent on one hand — involving those immediately affected would suggest a better outcome quality, surely! The problem, however, lies in their (in)ability to make such decisions. Furthermore, when the decision-making process is expanded to a consortium of stakeholders, the resulting committee-led decision confuses _consensus_ with _correctness_. When more people agree on something they barely understand, it doesn't make the decision any more sound. And finally, nontechnical stakeholders deciding on technical items gives rise to a conflict of interest: decision-makers will likely be incentivised by costs and schedules, rather than important nonfunctional considerations such as maintainability and supportability.

# The red pill
A police detective is looking to charge a felon with a minor offense. The charge carries a minimal penalty; if it stands up in court, that is. It requires witness testimonies, evidence gathering, and paperwork. And importantly, there is a mountain of more pressing case files that need getting through. There are "proper" murderers and rapists to rid the town of. So, what does he do?

Well... He doesn't flesh out a Pugh matrix or conduct a cost-benefit analysis. He doesn't put the matter up for a vote among his colleagues, nor does he abdicate the decision to a more senior officer. He simply does what he has been trained to. It mightn't _appear_ to be the best use of the detective's time<sup>5</sup>, but the decisions he makes are grounded in a set of principles instilled in him since joining the force.

><sup>5 </sup>For law enforcement professionals like detectives, principled decision-making guarantees actions are taken in accordance with the law and ethical standards, rather than being influenced by personal biases or external pressures. When certain crimes are consistently prioritised over others (for the sake of metrics or reporting), those that are constantly denied investigative effort will effectively become unpunishable, thereby encouraging their perpetration by criminals.

Principled decision-making is the method by which we tackle "fuzzy" problems lacking a logical or analytical solution. It works for straightforward problems as well as those with difficult to quantify criteria and responses, and poorly separable outcomes. It is the very method upon which CONTROL is founded.

Decisions are guided by a consistent set of values, ethical standards, and established principles, rather than by convenience, expedience, vote, emotional impulse, stakeholder opinion, popular sentiment, "gut feel", personal "favour", misguided pragmatism, or faux objectivity<sup>6</sup>.

><sup>6 </sup>Like trying to quantify the unquantifiable or drawing on superficial metrics. Or willfully plugging oneself into the Pugh matrix.

Principled decision-making works by rapidly eliminating solution options, assessing each against an _a priori_ set of principles<sup>7</sup>. In our original example, Solution 1 would have been culled quickly if the architect had considered the principle "Favour message-driven communication patterns in asynchronous workflows." Similarly, Solution 2 would have fallen to "Favour open, standards-compliant, accessible, and interchangeable technology and skills." Importantly, the options wouldn't have required comprehensive elaboration — they would have been summarily dismissed at the outline level. Much effort would have been saved.

><sup>7 </sup>Other criteria, such as values and ethical principles, we treat synonymously with principles for convenience.

We say that the method works by elimination, but it can also be made to work in reverse — by synthesis. In our example, the three solutions were developed and refined _independently_ of the decision-making method. But it doesn't have to be this way; solution development may _actually_ be guided by the principles, provided the analyst is well aware of them (which they should be). Knowledge of the two aforementioned principles could have yielded a good solution (or several), _a priori_ compliant with the principles.

A notable challenge with the principled approach is the treatment of various "red herrings" that may be separating solutions in other dimensions (orthogonal to the principles). The solution options contrasted change impacts and their effect on cost and delivery schedules. Should we fabricate new principles to deal with time and cost? "Favour the cheapest solutions," perhaps?

Absolutely not. Schedules and costs are _constraints_; they do not factor into principled decision-making. _Engineering is accountable for the quality of all software artefacts within its remit._ Since accountability is ineffective without authority, Engineering must have the final say in the quality of all solutions it commits to. Assuming schedules and costs are roughly immovable, the business stakeholders (via the Product team) have a say on scope. If, for instance, a compromised solution _X_ impacting just one team is inadequate in the quality dimension, while a high-quality solution _Y_ impacting three teams is costly, then the Product team has precisely three choices:

1. Pick _Y_ with its original scope, adjusting budgets and schedules accordingly.
2. Pick _Y_ with a reduced scope. Once the product gains traction, the complete solution may be delivered later as a separate initiative.
3. Do nothing.

Regardless of the choice made, Engineering will be in a position of guaranteeing the maintainability and supportability of the system. Note, this doesn't imply that the system _will_ be maintainable and supportable, only that Engineering alone will be held accountable over these obligations. They cannot, for example, later refer to being coerced into a pathway outside their ability or willingness to maintain and support. In other words, the approach does not provide iron-clad assurances, only opportunities — by promoting ownership and discouraging blame. At the other end, the Product team will know upfront what they are signing up for. They will have confidence in that the product will not come unstuck after its release. In turn, they can make more realistic promises to their stakeholders.

Consider the benefits of principled decision-making:

* **Consistency and reproducibility**: Decisions made under this approach are uniform across similar situations because they adhere to a stable set of guiding principles. No other factors are considered. And there are no quantification uncertainties, internal correlations, or numerical precision effects to contend with. Given a common set of clear and unambiguous principles, a pair of seasoned analysts (well-trained in the method) will likely arrive at similar decisions, even if they may not always agree.
* **Integrity**: In environments where there might be a temptation to take shortcuts, pressure to achieve results at any cost, chase short-term goals, or favour one vendor of another (or open-source, for that matter), the enhanced traceability offered by a principle-led method natural leads to more integral decisions.
* **Accountability**: Because decisions are grounded in well-defined principles, it becomes easier to hold decision-makers accountable for their actions. They cannot easily shift blame or justify poor decisions by external factors because the decision-making process itself is transparent and its outcomes must be justifiable.
* **Long-term perspective**: Where principles are focused on long-term benefits to the organisation, decisions made according to those principles will be equally conducive to the long-term goals.
* **Stability**: When solutions are assessed numerically, small variances in the quantified parameters (factors or responses) can result in flip-flopping between closely-matched outcome. In a principled approach, small variances in the interpretation of principles or solution responses are unlikely to alter the outcome drastically.
* **Efficiency**: Effort on assessing extraneous solutions is minimised as most poor solutions can be eliminated at the point of conception. Instead, effort is channeled into those solutions that conform with the principles from the get-go.

No method is flawless or universal, and this one is certainly not without its drawbacks and limitations:

* **An implicit reliance on the soundness of principles.** Without a set of principles that is clear, efficacious, relevant, nonconflicting, and complete, decision-making is rendered impotent. Solutions won't be guided by anything useful. Decent solutions may end up being rejected on esoteric grounds.
* **Requires skilled subject matter experts to interpret principles correctly and assess solutions objectively.** Principles are generally conveyed abstractly, maximising their breadth of application. They are not spelt out for every conceivable problem that might fit their use. It takes skill and experience to place them in the right context and refine them to the matter at hand.
* **All options may be eliminated.** It is a sobering reality that, once subjected to a set of rigorous criteria, all candidate solutions may be deemed noncompliant, leaving the analyst empty-handed.
* **Some options may be inseparable by principles alone.** While noncompliance may eliminate some candidates, the remaining may be equally compliant with the principles. This will leave the analyst with several options, requiring further analysis (and judgment) to isolate the optimal solution.
* **Political pressure to accept compromises.** Principled decision-makers might face significant pressure to compromise their standards, particularly in highly competitive or politically charged environments. It takes resilience and strong moral character to maintain integrity in such situations.
* **Perception of rigidity.** Adherence to principles can sometimes be perceived as rigidity, inflexibility, or stubbornness, especially in "dynamic" environments where adaptability and "pragmatism" are valued.

Let's digest the above.

It should not come as a surprise that a principle-centric method is heavily predicated on the quality of the underlying principles and the expertise of the practitioners who apply them. This reliance, without question, represents a limitation. Alternatives that require minimal upfront investment (in formulating principles) and place fewer demands on the analyst may seem preferable to many industry "experts". On the flip side, the failure to meet these requirements signals something far more concerning. An engineering organisation that struggles to formulate the binding "fabric" to safeguard the quality of its most significant and enduring decisions, and that is unwilling to cultivate its people's skills or promote its most merited talent (over, say, the best team players), will steadily drift toward the inescapable event horizon of the "software crisis."

The elimination of unsuitable options is a good thing. The elimination of _all_ options, while a major inconvenience to the analyst, is nonetheless good in the grand scheme of things. It highlights gaps in the design process, indicating that the organisation's standards exceed the quality of the solutions being considered. One must change or the other, and the lowering of standards is generally ill-advised.

Assuming that the principles are sound, the inseparability of some solutions by principles alone means that several "good enough" solutions have been elicited. It thereafter becomes a matter of determining the best among them, using any number of methods in the analyst's toolkit. Even methods that rely on weighted scoring may be employed to good effect, albeit with caution — to avoid the pitfalls described earlier. The cost of errors would have been reduced substantially — the principled decision-making method acting as safety net of sorts.

Regarding the political pressure to accept compromises or the perception of rigidity — both are evidence of an undisciplined or short-sighed approach to decision-making in the benign case and, in some cases, more systemic problems with the organisation's leadership and culture.

>Writing about the perception of rigidity reminds me of a certain senior executive. Let's call him James. An impeccable knowledge of the product domain was complemented by a solid technical background. A well-respected and much admired leader, James was famous for his "pragmatic" decisions. He'd eagerly get involved in heated discussions (not always but usually technical), cutting through the rhetoric of the feuding parties with simple questions like "How does this benefit the customer?" Notably, his interventions were done with utmost respect and gallantry. People did not feel as though they were being talked down to.
>
>Over time, James grew bored with his official role, which wasn't as close to the coal face as he would have liked. He reminisced of the old days. He became more engaging in Engineering's routine decision-making processes, injecting himself into discussions where he was neither needed nor, frankly speaking, welcome. He used his pragmatic lens to steer decisions in favour of short-term outcomes and cut corners to that effect. In his mind, however, he was helping Engineers solve problems they otherwise struggled with. In their mind, he was a royal pain.
>
>This story offers two lessons: 
>
>1. Pragmatism's practical focus can be immensely useful when cutting through red tape or combating "analysis paralysis". When decision-making becomes bogged down in endless discussions or theoretical debates, a pragmatic approach that homes in on tangible outcomes can help move things forward. But used indiscriminately, pragmatism leads to superficial, short-term solutions that address symptoms rather than root causes, favouring decisions that are expedient but not necessarily sustainable. Pragmatism is also highly subjective, fraught with personal biases, and inconsistent and irreproducible as a result.
>2. Weak decision-making regimens hinder progress, attracting external participants and opinions. While such interventions may be well-intentioned, they can disrupt the normal workflow, undermine trust in people, and contribute to a more frenzied and uncertain work environment. Ultimately, the result is a less confident team, whose weaknesses are amplified instead of being attenuated. A team that is increasingly more dependent than empowered.

# Defining and communicating the principles
Principles form the backbone of all decision-making within a CONTROL delivery organisation, in much the same way that CONTROL is built on foundational principles of its own. The availability and soundness of the principles is paramount to the quality of the decisions, as well as people's ability to interpret and apply these principles masterfully at various levels of the organisation. Well-crafted principles —

* Provide clarity and direction;
* Guide consistent decision-making;
* Foster a shared understanding and language; and
* Support empowerment and accountability.

Principles should be drawn up at the very start of a software project, alongside if not before the initial sketches of its conceptual architecture. Just as the construction of a building begins with blueprints, the architecture and engineering principles serve as the blueprints for the development of a software system. At the outset, it is usually the senior-most technical decision-makers who are involved in defining the principles — Architects, Engineering Managers, and the Head of Engineering.

Principles cannot be communicated (only) verbally. _They must be written down and made available to all key decision-makers._ While Chapter 11 discusses documentation in a lot more detail, we will jump the gun here slightly to get a taste of how principles might be described.

We begin with an opening statement. It introduces principles and explains their importance.

_Our core principles are the essential building-blocks of the product and engineering culture. They help form a set of common values and beliefs that influence how we organise ourselves, collaborate, grow, develop sustainable solutions, reinforce good behaviour, and work with key stakeholders. Culture is a lot more than just a handful of principles, but we won't succeed without them._

## Primordial principles
Not all Engineering principles directly relate to the system being developed. One principle, in particular, is the cornerstone of all principles and yet is the most agnostic of all. It is the self-referencing principle that every decision draws on principles.

---

### Primacy of principles

Principles are the prevailing decision-making criteria within the organisation.

* An outcome supported by an established principle is favoured over an outcome that is neutral to, or contradicts a principle.
* Without principles, we will not maintain conceptual integrity and will struggle with consistent and repeatable decision-making.

---

The principle of _personal accountability_, for instance, is also classed as primordial. It exists well in advance of the system being contemplated, let alone architected. Many of the more specific principles are founded upon it.

---

### Personal accountability

Performance is in our DNA, and _accountability is the main mechanism by which performance is achieved_. Accountability must be clear, uniquely attributable, within the individual's control, and measurable. 

* A well-designed accountability model should balance holding individuals accountable with providing necessary resources and support, ensuring clarity, fairness, and psychological safety. 
* The accountability model fosters motivation, ownership, and improved performance, reducing turnover.
* Accountability composes hierarchically: managers delegate responsibilities and assign specific accountabilities to their direct reports, while retaining accountability for overall performance.

---

## Behavioural principles
These principles influence the behaviour of the members of the delivery organisation. While they might not refer to technology directly, they ensure that people's actions contribute to the best possible outcomes for the system and its stakeholders. They shape the culture, and culture shapes technology. We consider some examples here.

---

### Empowerment of individuals and teams
The technical decision-making process is bottom-up.

* Accountability and decision-making power are inseparable.
* Engineering teams are responsible for local decision-making, delivering their part of the solution in the manner they see fit.
* Responsibility split: Business specifies requirements (including nonfunctional) and sets constraints, while Engineering determines the optimal technology solutions within their remit.

---

### Clear ownership demarcation
Teams are responsible for the quality of all components that are under their purview.

* Ownership of single responsibility solution components is reduced to single teams.
* Each team is responsible for one or more bounded contexts, ensuring clear ownership of that part of the system.
* Teams work closely with domain experts, the Product team, and Architects to understand and model the business domain.
* Teams are empowered to make technical decisions that best suit the domain requirements.
* Shared solution components (libraries, etc.) should have de facto custodians.
* Custodianship extends to the data persisted by the solution components. Those who own stateful components also own the underlying state and are responsible for its quality, integrity, and safekeeping.
* Ownership comes with implied warranty. Those who own it keep it running.

---

### Avoid knowledge siloing
Key knowledge should not be concentrated in the minds of the few.

* Within a team, knowledge of specific solution elements must be spread across team members.
* All critical knowledge, the loss of which is unacceptable, must be documented and reviewed.
* The degree of acceptable knowledge redundancy is left to managers; business-critical components should be accorded a greater knowledge spread.
* Team members should have an appreciation of the overall system architecture and the responsibilities of peer teams. 
* Managers will have a broader knowledge than their subordinates (but not necessarily deeper).
* A common vocabulary goes a long way in aiding communication both within and across teams.

---

### Avoid centralised communication
Do not delegate communication; bypass middlemen where possible.

* Don't ask your Engineering Manager or resident Architect to have robust conversations with other teams or colleagues on your behalf unless contention cannot be resolved by other means.
* Built rapport with your peers, particularly your direct suppliers and consumers. (I.e., teams and individuals who depend on your work and whose work you and your team depend on.)

---

### Permission to be wrong
We don't always get things right nor do we dwell on them.

* Quality is the prerogative of Engineering: the teams designate, monitor, and uphold quality objectives.
* Sometimes quality is intentionally relaxed; for example, for a proof-of-concept, to unblock a downstream team, to expedite feature delivery, or to meet a regulatory deadline. 
    + It is always better to avoid technical debt, but they may not always be possible. Occasionally, technical debt may be leveraged for greater gains.
    + In every case, time and resources _must_ be budgeted for follow-up work.
* We don't always get things right the first time, and sometimes we discover better ways of doing things. _We must give ourselves permission to be wrong._
    + The role of the leadership team is to uphold accountability while prioritising growth over blame.
    + Leadership must provide a safe space to evolve in, encouraging measured risk-taking while guaranteeing psychological safety. 
* We don't throw each other and our stakeholders under the bus. _We take responsibility for our actions._ If something didn't turn out the way we hoped, excuses like "we were told to get it out quickly" will not do.

---

### Avoid false alignment
Teams should be aligned internally based on their common objectives, particularly the decisions essential to meeting those objectives. They shouldn't align with artificial constraints unless these constraints are demonstrably required to achieve our goals.

For example, Engineering teams will be internally aligned to ensure we're all delivering on the one goal of building a market-leading product. They need not align on implementation detail; for example, technology stacks. The teams use a mixture of JavaScript, Rust, Python and Java. Despite their diversity, each team is effective in their delivery, and their deliverables are carefully aligned to a common goal.

Alignment across disparate teams should be limited to those collaborative areas that genuinely assist all parties in reaching their objectives. Done without due consideration, indiscriminate alignment robs teams of precious time and hurts morale; it does little to aid them in achieving their goals.

---

### Avoid design by committee
We've made some significant organisational and technology decisions already, and we have more decisions ahead of us. We must ensure that forthcoming decisions adequately support our system in the long term.

It may sound counterintuitive, but adding people does not necessarily lead to a better decision. There should be one key decision-maker who preserves the conceptual integrity of the overall system, supported by (and only by) —

* Those who are materially impacted by the decision; and
* Those with the relevant subject matter expertise.

---

### Design and build iteratively
Building a market-leading product is an evolutionary process. By overplanning and overbuilding, we risk venturing down the wrong path while wasting precious time in doing so. 

The challenge is to produce enough architecture up-front so that design gaps will not haunt us later, but not so much that we dwell on hypothetical scenarios that are unlikely to materialise, and lose track of the tangibles as a result.

* Critical design decisions must be made at the outset, as they unlock initial progress and set the foundation for the rest of the system. Implementation does not begin until all key technical risks have been addressed.
* Beware of drawing on assumptions that cannot be validated up-front. Parts of a design can only be fully validated once it is implemented in working software.
* There might be a tendency to provision for features that later turn out to be unneeded. (The YAGNI principle.)
* Work done later can draw upon the skills, experience and wisdom obtained earlier in the project. More of the problem space is uncovered as the work progresses; deferred design decisions can take advantage of these greater learnings.
* The implication of and undercooked design is costly refactoring down the track. Be aware and be prepared.

---

# Product principles
A CONTROL delivery organisation is populated by more than just technical personnel. The Product team plays as significant a role in achieving delivery objectives as Engineering. They, too, need principled guidance.

---

### Build products, not projects
We value long-term commitment over short-term engagement.

* The capabilities we build will serve the business for years and decades. Those involved (Engineers, Product Owners, UX designers, Architects, etc.) must take a long-term view.
* Some of our most successful competitors would have adopted the product mindset and numerous successful organisations in other industries have done the same.
* Products, unlike projects, don't have a well-defined end date. They evolve in response to market changes and business needs.
* Subject matter expertise takes a long time to build; we cannot afford to shuffle people in and out.

---

### Robustness over flexibility
Do not bake flexibility into a product's operational configuration unless it is essential or yields a competitive advantage. (Configurability here refers to operational parameters, rather than deployment, localisation, look and feel, content, and so forth.)

* Excessive flexibility complicates product design, implementation, and use. And in many cases it can lead to improper use.
* Decisions to alter a product's control surface should be based on empirical evidence.
* With time, most elements of the product's operation will be automated. This reduces the need for certain kinds of flexibility down the line.

---

## Technology principles
The final set of products relate directly to the system being built. They simultaneously guide and constrain the use of technology to solve business problems.

---

### Commoditise technology
Favour open, standards-compliant, accessible, and interchangeable technology and skills to reduce delivery cost and risk.

* Open-source solutions are preferred over commercial analogues, unless the competitive advantage offered by the latter exceeds their cost significantly.
* Generalised tooling is preferred over niche tooling (languages, frameworks, infrastructure, etc.) unless the latter is essential to fulfil specific functional and/or performance objectives.
* Operational (and other) costs and risks of maintaining prospective technology must be factored into the cost-benefit analysis. For example, a self-hosted message broker requires numerous infrastructure personnel that are suitably skilled. This presents a personnel risk.
* Prefer platform/vendor-neutral solutions over platform/vendor-specific solutions. For example, certain proprietary serverless solutions, while not without their advantages, may limit our future deployment options.
* Control technical diversity. Where a proposed technology is closely interchangeable with existing and well-supported technology, favour the latter. I.e., "new" or "different" not just for the sake of.

---

### Strongly event-driven
Our system is a substantial producer of data with many internal and external consumers. We have adopted the Event-Driven Architecture paradigm, ensuring that producers are minimally coupled to consumers.

* An event is a notification of something that might be of material significance; it is not a direct instruction to do something. (I.e., an event is not a command.) A consumer is free to interpret and process (or ignore) events as it chooses.
* Events are complete, correct, and timely. Where the producer is a system of record, all material entity updates should be accompanied by the publishing of an event.
* Producers determine the contract/schema for outgoing events and warrant that all published events conform to the contract.
* Producers preserve causality by ensuring that the partitioning scheme captures the causal order of events.
* Events are versioned. Versioning should be non-breaking where possible; breaking versions will require "double publishing" to support legacy consumers.
* Consumers should be idempotent. An event may be received multiple times and should not cause adverse effects on the consumer.

---

### Infrastructure as code
Favour the management of infrastructure through code instead of manual processes.

* Teams can provision and manage their own infrastructure using code (typically as declarative configuration).
* Teams manage the state of their infrastructure, including updates and rollbacks.
* Teams are responsible for the code that defines their infrastructure, ensuring it aligns with their service requirements.
* Specifying infrastructure as code ensures that environments are consistent across different stages of development.

---

# Patterns and guidelines
Principles are generally stated at a very high level of abstraction. They also tend to be succinct; a principle can be a embodied in one paragraph, yet it could be entirely unambiguous. An example is the "primary of principles" principle, which simply states that all decisions must refer to a principle where one exits. The combination of succinctness and abstraction makes principles broadly useful, but can also make their interpretation difficult in specific contexts.

Patterns and guidelines may be seen as refinements of principles, offering specific and actionable guidance for solving common problems:

* Patterns are reusable solution templates. They offer well-defined, scrutinised, and time-tested instructions that are effective in specific contexts.
* Guidelines are recommendations or best practices intended to influence how certain tasks should be performed. They are not clear-cut templates, unlike patterns. However, following a guideline should simplify the solutioning process and lead to higher quality (e.g., more robust) solutions.

Unlike principles, patterns and guidelines are rarely mandatory. In some ways, people ought to treat patterns and guidelines as tools in a toolbox. They don't have to use these tools to solve problems, and tools can sometimes be used interchangeably. For example, a hammer can be used to drive a stripped screw by force. However, Engineers are encouraged to follow patterns and guidelines where it is practical — to avoid reinventing the wheel, and to drive consistency within Engineering. Practitioners may deviate from this advice on some occasions, although they may be required to justify their decision to do so. Conversely, principles must be followed at all times.

Like principles, patterns and guidelines must be carefully vetted for the problem at hand:

* Many patterns are sourced from the industry and often reflect specific technology choices. For example, object-orientated design patterns apply to specific programming languages.
* Patterns and guidelines can be derived internally, especially for highly niche application domains where industry knowledge is hard to come by and is rarely shared. In many cases, internal patterns and guidelines can form the core intellectual property of an organisation; their leakage is highly undesirable.

Both patterns and guidelines serve common purposes. They aim improve the overall quality and maintainability of software. They ensure consistency in how problems are solved and tasks are performed across teams and software projects.

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

Patterns will typically offer more than a one-paragraph description. There will be references to problem contexts to which the patterns are ideally suited. Diagrammatic representations will frequently be used, while examples may be provided to guide the pattern's implementation.

Guidelines are generally more verbose and technology- or process-specific than patterns. Examples include:

* Branching strategies, code review and merge policies.
* Telemetry guidelines (covering the structure, organisation, and best-practices relating logging, metrics, and traces.)
* API versioning guidelines.

Regarding off-the-shelf patterns and guidelines, Architects and Engineering Managers shouldn't assume that because copious amounts useful material are commonly available and easily accessible, their use will be guaranteed. It is better to be explicit than to hope that Engineers will wilfully engage in research and self-education activities to determine the best tools for the job. (In theory, they will do precisely that. In practice, they won't.) Pick the most useful patterns that relate to your operating context and enrol them into the pattern catalogue. The same is said of guidelines. 

# Chalk outlines
The contentious assertion is that the main decision-making method used by millions of organisations daily is of little value and yields results only marginally better than chance. Nonetheless, I stand by this claim. Furthermore, I believe that the ongoing software crisis is partly due to this reality. Beyond the gaps in decision-making, many methods, processes, and frameworks that we hold in high regard are indistinguishable from snake oil. They often lack empirical reasoning or rigorous testing, are frequently applied outside their intended context, and are chosen for the simple reason that others have also chosen the same. They are about as useful to solving our problems as umbrellas are to fish.

Principled decision-making isn't without its challenges; like any method involving human judgment, it can be influenced by subjectivity, biases, and misunderstandings. I hold it in high regard not because of how good it is specifically but because how bad every _practical_ alternative is once scrutinised. A principled method discourages "tweaking" or, worse, "fudging". And while it alone doesn't guarantee the quality of the resulting decisions, it upholds the integrity of the process. In skilled hands, it is a robust method that can consistently produce good results.

# Summary
//TODO

Patterns and guidelines serve different but complementary roles in software development. Patterns provide concrete solutions to specific problems and ensure consistent and efficient problem-solving approaches. Guidelines offer broader recommendations and best practices to improve overall software quality and consistency. Both are essential tools for efficient and predictable software delivery.

# Concluding remarks
A large part of my work involves consulting clients on software architecture and engineering strategy. In certain fields, like sports wagering, I'm also regularly asked to provide insights on product-related matters, essentially stepping in as a subject matter expert. Making decisions and being involved in decision-making processes is, therefore, central to what I do.

Throughout the more senior period of my career, I have spent more time coaching "decision-makers" around me on making sound decisions than on deciding myself. If there is one observation made from my daily interactions with engineers, architects, and product folk, it is that most people — from greenhorns to seasoned professionals — are unskilled at decision-making. Even the more seasoned professionals haven't made significant strides in this area throughout their careers. I am convinced of this. I wouldn't have dedicated an entire chapter to decision-making had I thought otherwise.

Decision-making isn't formally taught in schools and universities, even though students are regularly tasked with solving problems. Instead, educational institutions focus on developing analytical skills, critical thinking, and problem-solving abilities, implicitly assuming that these skills will translate into effective decision-making. They don't, because the emphasis is on _solving_ a problem, not distinguishing among valid solutions. This suits educators because the gaps, in their worldview, lie in the theoretical foundations and _some_ practical skills. The overarching objective is to prepare students for the industry. And _it_ will do the rest.

Except that it doesn't. The industry has an objective of its own. Organisations exist to meet the needs of its stakeholders, first and foremost, not to educate those in its employ. Graduate development programmes that feature elements of education and training are really a mechanism for hiring candidates with good prospects at a salary that significantly undercuts that of an even minimally trained employee. These programmes have evolved in response to the acute imbalance between supply and demand that has plagued our industry. Beyond the initial training, however, recruits are on their own. The lucky ones will be mentored at various points and will receive good guidance from their managers, but the education outcomes are far from certain.

So, if industry doesn't teach decision-making skills and professionals aren't acquiring them naturally in their careers, the burden is on educational institutions to be more attentive to decision-making skills in their curricula.


---

 Many such vices have been exposed by Jerry Muller in _The Tyranny of Metrics_ (2018). The rollout of the Compstat ("computer statistics") system in New York in 1994 has led to systemic under-reporting of crime in order

Muller, J. Z. (2018). The Tyranny of Metrics. Princeton University Press.