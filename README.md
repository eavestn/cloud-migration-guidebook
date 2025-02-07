# The Cloud Migration Guidebook

Cloud migrations ("digital transformations") have a reputation - and, largely, it isn't positive. Transformations are known for going over budget, past deadlines, and not necessarily leaving the "transformed" company in a better state - some transformations even fail entirely, leaving  organizations with millions of dollars of spend and no results. However, your transformation experience doesn't have to be poor. 

**The Cloud Migration Guidebook** covers getting to the cloud - and transformation in general. The people. The process. And the technology. The below is rooted in firm, tried philosophies of Software Engineering that have been tested - rigorously - for decades. I've implemented these philosophies - practices, processes, standards - myself (see [**Audience**](#audience)) and grown quantifiably stronger, less-expensive teams and software.

You don't have to apply any or all of what you read. I'd argue the most important take away from all of this is the principles. Your implementation can honestly look like whatever you want; just don't deviate from the fundamentals.

## Table of Contents

| Chapter | Topic |
| ------  | ----- |
| [Introduction](./chapters/00-Introduction.md) | Bias, Audience, Success |
| [Software Delivery Fundamentals]() | |

# Software Engineering Fundamentals

The fundamentals matter. 

## Why Fundamentals Matter

In a dimly lit conference room in Silicon Valley, a scene plays out that's become all too familiar in the Software industry. A Senior Engineer emphatically implores a Founder to following established Engineering practices; the Founder emphasizes the need for speed and innovation, the Engineer wants the paycheck, the Founder wins. The tension is palpable, reflecting a deeper conflict that has plagued software development since its inception.

"We're not Google," the Founder insists. "Those standards don't apply to us."

The Fallacy of Exceptionalism – the belief that an organization is somehow immune to the fundamental challenges that have shaped our industry's best practices - is a dangerous mindset that has led countless projects to their demise.

Across the United States, every plug must conform to specific physical specifications. These standards are not arbitrary; they've emerged from years of experience, accidents, and retrospective studies. When you plug in your device, you don't question whether it will work – it simply does, because standardization ensures compatibility, safety, and reliability. The Institute of Electrical and Electronics Engineers (IEEE) has documented _thousands_ of case studies that demonstrate this reality. 

Software Engineering, despite dealing with seemingly abstract concepts, is no different. We (Engineers) are not producing _ideas_; we're creating physical systems that people ulitmately _physically_ interact with. These same systems that must adapt and be backed by architectures that need to withstand the test of time ([with startup exits taking as long as seven years to occur](https://media.hubtas.com/2024/09/01/how-long-before-a-startup-exits-or-goes-public/)). 

Yet, time and time again, organizations succumb to Exceptionalism. They skip documentation, rush through testing, bypass proven design patterns, all in the name of speed and innovation. The results are predictable: technical debt accumulates, systems become brittle, and the ability to pivot – often crucial for business survival – diminishes. The IEEE established the Software Engineering Body of Knowledge (SWEBOK) not as bureaucratic overhead, but as a distillation of decades of hard-learned lessons.

Google wasn't born at Google-scale. Amazon didn't start by handling millions of transactions. They grew to handle massive scale precisely because they respected Engineering fundamentals that enabled their organizations to adapt over time to changing demand. Their success wasn't built on ignoring standards but on understanding and implementing them effectively.

The cost of ignoring these fundamentals often becomes apparent only when it's too late. Three, four, or eight years into a company's journey, when the opportunity for a crucial pivot arrives, the accumulated technical debt becomes an insurmountable barrier. The very shortcuts taken to "move fast" become the anchors that prevent movement altogether.

The irony is that this pattern repeats itself with remarkable consistency. Organizations believing they can outsmart decades of engineering experience end up rediscovering the same pitfalls, paying the same prices, and learning the same lessons that led to the creation of these standards in the first place.

This isn't to say that innovation doesn't have its place. But true innovation builds upon solid foundations; it doesn't ignore them. The choice isn't between agility and engineering rigor – it's about understanding that proper engineering practices enable sustainable agility.

When we examine successful software organizations, we find they share a common trait: they stand on the shoulders of giants rather than stumbling through well-documented pitfalls. They understand that software engineering standards, like the physical specifications for electrical outlets, exist not to constrain but to enable – to ensure that what we build today can power the needs of tomorrow.

