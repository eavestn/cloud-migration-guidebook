# The Cloud Migration Guidebook

Cloud migrations ("digital transformations") have a reputation - and, largely, it isn't positive. Transformations are known for going over budget, past deadlines, and not necessarily leaving the "transformed" company in a better state - some transformations even fail entirely, leaving  organizations with millions of dollars of spend and no results. However, your transformation experience doesn't have to be poor. 

**The Cloud Migration Guidebook** covers getting to the cloud - and transformation in general. The people. The process. And the technology. The below is rooted in firm, tried philosophies of Software Engineering that have been tested - rigorously - for decades. I've implemented these philosophies - practices, processes, standards - myself (see [**Audience**](#audience)) and grown quantifiably stronger, less-expensive teams and software.

You don't have to apply any or all of what you read. I'd argue the most important take away from all of this is the principles. Your implementation can honestly look like whatever you want; just don't deviate from the fundamentals.

## Introduction

### My Bias

There's a lot of emotion in my [**State of Engineering**](#the-state-of-engineering) introduction. My "feeling" isn't a good one: I believe our industry is failing. And I think it is failing for one simple reason: misplaced arrogance. I have admittedly written a lot of what you will read below from that perspective:  despite that we _know_ there is a good way to deliver software, we continuously seek to make delivery overly complex and prone to failure - and largely do so from a foundation of ignorance. Where able, I've provided links out to articles that start to paint the picture into which many cloud migrations are introduced - and it's a picture you will first have to change if you want to succeed in your transformation. 

### Who's This Book For?

#### Audience

I remember the first time I told a decision maker I could save $25K USD per month (67%) on their cloud bill - for a single department - and the plan never getting traction beyond a vaguely interested eyebrow. Eventually, a company becomes so large its revenue growth outpaces its technology spend - that $25K USD per month is just acceptable waste. When those companies make a multi-million dollar mistake, they move on, uninterrupted. _Those_ companies are able to spend as much as 20% of their revenue on their Enginering Organization without questioning its necessity.

If this describes your company, stop reading.

This book is for the SaaS or Product company that hasn't broken $1BN in revenue. Why? I haven't yet implemented these patterns at that scale. I have _proven_ the below patterns and principles for organizations that: range from less than $1M USD ARR to well near $1B USD; range from fewer than five (5) Engineers to organizations with greater than 150; have audience bases between 100,000 users and 300M; and may need the capability to support transactions per second thresholds (TPS) of multiple-hundreds of transactions per second. I've seen what works in these organizations, put it in place, measured it, and had a great deal of success. I've also seen the exact opposite of what to do - and had the displeasure of solving _that_ problem. 

Yes, you need to get to a place where your revenue growth or market position are so strong that you can do whatever you want. But to do that, you first have to survive - and do so without debilitating your company in the process.

This book's ideal reader understands t
the first technological choices made in a system's life are the most critical to that system's success. This book's audience believes good software is sofware that succeeds. Realistically, this book is for the companies who will fail if their technology fails.

##### What Is Successful Software?

I wrote a [high-level article about the definition of "good" a few years back](https://medium.com/@eavestn/the-software-definition-of-good-c8c435212aff); and, while I still believe in the soft qualities defined in that article, I also believe a real definition of success is _measurable_.

I don't define success as getting acquired. That shallow definition (and target) has a reputation for delivering unscalable products that fail to meet revenue expectations or integration expectations after acquisition (that's why Merger and Acquisition (M&A) Consulting in technology is big business). I define successful software as: cheap, fast, stable, understandable, replaceable, and extensible. _These_ are all measurable qualities of software. Notice in this definition I don't list Product qualities. I define _software_ as successful if it enables a Product team to make informed decisions about what the Product should do. I define the _software_ as successful if the software can rapidly change to support those findings. I define successful software as software **that does not debilitate an organization from pivoting**.

Those measurable qualities listed above - though they enable usability and relevance - are not themselves quantifying success in terms of "makes me the most money". Those are natural consequences of measuring the right thing, but not the thing that is measured to dictate _technological_ choices. A product should be desirable (and measured), but the _technology_ should be judged by its ability to deliver desirable software. Again - making cash, mega important - but you can't do that with software that fails to deliver change.

The audience of this book believes that success is built on good software.

