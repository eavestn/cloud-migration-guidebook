## Introduction

### My Bias

There's a lot of emotion in my [**State of Engineering**](#the-state-of-engineering) introduction. My "feeling" isn't a good one: I believe our industry is failing. And I think it is failing for one simple reason: misplaced arrogance. I have admittedly written a lot of what you will read below from that perspective:  despite that we _know_ there is a good way to deliver software, we continuously seek to make delivery overly complex and prone to failure - and largely do so from a foundation of ignorance. Where able, I've provided links out to articles that start to paint the picture into which many cloud migrations are introduced - and it's a picture you will first have to change if you want to succeed in your transformation. 

If you take away one thing from this guide, it's the two principles:

1. Transformation cannot happen without first addressing the environment in which the transformation must happen.
2. Both - transformation and environment change - **cannot** be done at the same time.

### Who's This Book For?

#### Audience

I remember the first time I told a decision maker I could save $25K USD per month (67%) on their cloud bill - for a single department - and the plan never getting traction beyond a vaguely interested eyebrow. Eventually, a company becomes so large its revenue growth outpaces its technology spend - that $25K USD per month is just acceptable waste. When _that_ company made a _multi-million dollar mistake_ ($80M USD), they moved on. _Those_ companies spend as much as 20% of their revenue on their Enginering Organization without question.

This book is for leaders and contributors in the SaaS or Product company that hasn't broken $1BN in revenue. I haven't implemented these patterns above that scale, but I _have_ implemented and proven the below patterns and principles for organizations that:

- Range from less than $1M USD ARR to well near $1B USD;
- Range from fewer than five (5) Engineers to organizations with greater than 150;
- Have audience bases between 100,000 users and 300M;
- And may need the capability to support transactions per second thresholds (TPS) of multiple-hundreds of transactions per second.

I've seen what works in these organizations, put it in place, measured it, and had a great deal of success. I've also seen the exact opposite of what to do - and had the displeasure of solving _that_ problem. 

Yes, you need to get to a place where your revenue growth or market position are so strong that you can do whatever you want. But to do that, you first have to survive - and do so without debilitating your company in the process.

This book's ideal reader understands the **first** technological choices made in a system's life are the most critical to that system's success. This book's audience believes good software is sofware that succeeds. Realistically, this book is for the companies who cannot recover in a world on unstable technology - and don't have the very expensive budget to remediate that instability.

##### What Is Successful Software?

