---
title: Project Readiness
subtitle: People, Data, Culture, Governance, Incentives
chapter: 10
order: 10
part: III
part_title: The Project Layer
slug: project-readiness
---

The Readiness section of the project canvas is where you assess whether the organization can actually run the project you are proposing. Five dimensions get sketched: people, data, culture, governance, incentives. Each one is independently capable of stalling or sabotaging an otherwise-good project. Each one has a characteristic failure mode that does not look dramatic from the outside — projects rarely fail because of dramatic problems. They fail because of one or two readiness gaps that nobody named at the start.

The discipline this chapter teaches is light, deliberate sketching. None of these dimensions need to be perfect before a project starts. They need to be *named*. You take a stand on what you currently believe about each one, knowing parts of your stand will turn out to be wrong. As the project runs, the picture sharpens — readiness moves from sketch to substantiated assessment, and the gaps that show up across multiple projects start surfacing as candidates for the Global Policy Layer.

### People

The People dimension covers three things bundled together: skills (does anyone on the team know enough about AI to make sensible decisions about it?), trust (do the people whose work will change trust that this is being done thoughtfully?), and capacity (do they have the time to work on this without breaking the things they are already responsible for?).

Ready does not mean a fully staffed AI team. It means at least one person on the project has done enough homework to be genuinely useful — not necessarily an ML engineer, often a product person or domain expert who has put in the hours. It also means the people whose work is going to change know what is happening before they are surprised by it. They do not have to love it. They just shouldn't find out from a Slack message at 5 p.m.

Not ready typically looks like a project being run on top of someone's already-overcommitted plate, with the affected population unaware. Both gaps are recoverable, but they are not ignorable. A project sketched lightly here might say: *Lead is X, with three hours per week and no prior AI work; affected population is the customer support team; they have not yet been informed.* Three sentences. Each one true, each one specific, each one clearly a decision the project has not yet made.

### Data

The Data dimension covers availability, quality, and access. Availability is whether the data this project needs actually exists in the organization. Quality is whether it is any good. Access is whether the right people can use it without a months-long path through legal and IT.

The most common readiness failure here is not absence of data but unverified assumptions about it. Someone on the project says "we have the data," and the project starts running on that assumption. Six weeks in, the team discovers that the data exists in theory but the specific fields they need have been blank for two years, or the data is correct but lives in a system nobody has access to.

Light at start means a sketch like: *Source is the customer support ticket archive, last touched in 2023; quality unknown; access requires Sarah's team and an okay from legal.* That sketch is not an answer. It is a working description of what you don't yet know. The early phases of the project will turn each item into something firmer. When the data turns out to be unusable, the project either pivots or is shut down — the canvas tells the story honestly because the original sketch was honest.

Data is also the dimension most likely to surface patterns that move to the policy layer. When three projects in a row hit the same access bottleneck, that bottleneck has crossed from a project-level concern to an organization-level one.

### Culture

The Culture dimension asks whether the way this project will run is consistent with the principles the organization actually stands by. Most organizations have implicit cultural norms about how customers are treated, how decisions are made, what kind of automation is acceptable, what would be a brand betrayal. These norms are rarely written down. They show up when an output of the project lands in front of a leader and the leader's first reaction is "we can't ship that."

Ready means the team has had a working conversation about the cultural envelope — what kinds of outputs would and would not be okay, even if technically successful. They don't have to have it all written down. They have to have thought about it.

Not ready typically looks like a team that is heads-down on the technical problem and has not yet asked what the organization will refuse to deploy. The classic example is automating a moment that customers expected to feel human. The pilot works. The output gets surfaced to leadership. Leadership says "this is exactly what we wouldn't want to be." The project dies six weeks of work after it could have died in twenty minutes.

The light sketch is a single sentence: *We would not ship a version of this that did X.* That sentence makes the cultural envelope visible. Hardening means checking the project's actual outputs against the envelope as they appear.

### Governance

Governance, in this framework, is about decision speed. Not decision rights in the abstract — decision speed in the concrete. Can this project actually move at the pace it needs to move at? Or does every meaningful decision queue behind a committee that meets monthly?

Ready means there is a clear answer to "who can approve what," and the answer is at a level where decisions can happen in days rather than weeks. The project has a sponsor with real decision rights, not nominal ones. Course corrections during the pilot can be made by people who are actually paying attention to the project.

Not ready looks like governance at the wrong altitude. The CTO is the only person who can approve a $5,000 tooling decision. The committee that has to bless changes to the pilot scope meets the third Wednesday of every month. The project does not fail dramatically; it slows. Each week is a little less productive than the last as decisions queue up. The team gets quieter. The project becomes a thing nobody can quite kill.

Light at start: *Sponsor is Alex; project lead has authority on tooling and scope under $10K; anything above that goes to Alex within a week.* That is a working answer. It can be wrong, and it will probably need to harden as the project scales. But it is decision-able now.

### Incentives

The Incentives dimension asks the question almost no one asks at the start of an AI project: is anyone in this organization rewarded for making this succeed? Not formally signed up for. Not nominally supportive of. Actually rewarded — in their performance review, in their bonus, in the things their boss is going to ask them about.

Ready means there is at least one person whose meaningful success metrics include this project's outcome. Their stake is not "don't break anything." It is "make this work." They will lose something concrete if it fails.

Not ready is the most common readiness failure of all, and it is the hardest to see. Everyone says they support the project. Status meetings happen. Slides get updated. Nobody does the thing that would actually move the project forward, because nobody's day-to-day reality includes a consequence for it not moving. This is what kills more pilots than any other single factor — not a technical failure, not a data failure, but the slow death of a project nobody is materially on the hook for.

Light at start: a name and a sentence about how the person's success metrics include this. If the answer is "no one yet," that is a finding, and the project should not start until it has been resolved. This is the one readiness dimension where a missing answer is not a sketch — it is a stop.

### How readiness sharpens over time

The point of light, named sketches at the start is to make the project's beliefs visible. Readiness on each dimension sharpens as the project runs. People on the team learn the technology. Data assumptions get tested. Cultural envelopes get refined as outputs appear. Governance arrangements get pressure-tested by actual decisions. Incentive structures get adjusted as the project's scope changes.

The other thing that sharpens is the organization's awareness of which readiness gaps are project-specific and which are systemic. The Global Policy Layer fills in around the systemic ones — a learning function for recurring people gaps, a data hygiene program for recurring data gaps, a governance protocol for recurring decision-speed gaps. A readiness gap a project encounters once is the project's problem to solve. A readiness gap the organization keeps encountering is the policy layer's problem to absorb.

The next chapter takes up the second section of the canvas — the project roadmap, where the plan itself lives.
