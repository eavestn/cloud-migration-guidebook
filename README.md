# The Cloud Migration Playbook

So, you want to migrate your legacy, on-premises services to the cloud? Cloud migrations ("digital transformations") have a reputation - and, largely, it isn't positive. However, your experience doesn't have to be. This playbook covers getting to the cloud. The people. The process. And the technology.

## Introduction

### Who's This Book For?

...

### To Cloud or Not To Cloud

#### Why You Need To Pay Attention

This history below isn't new, but in order to successfully produce software, you need to understand it; or, rather, you need to master it. We've been writing software for _decades_ at this point; yet, unlike roads, bridges, houses, manufactured goods, farming, and so on, software fails at an unnacceptably high cost. And it doesn't have to. The reason software's failure is so grandiose is because - in part - people believe they can do it without knowing anything about it. You wouldn't hire a mechanic to fix your dog; and, yet, we hire into leadership from backgrounds with _zero_ exposure to the history of the problem they are trying to solve. 

[The Rolls Royce MErline wasn't built in a vacuum](https://www.iwm.org.uk/history/the-rolls-royce-merlin-engine). Aviation itself is a really interesting lesson in innovation and timescale. If you consider that the [Wright Brothers](https://airandspace.si.edu/explore/stories/researching-wright-way) first flew in - dropping shells in . 

We've been programming for profit for ... yet we still don't get it right despite ...

##### My Bias

There's a lot of emotion in my [**State of Engineering**](#the-state-of-engineering) introduction to this book, below. I've tried to provide some citations, but significant portions are experience based. My "feeling" isn't a good one. I think our industry is failing. And I think it is failing for one simple reason: missplaced arrogance. I write a lot from that perspective: that despite the fact that we _know_ there is a good way to delivery software, we continuously seek to make it overly complex and largely do so from a foundation of ignorance. 

#### The State of Engineering

There's a fight going on right now in the mid-2020s; the reputation of the cloud is diminishing. A number of organizations are evaluating their infrastructural posture not having seen the gains they expected by moving off-premises and into "the cloud". Some go as far as to define this fight and evaluation as the early stages of an exodus. My _feeling_? Like Marx wrote of the economies, the utopian future is the coming-to-rest of the cloud vs. on-premises predulum smack in the center. But, here's the thing: on-premises solutions are _cheaper_ (see [**The Problems With Cheap On-Premises Services**](#the-problem-with-cheap-on-premises-services) later). Think about it, how many servers could you purchase for $50K a month - a real number that won't shock many technology leaders of cloud-based companies barely breaking $1M USD ARR (though it should, particularly as the spend is likely over-inflated by bad decisions in the magnitude of 10x)? 

So, how did this happen? How did the cloud become "a bad decision" or "expensive"?

There are always two costs to any project: the tools and the decision making of the people using those tools. That decision making - _the_ factor driving the short- and long-term costs of _your_ company - is informed by skills. Those skills are rooted in a person's training, a person's exposure, and a person's humanity. If that person has not been exposed to a different way of doing this - and people are intrisically motivated to do what they know - then their ability to do what's best for your company is severely limited by their exposure. 

[Curtain opens on the Leader. Standing alone. Center stage.]

Futher layer into this - problem of underexposure - a fact (and one people will write me nastygrams about later): there is only one way to solve any given problem that drives real success. Given a clear understanding of the constraints, we _know_ what problems need to be solved for and how best to solve them. Anything that isn't that solution will slow down productivity, drive down efficiency, and explode any semblence of predictability. _All_ of these deviations will cost you money, and likely your business. Yet Engineers are constantly pushed to deliver whatever works despite the very real near-term risks of those solutions.

There are inescapable truths about Software. The worst? [Every system will fail to meet needs and will become progressively worse over time](https://medium.com/@eavestn/the-common-life-of-source-code-4c6aba1250fb). Why? People believe they can out perform the very hysics of software. 

If leaders cannot articulate these truths, then are they able to plan for them? My concern is that I have met very few technology leaders who are capable of articulating these inescapable truths.

Never trust the arrogance that assumes manufacturing the little silver trash can in my bathroom is harder at scale than manufacturing software. People _pretend_ software is different. Why? Software is maleable, quickly modifiable. The perception is that software - as we way in climbing - has a lower commitment grade than manufacturing a trash can.

[_Enter stage right the problem of the Customer._]

About twenty years ago, the industry learned something dangerous in software. There's infinite cash on the table. If your software can do exactly what your user needs, then that cash is yours. And - theoretically - the more your software does of what's needed, the more needed your software becomes. Unfortunately, Waterfall taught us that if you wait too long to get your understanding of your customers' needs in front of them ("the product"), the greater the chance your customers' needs will have changed - you will have burned your cash and delivered something irrelevant. The belief is that **the faster you get your product in front of the customers, the faster you can understand if the product meets the customers needs**. You also get the ever-needed, gold-encrusted feedback. 

Your product sucks? No problem. You'll just change it.

[_Enter stage left the problem of the Agile "Movement"_.]

A few years ago, some dudes (2001) figured out that you could get your product to the customer and learn more about your product if you got [rid of some rules that were perceived to undermine success](https://agilemanifesto.org/) (success here meaning "making money"). They figured out

> ... [I]f you wait too long to get your understanding of your customers' needs in front of them, the greater the chance your customers' needs will have changed.

But, like, they didn't do anything big, all they wrote was (_emphasis original_): 

> We are uncovering better ways of developing  
> software by doing it and helping others do it.  
> Through this work we have come to value:  
>
> **Individuals and interactions** over processes and tools  
> **Working software** over comprehensive documentation  
> **Customer collaboration** over contract negotiation  
> **Responding to change** over following a plan  
>
> That is, while there is value in the items on  
> the right, we value the items on the left more.  

The problem was that people ran with wreckless abandon to the edge of the cliff of this freedom and jumped straight off. The point was missed and quickly everything became excessively over-regimented. Certificate-issuing organizations started introducing frameworks that sought to structure this new way of working and guarantee results; however, those frameworks became so poorly adopted and misused - and then made even more complex - that [they didn't work](https://www.reuters.com/technology/capital-one-scraps-1100-tech-positions-source-2023-01-19/). Worse? Those frameworks forgot about the very reason they existed. To focus time on doing well-defined work in a way that was not over-encumbered by process. 

The reality is none of these factors change whether you're in the cloud or on-premises.

#### Focus

#### The Problems With Cheap On-Premises Services

A friend of mine works in IOT for large corporate offices. The problems she and her team solve are enormous. A recent endeavor was determining how to enable corporate office spaces to automate efficient climate control without knowing anything about office structure and environment. Not small problems. She and I disagree about technology all the time. She and I got to talking about how much cheaper on-premises services are to run. The business function she runs is one of the most profitable. I pushed back on her bias for on-premises and immediately she started laying out the solution topography for an on-premises "serverless" function. Her solution was nothing ground breaking (AWS does it probably hundres of millions of times a day); just good, simple, accomplishable Engineering. If you've been around long enough in Engineering, likely you've had to deploy a server-backed solution that makes intelligent us of its operating environment. 

But, as a Hiring Manager, here's the problem I have: the fundamentals of Engineering are disappearing behind an enormous, social-media-driven spray of bad advice. [People are even _reading_ less](https://www.newyorker.com/culture/cultural-comment/why-we-dont-read-revisited) - they're testing their ideas against others' less. Everything is being learned through "secondary orality." _Additionally_, [people aren't even trying to disprove themselves anymore](https://en.wikipedia.org/wiki/Replication_crisis). before launching off on a million-dollar campaign to change the world based on flimsy research. Self-labeled "technology leaders" never having had to deal with the consequences of their poor decision yet issue tome after tome of 250-word blog entries for running effective organizations. A great lot of it runs absolutely counter to the way we know we _have to_ build software. 

Don't believe me? How many organizations do you know that bemoan the fact they can never get _anything_ done? It takes forever. The Engineering team is slow. Change is risky. We are failing to produce good systems because as an industry we have abandoned the fundamentals that matter.

Yet - with that lack of foundation - there are technology leaders who believe we should be talking about self-managing the segmentation of processing on self-hosted servers. Our profession isn't built to support on-premises solutions anymore. And getting back? Getting back is going to be so expensive. You've got to re-train an entire industry and do that while delivering software. Similar to cloud migrations: if you want a team that is _efficient_ in the future, you will have to homogenize your technical posture. Living in two environments - baselining focus on any one solution at fifty percent (50%) out of the gate - is an impossibility without horrendous budgets. So, not only do you have to retrain an entire industry, you've got to _again_ not deliver any new capabilities (risk your relevance) to your customers for two to three years. 

The worst part is that the people that can think the way that is needed to build on-premises systems are becoming a rarer species. And if Keynesian economics teaches us anything, it's what happens to scarce resources in high demand. So, should you develop your system on-premises? Is the infrastructure cheap? Yeah. But what happens when your team quits? What happens when your system fails? What happens when you need to change the size of your team to accommodate the anticipated workload to implement support for a client?

[And our technology choices may not even matter in the near future](https://www.nytimes.com/2023/06/02/opinion/ai-coding.html), especially with some of the case studies coming out of Google, Microsoft, and state-level government departments mired in legacy systems.


## People

### The Culture That Produced The Problem Is Liable To Repeat The Failure

### Watch Out For Unicorns

### Set The Vision

Everyone needs to articulate _why_ **the cloud** is _the_ solution. And it can't be superficial - finances are great, but why should people believe in the cloud?

### Education

Should I train my people?  

#### Short-term Education Strategy

Beneficial in the short tem. Consult "Should I hire a different team?"

## Hiring

### Should I Hire A Different Team?

#### Consultants

Only if you know the problem you are trying to solve and if short-term training initiatives don't gain traction. See Domain Risk.


## Process

### Every Process Should Have A Documented Outcome

### Watch Out For the Figs

### Test The Process

Leverage "doing" as an opportunity to observe failure - and to learn. Section your system. DOCUMENT FIRST.

### Compliance

## Technology

### Domain Knowlege

#### Is This A Risk?

Depends on your cloud migration strategy. Are you net-newing based on a Product organization that has a clear, written definition of the behaviors the business needs to support? Or are you discovering this as you go? Or are you "lifting-and-shifting" your way to the cloud.
