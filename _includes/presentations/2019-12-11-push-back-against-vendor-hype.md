
## Vendor hype
+ Dangers of being vendor-led
+ Omission, misdirection and optimism
+ New means more sales
+ Support is time-limited

{% if include.pres %}Note: {% endif %}
I love vendor presentations. 
There's a kind of gloss that just doesn't seem like \[my\] real life.
Everything just works, better.

The problem is that they're often unrepresentative of their real world implementations.
While I hope that all vendor presentations are entirely factual, there's enough omission, misdirection and unfounded optimism to make them misleading.

Vendors need to sell and, depending on their level of integrity, that need may outweigh our credulity.
What they're pushing will work, but how well depends on a myriad of adoption factors.

How is your organisation set up to adopt new technology?
How well trained and how often trained are your team?
How much capacity do they have for investigating new ways of achieving something?
Do you have the measures in place to know if it's working?

Whatever they're selling, this product has probably got a fixed lifespan.
If nothing else does, the arrival of this product's successor will ultimately ensure that it's deprecated, by fair means or fowl.
So why are so few vendors willing to talk about the end-of-life for their shiny new offering?

---

## Newphoria
+ New is full of promise
+ Solutions to present challenges
+ Improvements, upgrades

{% if include.pres %}Note: {% endif %}
Admittedly that new solution is full of promise, largely because it caters for a set of problems that we now understand.
I know it would certainly do a great job solving the problems I've currently got.
However, the question it needs to answer is how well will it solve the problems I'm about to have.

Almost all modern working environments are dynamic systems.  While some might be able to slow the pace of change due their sector's nature, core technologies or incumbency, most will constantly be facing change on several fronts simultaneously.

Predicting those forces is hard, so the value of a new product cannot be determined only by its ability to solve today's problems, but also how well it can flex and adapt to future needs.

---

## Downside of new
+ Complications undiscovered
+ Bugs as yet unsorted
+ Problems as yet unsolved

{% if include.pres %}Note: {% endif %}
That same glowing new thing will also introduce new and unfamiliar complications and challenges.
There will be features it lacks that we won't know we need, until we adopt it.
There will be bugs, though hopefully they will be sufficiently common to motivate the vendor to patch them.  Not all will.
There will be problems associated with the adoption of the technology.

---

## Vendor pressures
+ Buy now (reduces runway)
+ Buy ours (non-standard)
+ Buy tailored to you (restricted marketplace)
+ Buy ours again in the future (lock-in)

{% if include.pres %}Note: {% endif %}

Large scale IT vendors are motivated by many different forces and it would be unfair for me to tar them all with the same brush.  I've worked for some who held themselves to a higher standard; their products were marketed with integrity and they are accountable for their end users' experience of them.  Sadly this is not true of all.

In some Sales functions, the goal is the sale and only the sale, at all costs.  They want you to buy now, from them and only from them in the future.  They will try to restrict your options (or what you believe about your options) to one: only they can sell you the right product for your business.

---

## Goals
+ How are you organised?
+ What are you trying to achieve?
+ How will this tech help you achieve that?
+ How long will that impact take?
+ What will it cost?

{% if include.pres %}Note: {% endif %}
So in the face of this sales barrage, I've been thinking about how organisations can make sensible (and justifiable) purchasing decisions.
It all comes back to goals.

* What is it that the organisation is trying to achieve?
* What's going to help that end?
* How long will it take to have that impact and at what cost?

That's all basic management theory, but rarely do these questions yield absolute and clear answers to the purchasing questions that precipitate them.

I can't offer a panacea to such a complex question, but here are some counter strategies to balance out the vendor push.  By all means go with a vendor, dive into their product, commit to their service contract, but please consider these first!

---

## Counter strategy: service granularity
+ Small services
+ Highly competed
+ Standardised, so interchangeable

{% if include.pres %}Note: {% endif %}
When services are massive, monolithic entities, the prospect of replacing them becomes horrific.
Even if a single, comprehensive service might represent the best option at the time of purchase, it's exceedingly unlikely that this monopoly will endure.
Some part of the process will change, or be disrupted by new innovation and when, not if, that happens the interoperability of the service will outweigh it's initially integrated advantage.
Purchasing small services requires a greater ownership of the technical specifics that will ensure:

1. they work together now (functional)
2. they work together well (performant)
3. they will continue to work together (reliable)
4. they work together when things go wrong (resilient)
5. they are loosely bound, such that each can be replaced (decoupled)

---

## Counter strategy: service lifecycle
+ Need a good runway to prepare
+ Staff training
+ Service deprecation
+ Trial phase / Canary deployment

{% if include.pres %}Note: {% endif %}
Big bang service replacement often made a big mess, or led to extended periods of downtime.
As project management has become more agile, often in recognition of the fast pace of change that we cannot predict, service delivery and critically service replacement has become more flexible.
Services are often changed out on a rolling basis.
In successful instances, that service swap-out experience can be at least indifferent and at best invisible to the user.
The key is a runway.

Major upgrades require early commitment from the business sponsor(s), whether individual budget-holder or board.
By bringing staff training up before the major rollout, and not as an after thought, potential shortfalls in the specification or evaluation of the service can be avoided.