The fundamentals matter because they represent our collective learning as an industry. They matter because software isn't just code – it's infrastructure that powers modern society. And most importantly, they matter because ignoring them doesn't make you exceptional; it just makes you the next case study in why they exist in the first place.

## Evidence-Based Engineering

In medicine, the shift to evidence-based practice revolutionized patient care. Doctors moved from relying on intuition and tradition to making decisions based on rigorous research and documented outcomes. This transformation didn't happen overnight, and it wasn't without resistance. Yet today, we'd be skeptical of any medical professional who dismissed peer-reviewed studies in favor of their personal theories.

Software engineering stands at a similar crossroads. We have thousands of case studies, decades of research, and countless documented successes and failures. Organizations like IEEE have meticulously cataloged what works, what doesn't, and under what circumstances. Yet many software teams continue to operate on intuition, preferences, and untested assumptions.

Consider a typical scenario: a team decides to skip writing tests because "we move too fast for testing." This decision isn't based on evidence – in fact, it contradicts numerous studies showing that tested code reduces bug rates, speeds up development, and improves maintainability. The IEEE's Software Engineering Body of Knowledge contains extensive research demonstrating that every dollar spent on testing saves multiple dollars in maintenance and bug fixes.

This rejection of evidence-based practices often stems from a fundamental misunderstanding of software engineering's nature. Software development isn't art, where personal expression trumps established techniques. It's engineering – a discipline where outcomes can be measured, compared, and improved through systematic study.

The evidence is clear and compelling:
- Version control practices reduce code conflicts and improve collaboration
- Code reviews catch bugs earlier in the development cycle when they're cheaper to fix
- Documentation reduces onboarding time and maintenance costs
- Automated testing improves code quality and reduces regression bugs
- Standard architectures improve system maintainability and scalability

These aren't opinions or preferences – they're conclusions drawn from thousands of real-world projects, meticulously studied and documented. When organizations like IBM, Microsoft, or Google publish case studies through IEEE, they're not sharing theories but documented results with measurable outcomes.

Yet resistance persists. Teams continue to "reinvent the wheel," ignoring decades of evidence in favor of learning lessons the hard way. This approach isn't just inefficient – it's professionally irresponsible. Would we trust a bridge builder who ignored structural engineering principles in favor of their personal theories?

Evidence-based engineering doesn't stifle innovation; it enables it. By building on proven foundations, engineers can focus their creative energy on solving new problems rather than relitigating solved ones. When Google tackles a new challenge, they don't redesign basic data structures – they build on proven fundamentals to push the boundaries of what's possible.

The path forward is clear. Just as medicine embraced evidence-based practice, software engineering must move beyond intuition and preference to embrace documented evidence. This means:
- Studying and applying proven patterns rather than reinventing them
- Making decisions based on data rather than opinions
- Learning from others' experiences rather than repeating their mistakes
- Contributing to the body of knowledge through careful documentation of outcomes

The cost of ignoring evidence is too high. In an industry where failure rates for software projects remain stubbornly high, we can't afford to dismiss the lessons learned through decades of collective experience. Every failed project that ignored evidence-based practices becomes another case study in why they matter.

The future of software engineering lies not in maverick intuition but in the careful application of proven principles, guided by evidence and refined through experience. As our industry matures, the question isn't whether to embrace evidence-based engineering, but how quickly we can make it the standard rather than the exception.

## Focus

To drive strong teams, you must drive focus. Strong teams deliver cheap, scalable, extensible, and maintainable software - the software we aim to deliver. The problem with software today is that there are too many ways to solve problems. Deviations in solution technology choices represent yet more lack of focus for an Engineer: rather than adequately solving a problem, an Engineer ends up focused on something not only unrelated, but avoidable. Technological heterogeneity isn't by nature bad; but it must be managed to enable strong teams. Simply stated: in today's poorly-informed, fast-paced "development" world, the odds are stacked against enabling your team to focus. 

Companies have a bias for touch - particularly when it comes to transformations. They want to _see_ the **results** of the transformation **immediately**. 


# The Impact of 'Big' Initial Deliverables on Focus

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

## Long-term employees kill companies

### Smaller doesn't mean "Nope"; it means more "yes"

### Software Fundamentals: MEasureing Everything First