I wrote a [high-level article about the definition of "good" a few years back](https://medium.com/@eavestn/the-software-definition-of-good-c8c435212aff); and, while I still believe in the soft qualities defined in that article, I also believe a real definition of success is _measurable_.

To start: I do **not** include "acquired" among the top criteria of "good". That shallow definition (and target) has a reputation for delivering unscalable products that fail to meet revenue expectations or integration expectations after acquisition (that's why Merger and Acquisition (M&A) Consulting in technology is big business). The majority of startups fail to meet a return on investment. While there are a myriad of reasons startups fail, "failing to adapt to change" is among the top-listed reasons. This may be due to poor planning (another reason), a lack of good marketing (another reason) from which to derive fit; but it can also be due to being bound inextricably to the wrong decision. 

I define successful software as: cheap, fast, stable, understandable, replaceable, and extensible. These are measurable qualities of software. Notice in this definition I don't list Product qualities, but I do define _software_ as successful ("good") if it enables a Product team to make informed decisions about what the Product should do. I define the _software_ as successful if the software can rapidly change to support those findings. I define successful software as software **that does not debilitate an organization from pivoting**.

Those measurable qualities listed above - though they enable usability and relevance - are not themselves quantifying success in terms of "makes me the most money". Those are natural consequences of measuring the right thing, but not the thing that is measured to dictate _technological_ choices. A product should be desirable (and measured), but the _technology_ should be judged by its ability to deliver desirable software. Again - making cash, mega important - but you can't do that with software that fails to deliver change.

The audience of this book believes that success is built on good software.

_Measuring the right thing and using those metrics as a launching off point for deeper conversations is something I address in [**Metrics**](#metrics)._

### To Cloud or Not To Cloud

#### Why You Need To Pay Attention

This history below isn't new, but to successfully produce software, you need to understand it. _You_ need to master it. We've been writing software for _decades_; yet, unlike roads, bridges, houses, manufactured goods, farming, and so on, software fails at an unnacceptably high cost and rate. And it doesn't have to. The reason software's failure is so grandiose is because - in part - people believe they can do "software" without knowing anything about it ("[arrogance](https://www.merriam-webster.com/dictionary/arrogance)"). You wouldn't hire a mechanic to fix your dog; and, yet, we hire into leadership from backgrounds with _zero_ exposure to the history of the problem they are trying to solve. 

Let's take a simple historical anecdote: [The V12 Rolls Royce Merline (1933)](https://www.iwm.org.uk/history/the-rolls-royce-merlin-engine) - an engine that defined mid-century aviation was not developed in a vacuum. The [Wright Brothers](https://airandspace.si.edu/explore/stories/researching-wright-way) flew in 1903. That first flight was twelve seconds and one-hundred tweny feet (120 ft.) - approximately four miles per hour (4 MPH). By 1917, the British Sopwith Camel could reach three-hundred (300) miles and achieve a maximum speed of one-hundred thirteen MPH (113 MPH). By 1936, the Supermarine Spitfire - outfited with the V12 Rolls Royce Merline - could travel over four-hundred fifty miles (450 mi.) and fly at a maximum speed of three-hundred seventy MPH (370 MPH). In thirty years, Engineers provided nearly a 10,000% increase in speed and a 11,879,900% increase in distance over the Wright Brothers' first flight. 

##### Flight Numbers

| Model                 | Maximum Speed  | Increase Over Last (IOL)  | Distance   | IOL                 | Service Ceiling | IOL    | Year of Manufacture | Years Between |
| --------------------: | -------------: | ------------------------: | ---------: | ------------------: | ---------------: | ------: | :-------------------: | :-------------: |
| Flyer 1               | 4 MPH          | `-`                       | 20 ft.     | `-`                 | `-`             | `-`    | 1903                | `-`           |
| Sopwith Camel         | 113 MPH        | 2,725%                    | 300 mi.    | 7,936,410%          | 19,000 ft.      | `-`    | 1917                | 14            |
| Supermarine Spitfire  | 370 MPH        | 227.4%                    | 450 mi.    | 50%                 | 36,000 ft.      | 89.4%  | 1936                | 19            |
| SR-71 Blackbird       | 2,500 MPH      | 575.7%                    | 3,250 mi.  | 62.2%               | 85,000 ft.      | 136.1% | 1964                | 28            |

So, how did they do it? Aeronautical Engineers would be nowhere without the continuous iterative evaluation of - and response to - the environment and functions that produce flight. In the over one-hundred years of aviation, Aeronautical Engineers have learned several things, including what _not_ to do (and have largely gotten there through structured experimentation). They document what not to do and don't do it again because they know _it would be a waste of time to incessantly repeat the failures of others._

A 1971 computer had two-hundred fifty-six bytes (256B) of memory. Today, off-the-shelf phones can store up to one terabyte (1 TB) of data - a 390,625,000,000% increase in fifty years. The first Windows system was introduced nearly forty years ago in 1985. Yet, despite having done the research and despite knowing how to deliver quality software, we still fail far more often than we succeed. 

It's important for you to pay attention to this history below because clearly something is wrong in building software.

#### The State of Engineering

There's a fight going on right now in the mid-2020s; the reputation of the cloud is diminishing. A number of organizations are evaluating their infrastructural posture not having seen the gains they expected by moving off-premises and into "the cloud". Some go as far as to define this fight and evaluation as [the early stages of an exodus](https://www.entrepreneur.com/science-technology/with-rising-costs-and-vendor-lock-ins-is-a-cloud-exodus-in/380648). My _feeling_? Like Marx wrote of the economies, the utopian future is the coming-to-rest of the cloud vs. on-premises predulum smack in the center. But, here's the thing: on-premises solutions are _cheaper_ (see [**The Problems With Cheap On-Premises Services**](#the-problem-with-cheap-on-premises-services) later). Think about it, how many servers could you purchase for $50K a month - a real number that won't shock many technology leaders of cloud-based companies barely breaking $1M USD ARR (though it should, particularly as the spend is likely over-inflated by bad decisions in the magnitude of 10x)? That's right, there are companies today that are so inverted they are spending as much as 50% of their revenue on their cloud infrastructure. And those companies are _still_ running Engineering Organizations 20-30 deep. 

People ask me all the time why Software Organizations fail. The answer is simple. People refuse to acknowledge that driving Software Engineering Organizations requires skill. Not talent. For the last time, let's return to the word "arrogance," defined by Merriam Webster as:

> an attitude of superiority manifested in an overbearing manner **or in presumptuous claims or assumptions**

So, how did this happen? How did the cloud become "a bad decision" or "expensive"?

There are always two costs to any project: the tools and the decision making of the people using those tools. That decision making - _the_ factor driving the short- and long-term costs of _your_ company - is informed by skill. That skill is rooted in a person's training, a person's exposure, and a person's humanity. If that person has not been exposed to a different way of doing this - and people are intrisically motivated to do what they know - then their ability to do what's best for your company is severely limited by their exposure. 

[Curtain opens on Leader. Standing alone. Center stage.]

Futher layer into this - the problem of underexposure - a fact (and one people will write me nastygrams about later): there is only one way to solve any given problem that drives real success. Given a clear understanding of the constraints, we _know_ what problems need to be solved for and how best to solve them. Anything that isn't that solution will slow down productivity, drive down efficiency, and explode any semblence of predictability. _All_ of these deviations will cost you money, and likely your business. Yet Engineers are constantly pushed to deliver whatever works despite the very real near-term risks of those solutions.

There are inescapable truths about Software. The worst? [Every system will fail to meet needs and will become progressively worse over time](https://medium.com/@eavestn/the-common-life-of-source-code-4c6aba1250fb). Why? Systems fail because people believe they can out perform the very physics of software - or, perhaps, they are just unaware.

If leaders cannot articulate these physics - these truths - then are they able to plan for them? My concern is that I have met very few technology leaders who are capable of articulating these inescapable truths.

Never trust the arrogance that assumes manufacturing the little silver trash can in my bathroom is harder at scale than manufacturing software. People _pretend_ software is different. Why? Software is maleable, quickly modifiable - a dangerous capability. The perception is that software - as we say in climbing - has a lower commitment grade than manufacturing a trash can.

[_Enter stage right the problem of the Customer._]

About twenty years ago, the industry learned something dangerous in software: there's near-infinite cash on the table. If your software can do exactly what your user needs, then that cash is yours. And - theoretically - the more your software does of what is needed, the more needed your software becomes. Waterfall taught us that if you wait too long to get your understanding of your customers' needs in front of them ("the product"), the greater the chance your customers' needs will have changed - you will have burned your cash and delivered something irrelevant. The belief is that **the faster you get your product in front of the customers, the faster you can understand if the product meets the customers needs**. You also get the ever-needed, gold-encrusted feedback. 

Your product sucks? No problem. You'll just change it. Improve relevance, get cash. Simple, right?

[_Enter stage left the problem of the Agile "Movement"_.]

A few years ago, some dudes (2001) figured out that you could get your product to the customer faseter and learn more about your product if you got [rid of some rules that were perceived to undermine success](https://agilemanifesto.org/) (success here meaning "making money"). They figured out

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

#### The Problems With Cheap On-Premises Services

Costs.

A friend of mine works in IOT for large corporate offices. The problems she and her team solve are enormous. A recent endeavor was determining how to enable corporate office spaces to automate efficient climate control without knowing anything about office structure and environment. Not small problems. She and I disagree about technology all the time. She and I got to talking about how much cheaper on-premises services are to run. The business function she runs is one of the most profitable. I pushed back on her bias for on-premises and immediately she started laying out the solution topography for an on-premises "serverless" function. Her solution was nothing ground breaking (AWS does it probably hundres of millions of times a day); just good, simple, accomplishable Engineering. If you've been around long enough in Engineering, likely you've had to deploy a server-backed solution that makes intelligent us of its operating environment. 

But, as a Hiring Manager, here's the problem I have: the fundamentals of Engineering are disappearing behind an enormous, social-media-driven spray of bad advice. [People are even _reading_ less](https://www.newyorker.com/culture/cultural-comment/why-we-dont-read-revisited) - they're testing their ideas against others' less. Everything is being learned through "secondary orality." _Additionally_, [people aren't even trying to disprove themselves anymore](https://en.wikipedia.org/wiki/Replication_crisis) before launching off on a million-dollar campaign to change the world based on flimsy research. Self-labeled "technology leaders" never having had to deal with the consequences of their poor decision yet issue tome after tome of 250-word blog entries for running effective organizations. A great lot of it runs absolutely counter to the way we know we _have to_ build software. 

Don't believe me? How many organizations do you know that bemoan the fact they can never get _anything_ done? It takes forever. The Engineering team is slow. Change is risky. We are failing to produce good systems because as an industry we have abandoned the fundamentals that matter.

Yet - with that lack of foundation - there are technology leaders who believe we should be talking about self-managing the segmentation of processing on self-hosted servers. Our profession isn't built to support on-premises solutions anymore. And getting back? Getting back is going to be so expensive. You've got to re-train an entire industry and do that while delivering software. Similar to cloud migrations: if you want a team that is _efficient_ in the future, you will have to homogenize your technical posture. Living in two environments - baselining focus on any one solution at fifty percent (50%) out of the gate - is an impossibility without horrendous budgets. So, not only do you have to retrain an entire industry, you've got to _again_ not deliver any new capabilities (risk your relevance) to your customers for two to three years. 

The worst part is that the people that can think the way that is needed to build on-premises systems are becoming a rarer species. And if Keynesian economics teaches us anything, it's what happens to scarce resources in high demand. So, should you develop your system on-premises? Is the infrastructure cheap? Yeah. But what happens when your team quits? What happens when your system fails? What happens when you need to change the size of your team to accommodate the anticipated workload to implement support for a client?

#### So, Cloud Or Not?

You can cloud if you want to, but ask first: is my product stuggling because of my infrastructure? Probably not. Everything you can do in the cloud, you can do [And our technology choices may not even matter in the near future](https://www.nytimes.com/2023/06/02/opinion/ai-coding.html), especially with some of the case studies coming out of Google, Microsoft, and state-level government departments mired in legacy systems.

