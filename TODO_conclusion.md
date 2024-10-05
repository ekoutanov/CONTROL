Conclusion
---
Our journey has come to its conclusion. It is not the end, however. The software engineering discipline will continue to evolve with or without our involvement or approval. Nor is it the beginning. The engineering community has been slaving at the grindstone of improvement for many decades now. Whether progress has been commensurate with our efforts, however, is a matter of opinion. Is it, perhaps, the end of the beginning? Not at all, because we've had multiple "beginnings" now, and none with a clear "ending"; each of these events marking a distinct and impactful leap in information technology. The very concept of software, abstractions and high-level languages, software engineering as a profession, commoditisation of hardware and software, iterative and incremental approaches to development, Agile methodology... These are, undoubtedly, "beginnings" in their own right.

Instead, my hope for this book is that it marks the beginning of the end — a close to false assumptions, illusions, silver bullets, and unfulfilled promises that have spread like wildfire through our industry. I refer in particular to the last three decades of software "evolution", wherein unscrupulous salesmen disguised as method experts have systematically undermined the integrity of the profession, fueling the ongoing software crisis instead of trying to extinguish it.

# A brief recap
In large part, this book has been an exposé, uncovering lies that have been fed to current and aspiring software engineers by industry "thought leaders". We recount a few brief "lessons" below.

**I. Waterfall is not the antithesis of Agile.**

We began our investigation — if one may call it that — with a _partial_ rehabilitation of Waterfall. Specifically, it is not the model that we seek to redeem but its de facto scapegoat status. Waterfall is not the antithesis of Agile methods as it is often made out to be. Nor is it endorsed by proponents of Classical methodology. Nevertheless, Waterfall is routinely used in scaremongering campaigns by Agileists to depict in no uncertain terms what might happen if an organisation were to try something _different_ and non-Agile.

**II. Agile is sometimes appropriate.**

We also examined Agile methodology and the ideal problem context to which it is suited. Namely, 1) small, 2) highly-skilled teams, navigating 3) turbulent environments, supported by 4) highly engaged stakeholders. If the parameters of your project fit these constraints, then by all means go Agile; I'd be surprised if you haven't yet done so. Otherwise, if at least one of the aforementioned assumptions is unsatisfiable, then perhaps more suitable options ought to be considered. Reiterating one of the central themes of this book — _the reader must think and decide for themselves_. Herd mentality is best suited for cattle, both literally and figuratively.

**III. Teamwork is overpriced.**

One bombshell that this book might be remembered by is that teamwork is important but not quite so indispensable as some paint it. Between a moderately cohesive team of highly-skilled engineers and a highly cohesive team of moderately-skilled engineers, the former will yield better productivity and quality. And the less interrelated the problems being tackled by the team, the more the individual skills trounce teamwork. Some cohesion is undoubtedly needed to prevent dysfunction and ensure progress, but beyond that, cohesion cannot fill in for lack of skills.

**IV. Middle managers make poor delivery decisions (but are still useful).**

We explored the ideal topology of a delivery organisation and, in particular, considered the role of middle management in the delivery of software systems. The sobering conclusion is that while middle managers can support those involved in the delivery — individual contributors and their line managers — they mustn't make delivery-related decisions due to their arms-length separation from the problem space. This flies in the face of mainstream thinking in which organisations hope to boost underperforming delivery by adding people and ascending much of the routine decision-making to the level of middle management. However, the reduced amount of information available to middle management — a phenomenon referred to as the _knowledge gap_ — can only lead to less optimal delivery-level decisions.

Middle management can, indeed, be used to scale a delivery organisation — by supporting delivery personnel rather than managing delivery concerns directly. They can deal with staffing and budgetary concerns, assisting in hiring, performance management, team dynamics, and conflict mediation, while shielding their teams from difficult stakeholders. They can also help shape principles and define good engineering practices. Fundamentally, middle management's role is to resource, equip, and grow the teams in ways that set them up for success. Crucially, among the key obligations of middle managers is to develop the next generation of transformational leaders.

**V. Hiring for team fit will likely backfire.**

In discussing growth, we remarked on it being as much of a problem as a sign of success. Hiring people from the outside will (more than) occasionally introduce people into the organisation whose presence will be regretted later. The current (and likely future) disparity between engineering supply and demand means that the hiring side is always on the back foot, trying desperately to get someone who "can do the job" while balancing the likelihood of good candidates gravitating towards competitors with quicker screening processes or superior terms. It's a race to the bottom, with recruiters being the ultimate winners.