_Measuring the right thing and using those metrics as a launching off point for deeper conversations is something I address in [**Metrics**](#metrics)._

### To Cloud or Not To Cloud

#### Why You Need To Pay Attention

This history below isn't new, but to successfully produce software, you need to understand it. _You_ need to master it. We've been writing software for _decades_; yet, unlike roads, bridges, houses, manufactured goods, farming, and so on, software fails at an unnacceptably high cost and rate. And it doesn't have to. The reason software's failure is so grandiose is because - in part - people believe they can do "software" without knowing anything about it ("[arrogance](https://www.merriam-webster.com/dictionary/arrogance)"). You wouldn't hire a mechanic to fix your dog; and, yet, we hire into leadership from backgrounds with _zero_ exposure to the history of the problem they are trying to solve. 

Let's take a simple historical anecdote: [The V12 Rolls Royce Merline (1933)](https://www.iwm.org.uk/history/the-rolls-royce-merlin-engine) - an engine that defined mid-century aviation was not developed in a vacuum. The [Wright Brothers](https://airandspace.si.edu/explore/stories/researching-wright-way) flew in 1903. That first flight was twelve seconds and one-hundred tweny feet (120 ft.) - approximately four miles per hour (4 MPH). By 1917, the British Sopwith Camel could reach three-hundred (300) miles and achieve a maximum speed of one-hundred thirteen MPH (113 MPH). By 1936, the Supermarine Spitfire - outfited with the V12 Rolls Royce Merline - could travel over four-hundred fifty miles (450 mi.) and fly at a maximum speed of three-hundred seventy MPH (370 MPH). In thirty years, Engineers provided nearly a 10,000% increase speed and a 11,879,900% increase in distance over the Wright Brothers' first flight. 

##### Flight Numbers

| Model                 | Maximum Speed  | Increase Over Last (IOL)  | Distance   | IOL                 | Service Ceiling | IOL    | Year of Manufacture | Years Between |
| --------------------: | -------------: | ------------------------: | ---------: | ------------------: | ---------------: | ------: | :-------------------: | :-------------: |
| Flyer 1               | 4 MPH          | `-`                       | 20 ft.     | `-`                 | `-`             | `-`    | 1903                | `-`           |
| Sopwith Camel         | 113 MPH        | 2,725%                    | 300 mi.    | 7,936,410%          | 19,000 ft.      | `-`    | 1917                | 14            |
| Supermarine Spitfire  | 370 MPH        | 227.4%                    | 450 mi.    | 50%                 | 36,000 ft.      | 89.4%  | 1936                | 19            |
| SR-71 Blackbird       | 2,500 MPH      | 575.7%                    | 3,250 mi.  | 62.2%               | 85,000 ft.      | 136.1% | 1964                | 28            |

A 1971 computer had two-hundred fifty-six bytes (256B) of memory. Today, off-the-shelf phones can store up to one terabyte (1 TB) of data - a 390,625,000,000% increase in fifty years.

So, how did they do it? Aeronautical Engineers would be nowhere without the continuous iterative evaluation of - and response to - the environment and functions that produce flight. In the over one-hundred years of aviation, Aeronautical Engineers have learned several things, including what _not_ to do (and have largely gotten there through structured experimentation). And they read about what not to do and don't do it because they know _it would be a waste of time to incessantly repeat the failures of others._

The first Windows system was introduced nearly forty years ago in 1985. Yet, despite having done the research and despite knowing how to deliver quality software, we still fail far more often than we succeed. 

It's important for you to pay attention to this history below because clearly something is wrong in building software.

#### The State of Engineering

There's a fight going on right now in the mid-2020s; the reputation of the cloud is diminishing. A number of organizations are evaluating their infrastructural posture not having seen the gains they expected by moving off-premises and into "the cloud". Some go as far as to define this fight and evaluation as [the early stages of an exodus](https://www.entrepreneur.com/science-technology/with-rising-costs-and-vendor-lock-ins-is-a-cloud-exodus-in/380648). My _feeling_? Like Marx wrote of the economies, the utopian future is the coming-to-rest of the cloud vs. on-premises predulum smack in the center. But, here's the thing: on-premises solutions are _cheaper_ (see [**The Problems With Cheap On-Premises Services**](#the-problem-with-cheap-on-premises-services) later). Think about it, how many servers could you purchase for $50K a month - a real number that won't shock many technology leaders of cloud-based companies barely breaking $1M USD ARR (though it should, particularly as the spend is likely over-inflated by bad decisions in the magnitude of 10x)? That's right, there are companies today that are so inverted they are spending as much as 50% of their revenue on their cloud infrastructure. And those companies are _still_ running Engineering Organizations 20-30 deep. 

People ask me all the time why Software Organizations fail. The answer is simple. People refuse to acknowledge that driving Software Engineering Organizations requires skill. Not talent.

So, how did this happen? How did the cloud become "a bad decision" or "expensive"?

There are always two costs to any project: the tools and the decision making of the people using those tools. That decision making - _the_ factor driving the short- and long-term costs of _your_ company - is informed by skills. Those skills are rooted in a person's training, a person's exposure, and a person's humanity. If that person has not been exposed to a different way of doing this - and people are intrisically motivated to do what they know - then their ability to do what's best for your company is severely limited by their exposure. 

[Curtain opens on Leader. Standing alone. Center stage.]

Futher layer into this - the problem of underexposure - a fact (and one people will write me nastygrams about later): there is only one way to solve any given problem that drives real success. Given a clear understanding of the constraints, we _know_ what problems need to be solved for and how best to solve them. Anything that isn't that solution will slow down productivity, drive down efficiency, and explode any semblence of predictability. _All_ of these deviations will cost you money, and likely your business. Yet Engineers are constantly pushed to deliver whatever works despite the very real near-term risks of those solutions.

There are inescapable truths about Software. The worst? [Every system will fail to meet needs and will become progressively worse over time](https://medium.com/@eavestn/the-common-life-of-source-code-4c6aba1250fb). Why? Systems fail because people believe they can out perform the very physics of software - or, perhaps, they are just unaware.

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

To drive strong teams, you must drive focus. Strong teams deliver cheap, scalable, extensible, and maintainable software - the software we aim to deliver. The problem with software today is that there are too many ways to solve problems. Deviations in solution technology choices represent yet more lack of focus for an Engineer: rather than adequately solving a problem, an Engineer ends up focused on something not only unrelated, but avoidable. Technological heterogeneity isn't by nature bad; but it must be managed to enable strong teams. Simply stated: in today's poorly-informed, fast-paced "development" world, the odds are stacked against enabling your team to focus. 

Companies have a bias for touch - particularly when it comes to transformations. They want to _see_ the **results** of the transformation **immediately**. 


# The Impact of 'Big' Initial Deliverables on Focus and Efficiency

## 1. The "Touch" Mentality

In the mid-2020s, we're witnessing a fight. It's not just about cloud versus on-premises; it's about the very nature of how we approach software development and digital transformation. Companies, driven by a misplaced arrogance and an insatiable need to "touch" immediate results, are pushing for bigger, flashier deliverables right out of the gate. This mentality isn't just misguided—it's dangerous.

The desire for quick wins has become a pandemic in our industry. Leaders, often coming from backgrounds with zero exposure to the history of software development, make decisions as if they're hiring a mechanic to fix a dog. They want to see, feel, and showcase the results of their transformation efforts immediately, regardless of the long-term consequences.

But what happens when we give in to this "touch" mentality? The consequences are far-reaching and often devastating to the very goals these leaders aim to achieve.

## 2. Consequences of "Bigger" Initial Deliverables

### a) Increased Complexity

When we push for bigger initial deliverables, we're not just adding features—we're exponentially increasing complexity. It's like trying to build a Rolls Royce Merlin engine without understanding the basics of aviation. The result? A Frankenstein's monster of code, stitched together with the thread of immediacy rather than the steel of solid engineering principles.

This complexity doesn't exist in isolation. It cascades through every aspect of the project, affecting not just the code, but the people working on it as well.

### b) Diluted Focus

Focus isn't just about concentration—it's about efficiency, quality, and ultimately, success. When we spread our engineers thin across multiple objectives, we're not just diluting their focus; we're setting them up for failure. It's akin to asking a pilot to fly a plane while simultaneously repairing the engine and serving drinks to the passengers.

This dilution of focus doesn't just impact the day-to-day work; it sets a dangerous precedent for the entire project lifecycle.

### c) Technical Debt

Here's a hard truth: shortcuts taken to deliver more features quickly are nothing but loans taken against your future. And the interest on these loans? It's compounded daily. The technical debt accrued from rushing big deliverables is often the silent killer of promising software projects.

But the ramifications of technical debt extend beyond just code quality. They fundamentally alter the trajectory of your entire project.

### d) Misaligned Priorities

In the rush to deliver big, we often lose sight of what truly matters. It's not about how many features you can cram into a release; it's about building a foundation that can support and adapt to future needs. Misaligned priorities at the start of a project are like setting off on a journey with a faulty compass—you might move fast, but you're heading in the wrong direction.

These misaligned priorities don't just affect the current project. They set a precedent that can derail an entire organization's approach to software development.

## 3. The Paradox: Less is More

Now, here's the kicker: in software development, less often leads to more. It's counterintuitive, especially to those outside the engineering realm, but it's a fundamental truth. Smaller, focused deliverables aren't just easier to manage—they're the building blocks of truly scalable, maintainable software. It's not about how much you can do; it's about how well you can do it.

This paradox isn't just a nice theory. It's a principle that, when applied correctly, can transform the way we approach software development.

## 4. Strategies for Balancing Touch and Focus

Balancing the need for tangible results with the importance of focus isn't just a good idea—it's essential for survival in today's software landscape. We need to:

1. Educate stakeholders on the value of focused, incremental development
2. Set clear priorities and limit work-in-progress
3. Implement MVP (Minimum Viable Product) approach
4. Provide regular demonstrations of progress, even on foundational work

But more importantly, we need to change the conversation. Instead of asking "How much can we deliver?", we should be asking "How can we deliver value most effectively?"

These strategies aren't just band-aids for a broken system. They're the foundation of a new approach to software development that prioritizes long-term success over short-term gains.

## 5. Long-term Benefits of Focused Initial Work

The long-term benefits of focused initial work aren't just theoretical—they're the difference between a software project that thrives and one that barely survives. A strong foundation built on focused, quality work doesn't just support future development—it accelerates it. It's the difference between building on solid ground and trying to construct a skyscraper on quicksand.

The benefits include:

1. Stronger foundation for future development
2. Improved code quality and maintainability
3. More efficient use of engineering resources
4. Better alignment with overall transformation goals

In the end, the choice is clear. We can continue down the path of big, unfocused deliverables, chasing the dragon of immediate gratification. Or we can embrace the power of focus, building software that's not just successful by shallow metrics, but truly good—cheap, fast, stable, understandable, replaceable, and extensible. The future of your software, and possibly your entire organization, hangs in the balance.

The path forward isn't easy, but it's necessary. It requires a fundamental shift in how we think about software development, project management, and organizational success. But for those willing to make this shift, the rewards are immeasurable.

Depth

#### The Problems With Cheap On-Premises Services

A friend of mine works in IOT for large corporate offices. The problems she and her team solve are enormous. A recent endeavor was determining how to enable corporate office spaces to automate efficient climate control without knowing anything about office structure and environment. Not small problems. She and I disagree about technology all the time. She and I got to talking about how much cheaper on-premises services are to run. The business function she runs is one of the most profitable. I pushed back on her bias for on-premises and immediately she started laying out the solution topography for an on-premises "serverless" function. Her solution was nothing ground breaking (AWS does it probably hundres of millions of times a day); just good, simple, accomplishable Engineering. If you've been around long enough in Engineering, likely you've had to deploy a server-backed solution that makes intelligent us of its operating environment. 

But, as a Hiring Manager, here's the problem I have: the fundamentals of Engineering are disappearing behind an enormous, social-media-driven spray of bad advice. [People are even _reading_ less](https://www.newyorker.com/culture/cultural-comment/why-we-dont-read-revisited) - they're testing their ideas against others' less. Everything is being learned through "secondary orality." _Additionally_, [people aren't even trying to disprove themselves anymore](https://en.wikipedia.org/wiki/Replication_crisis) before launching off on a million-dollar campaign to change the world based on flimsy research. Self-labeled "technology leaders" never having had to deal with the consequences of their poor decision yet issue tome after tome of 250-word blog entries for running effective organizations. A great lot of it runs absolutely counter to the way we know we _have to_ build software. 

Don't believe me? How many organizations do you know that bemoan the fact they can never get _anything_ done? It takes forever. The Engineering team is slow. Change is risky. We are failing to produce good systems because as an industry we have abandoned the fundamentals that matter.

Yet - with that lack of foundation - there are technology leaders who believe we should be talking about self-managing the segmentation of processing on self-hosted servers. Our profession isn't built to support on-premises solutions anymore. And getting back? Getting back is going to be so expensive. You've got to re-train an entire industry and do that while delivering software. Similar to cloud migrations: if you want a team that is _efficient_ in the future, you will have to homogenize your technical posture. Living in two environments - baselining focus on any one solution at fifty percent (50%) out of the gate - is an impossibility without horrendous budgets. So, not only do you have to retrain an entire industry, you've got to _again_ not deliver any new capabilities (risk your relevance) to your customers for two to three years. 

The worst part is that the people that can think the way that is needed to build on-premises systems are becoming a rarer species. And if Keynesian economics teaches us anything, it's what happens to scarce resources in high demand. So, should you develop your system on-premises? Is the infrastructure cheap? Yeah. But what happens when your team quits? What happens when your system fails? What happens when you need to change the size of your team to accommodate the anticipated workload to implement support for a client?

[And our technology choices may not even matter in the near future](https://www.nytimes.com/2023/06/02/opinion/ai-coding.html), especially with some of the case studies coming out of Google, Microsoft, and state-level government departments mired in legacy systems.


## People

### Team Structure

Good processes build good software. 

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

### No Man's Land (Need Place In Structure)

#### Do's and Dont's Of On-Call
#### Measuring Software (Metrics)
#### Don't Obsess Over Touch
#### Plan For Failure
#### Cloud Transformation Readiness Test

Could you deploy something to the cloud, today? Then you are not ready. No work should begin until your answer to that question is "yes"

#### Cloud Transformation Readiness Inventory

Can be taken to any technical organization.

#### Metrics

When I define success measurably, I can evaluate whether or not I have succeeded. I can also evaluate whether or not I should change my strategy. When something is unmeasurable, I cannot make informed decisions and therefore it is dangerous. 

### Standards

## clarity - shift legt