Without time, our business transformation programme can fall back into the vendor's clutches.
Vendors benefit at the expense of organisations, who for whatever reason need to achieve their goals fast:

* Fast means that risk increases, as due diligence becomes a nice-to-have.
* Fast means buying something fairly general, off-the-shelf and turnkey: a catholicon.
* Fast places the buyer's back against the wall, meaning that unscrupulous vendors can capitalise.

If service deprecation is planned not when services get old, but when they're brand new, then replacement spend doesn't come as a surprise.
In fact services can be amortised over their lifetime, so even if there are capital costs at the start of life, they can be spread through to the end.

---

## Counter strategy: preserve access to data
+ Standardised data storage formats
    + Native or if not, exports
+ Standardised data access protocols
+ Standardised data management

{% if include.pres %}Note: {% endif %}
If present success comes from a well-purchased service,
then future success is predicted upon the boundaries between each system component.

The way IT services store data matters:

* who has access to it,
* what tools can be used to manipulate it
* how is it updated
* how is the data governed and who is accountable
* how is it validated as correct, or how are errors identified and remediated

If you can answer these questions about the new service now, you'll see a much better return on that investment as it ages.

---

## Counter strategy: invest in glue
+ Systems outweigh components
+ Control interfaces
    + Wrap, abstract, define APIs
    + Maintain client lists
+ Manage with code
+ Ongoing training / CPD

{% if include.pres %}Note: {% endif %}
In the past systems could only be provisioned by filling out text boxes in web interfaces.
This meant that replicating that configuration was a hard task that required incredible discipline.
Nowadays the volume of system components has increased dramatically, further stretching that manual click-and-tick process.
The cost of it going wrong is high.
A single missed firewall port or an unencrypted volume might mean a data breach and a GDPR fine running into millions.

This has contributed to a greater emphasis on security, and provably correct security at that.
The way the system is put together matters.
If it's going to play a key role:
* a stand-by system may be necessary to maintain delivery through and recover from a disaster
* problems anywhere in the system need to be identified by proper monitoring
* upgrades and downtime need to be managed carefully
* data need to be backed up and archived, and sometimes deliberately removed
* the performance of the system against a set of requirements or test suite may need to be affirmed

All of a sudden, there's no longer just a single instance of these components.  There could be multiple similar environments:

* dev, for developing new integrations or swapping out components
* test, for verifying continued performance
* staging, for testing new updates
* production, for live operation
* DR, for falling back to in a disaster

In fact, there could be more than one instance of each of these.

This myriad of components could be managed with thorough and rigorous documentation, or better with code.
Code affords those responsible for the system as a whole:

* to demonstrate its performance
* to demonstrate its functionality
* to demonstrate its robustness
* to demonstrate its resilience
* to demonstrate its flexibility

> Investing in staff development is crucial.  Their ability to adapt and grow, with the system as it changes, fundamentally underscores the organisation's ability to deliver.

Few organisations have their infrastructure described as code now.  If the next decade continues these trends towards complicated systems and high-cost downtime, it will be pervasive.

---

## Counter strategy: seasonal purchasing
+ Know your vendor's year-end
+ Plan in September (YE-6)
+ Trial pre-Christmas (YE-4)
+ Train in the new year (YE-3)
+ Purchase in March (YE-1)

{% if include.pres %}Note: {% endif %}
Vendors have salespeople, who typically work on yearly targets.
Knowing when those salespeople will be most incentivised to give you a good deal plays in your favour.
This is often a narrow window, so it takes real planning and commitment to be ready for that.  Purchasing a small number of seats, licences or units allows you to run a trial and train staff ahead of negotiating a major programme of work.

---

## Counter strategy: hope not hype
+ Budget determines Hype cycle position
+ Pragmatism about timescales
+ Tech purchases don't change people

{% if include.pres %}Note: {% endif %}

Gartner's Hype cycle is one of the best known route maps for technology adoption.
Where you are and when you 'jump' or 'plump' or 'flump' for the next big thing is often determined by budget and aspiration.
There's a lot of pain at the cutting edge, but more if left behind.

Ultimately it's people that drive successful technology adoption projects.  Understanding where your team positions itself is not a strategy to be dictated but a cultural discussion to be fostered (see Peter Drucker's breakfast).

---

## Counter strategy: digital culture
+ Adaptive
+ Responsive
+ Curious and experimental
+ Stable and solid
+ Resilient

{% if include.pres %}Note: {% endif %}

Finally and perhaps most importantly is culture.
It's often forgotten or overlooked, too easily consigned to a post-launch "campaign" to get users to behave differently.
Creating a digital culture capable of squeezing greatness out of technology is hard.
It requires constant commitment and an authentic belief that it's better.

Innovation is cheap to pretend to, but very costly to embody.
It's often based on extensive trial and error, which by nature is inefficient.
One of my mentors used to say "don't worry about trouble, just find the right kind of trouble!" 
It's not all perfect and plain sailing, neither should it be.

Innovation-driven inefficiency is a great example of the right kind of trouble.
Yes, resources are not deployed in the most anaemically efficient way, but that's a good thing.
Innovation is the life blood of any organisation that recognises change as endemic.

---

## Help

If you'd like help organising and preparing your digital strategy, working with your team to foster a data-driven culture, or just training in the nuts and bolts of infrastructure as code, please [get in touch](/contact).