In a performance-focused, meritocratic organisation, individual skill is preferable to teamwork. But let's say you're unconvinced and will settle on nothing less than a great all-rounder. When the hiring time frames are highly condensed, it is next to impossible to find a highly talented engineer who is also a great team player and a potential coach to others. Conventional wisdom would have you believe that screening should focus on weeding out the "insociables" and manage their technical skills post hire. The thinking is that lack of technical skill will be noticed quickly and addressed summarily within the probation period, while hiring "brilliant arseholes" disrupts the team and is an absolute no-no, even if they are dealt with later.

The reality is that peoples' skills are usually not monitored during the "honeymoon" period when the candidate is learning the ropes, especially in environments dominated by legacy systems. Even when a gap in technical skills is eventually spotted (by their colleagues, most likely), their social prowess will often tow them out of scrutiny. No one wants to call out "nice guys", much less fire them. Besides, they _might_ improve, given a chance (or three). Lo and behold, the probation period is over with no improvement in sight. Conversely, skilled individuals with inadequate team skills won't be getting any preferential treatment from their colleagues; they tend to get "thrown under" pretty quickly. So, if you lack the time or appetite to screen for both technical and team skills, then it's a no-brainer: hire for technical ability unless the candidate's team skills are _obviously_ lacking from the get-go.

**VI. Tech initiatives mustn't yield to product.**

We also explored the journey to maintainable, (tech) debt-free software — the treatment of important system qualities compared to product functionalities. In particular, we examined the challenges of prioritising among the different capability types — technical _versus_ product. It is a perilous activity that rarely turns out as people expect. There is a strong temptation to allow one decision-maker to arbitrate among these seemingly conflicting needs — that person may be a Head of Product or a major business sponsor. An all-seeing oracle: one individual with the breadth of domain knowledge, an understanding of the competitive landscape, good rapport with internal stakeholders, and a solid grip on business priorities. Surely, there is no one better to steer the product _vs._ tech debate, achieving the optimal value outcome for the business.

This is precisely the kind of naive and misguided thinking that leads to today's brittle, debt-ridden software systems that barely last a decade before requiring a complete rewrite. It is the engineering equivalent of putting the fox in charge of the henhouse and hoping its "impartiality" towards poultry will maximise the long-term value for the farmer. People will _almost always_<sup>1</sup> prioritise activities that favour their personal interests - aligning with their role's expectations, for starters. Having dispensed with self-interests, the concerns of their immediate boss will be given a nod. Their department's interests may also receive consideration at some point, especially if group performance affects bonuses. Finally, having addressed the most pressing interests, employees will consider the organisation's broader interests, catering to its owners or shareholders. 

><sup>1 </sup>I say "almost always" to allow for the occasional outlier who acts irrationally. They present a challenge: on one hand, their presence cannot be ignored in our model; on the other hand, their irrational behaviour is varied and unreliable. It is, thus, better to permit stereotyping — assume that everyone acts rationally, in their best interest.

A corollary of the above, a member of the business or product community will almost always prioritise capabilities that generate revenue over those that protect it. They will prioritise a technical piece only when it becomes a hard dependency for reaching a short-term product delivery objective. Such technical initiatives are called _curative_ because without them something stays "broken". It could, for example, be an architectural quality that inhibits cost-effective product delivery. Beyond these bare essentials, longer-term _preventative_ measures are almost never considered. As a result, we have what we deserve.

None of this should come as a surprise: _pursuit of self-interest is a fundamental aspect of human behaviour_. In psychology and economics, this trait is central to understanding motivation and decision-making in a variety of settings. It is an axiom that the world has known for millennia. The sooner software engineers "discover" it, the better it is for them and others.

There is a solution, however unrefined or inelegant it may appear. Before proceeding, however, one must first let go of the illusion that technical and product initiatives may be objectively prioritised over each other by people who clearly benefit by one or the other. Both sets of initiatives are needed for the system to meet its objectives and realise long-term business value. Therefore, the solution is to split engineering capacity so that each of the streams is delivered with no regard for the other. Our stance may seem overly simple and unscientific, and it is — but it gets the job done without bias or favoritism. Crude but bulletproof, this method cannot be easily "fudged" or subverted. Ultimately, it is better to work with the known but acceptable limitations of a method than to adopt another whose limitations are unknown or, worse, operate under the false belief that there are no limitations at all.

**VII. Balanced decision-making is the bane of our existence.**

Decision-making is a routine activity found in every engineering organisation, and one can hardly fathom its impact on the quality of software produced day to day. A popular myth is that decision-making should yield the optimal outcome through a careful balance of pros and cons. As the theory goes, aggregating all relevant criteria and attributing a weighting (quantitatively or qualitatively) will identify the best _overall_ solution — on the balance of all things considered. 

In reality, many of the assumptions of this approach cannot be satisfied by its practitioners; in particular, appropriate (relevant, complete, and uncorrelated) factor selection, unbiased weight assignment, and objective scoring. This approach can also elicit "tweaking" behaviours that are questionable at best, and further undermine the decision quality. The result is an _illusion of objectivity_ — a "blue pill" that offers just the right amount of comfort in assuming that people have done their job to the best of their ability.

The only approach that works consistently is a principled one. By assessing the candidates against a well-known set of steadfast principles, principled decision-making eliminates solutions that fail to meet the standards defined by the organisation. Furthermore, by considering the principles from the outset, designers can formulate better, _a priori_ compliant solutions.

**VIII. Documentation is the best form of self-critique.**

In exploring the role of documentation in an engineering organisation we considered its most common application — as an asynchronous communication tool and method of educating the audience on matters that the authors believe to be essential for the maintenance of the software system being described. There in lies the main perceived value of documentation — it is an essential ingredient for enabling the evolution of software systems, especially beyond the point when its original designers or developers have moved on. Furthermore, the more stable the aspect being documented, the greater the dividends derived from documenting it.

While this virtue of documentation cannot be debated, there is a complementary perspective that documentation serves more than the outward audience that it primarily targets; its value is, in fact, derived immediately rather than at some future point. In actuality, documentation has a quicker payback period than the software itself: while software does not generate value until it is built, tested, and deployed, the self-reflection offered to authors releases value incrementally with every paragraph written and every diagram drawn.

**IX. There is such a thing as a stupid question.**

A much-flogged cliché in the world of highly institutionalised and equally underperforming engineering organisations is that there is no such thing as a stupid question If a question can be asked, it should be asked. Thoroughly studying the subject matter, reading through documentation, or otherwise trying to figure things out the hard way when a source of knowledge is readily at hand — a colleague or chatbot — is the equivalent of spinning wheels in a productivity sense.

Well, let me tell you this: _there are stupid questions_. At the very least, there are questions that didn't need asking — whether we choose to call them stupid, lazy, impertinent, or simply premature is beside the point. Furthermore, the ratio of such questions to the totality of questions asked is much higher than one might imagine.

Engineers are expected to understand the intricacies of the matters they deal in. This requires lots of learning and practicing. While asking questions is a form of learning, it provides an instant (but not necessarily correct) answer, and is often done in lieu of more structured and purposeful studies. I have, thus, compared this form of learning to instant gratification. Notwithstanding people's varied capacity for cognition, there is an inescapable need for our kind to educate ourselves, especially if we are to self-label as engineers or computer scientists. In that regard, delaying one's gratification is a tested path to intellectual wealth.

**X. Think for yourself.**
If there is just one lesson that can be taken away it is that one must always exercise healthy skepticism when facing popular "solutions" to nontrivial problems that are multidimensional and highly contextual in nature, particularly when these so-called solutions do not consider all the necessary variables, positing a unified "formula" for success. 

One should exercise similar levels of skepticism regardless of whether the solution came from a colleague, a highly-read blog, a popular podcaster, or a peer-reviewed paper. There is very little new in this world; most people simply peddle content generated by others, sometimes putting their unique spin on it, offering some guidance or gotchas, or presenting the results of a social questionnaire or a meta-study. It isn't to say that none of this content is useful, only that it cannot be taken without further analysis by those adopting the solution.

Take Agile, for instance. There is a plethora of material covering all aspects of its use and adoption, its strengths and limitations, success stories and failures... Yet we insist on adopting it with no regard to our individual and unique conditions, hoping that because it has purportedly worked for some organisations, it must work equally well for us.

Thinking for yourself implies a propensity for solving problems or, at least, a strong desire to do so.







Team cohesion is necessary but not sufficient quality of a high-performing team.


The idea of an entirely self-organising professional sporting team is an absurdity.

disillusionment and outright lights

We started the journey with a recount of the history of software development — both as an industry and as the profession. While retracing the historical underpinnings of software, the reader has learned of 




I rarely speculate on the future; not without long-winded disclaimers. But if there is one outcome I'd be willing to stake on is that artificial intelligence (AI) will become pervasive in our daily lives.

In wrapping up we will momentarily revisit this book's preface. An "unlearning" was promised — an antidote to the "knowledge" that systematically accumulated by the reader throughout their career. Indeed, this book has been a debunking and teaching tool in equal measure. But more importantly, I urged the reader to think for themselves — questioning _everything_ including all that I had to say. Your opinion is yours alone to make. And on that note, I wish you all the best in your _new_ career.






systematically exposed to throughout your engineering career, which I'm sure was, is, and will continue to


The first few decades have been marked by much misconception, numerous false promises

No silver bullets.

Neo-classical vs. Post-agile.

In concluding our journey we will momentarily revisit this book's preface

Classical ≠ Waterfall.