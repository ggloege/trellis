---
title: Project Risk and Governance
subtitle: The Day-One Questions
chapter: 12
order: 12
part: III
part_title: The Project Layer
slug: project-risk-and-governance
---

The Risk section of the canvas exists because some questions are too important to wait on. They are not the kind of risks that get discovered while the project is running. They are the kind that need to be asked on day one — when the project's shape is still flexible, before commitments have been made that are hard to walk back.

There are four of them. What could go wrong. Whose data is involved. What is our ethical stance if this works too well. And who is watching, if no human is in the loop. None of these need a comprehensive answer at the start. They need an honest, short, written answer — sketched lightly, like the rest of the canvas — that the project carries forward and revises as it learns.

### What could go wrong

The first question is the most basic, and the one teams most often answer too narrowly.

The natural answer focuses on first-order failures: the AI gives wrong answers, the system goes down, latency spikes, users get frustrated. These are real risks and worth naming. They are not, however, where most AI projects actually break.

The risks that bite tend to be second-order — things that happen because the AI works, not because it fails. The hiring screen that works well and reproduces existing biases at scale. The drafting assistant that works well and slowly erodes the writing skill of the people using it. The recommendation system that works well and traps users in narrower content over time. These failures do not show up early. They show up later, after enough usage has accumulated for the second-order effect to become legible.

The day-one answer names both layers. Two or three sentences on the first-order failure modes (what breaks, what the bad output looks like, what the worst-case visible failure is) and two or three on the second-order effects (what changes about people, work, or relationships if this works exactly as we hope). The second part is the part teams skip. It is also the part that, looking back, will have been the most useful thing on the canvas.

A lightly sketched answer might read: *First-order: model could classify support tickets incorrectly, leading to misrouting and degraded response quality. Second-order: agents may stop developing their own classification judgment if the tool always pre-fills it; the team's ability to spot novel ticket types could erode over time.* That is enough to start.

### Whose data is involved

The second question asks who, exactly, the data being used belongs to — and on what basis is it being used.

Three things get named. *Sources* — what data this project touches, and where it came from. *Consent* — what the people whose data this is understood when they provided it, and whether the current use is consistent with that understanding. *Sensitivity* — how serious it would be if this data leaked, was misattributed, or was used in a way that violated the original agreement.

The most common failure here is treating consent as a legal compliance question rather than a substantive one. "It's in the terms of service" is sometimes the right answer for the lawyers and almost never the right answer for the customer. The question worth asking is what a thoughtful version of the person whose data this is would think if they were told, in plain language, what was happening with it. If the answer is "they would be surprised, and not in a good way," the project has a consent problem regardless of what the legal documents permit.

The day-one answer is short. A description of the data sources, who they belong to, what those people understood at the time, and a quick read on whether the current use of the data is within the spirit of what they agreed to. As the project scales, scope tends to expand — more data, more people, broader use. The canvas tracks the expansion so it can be evaluated honestly each time, rather than discovered after the fact.

### Ethical stance if this works too well

The third question is the one that distinguishes this framework from most. It asks: what is our stance if the project succeeds, exactly as we hope, at full scale and full speed? Where is the line we would not cross even if the technology made it easy?

This question matters because most AI initiatives that produce regret outcomes do not produce them through failure. They produce them through unconsidered success. A pricing system optimized for revenue, deployed at scale, may well do what it was asked to do — and erode the customer relationship in the process. A customer service automation that successfully removes 80% of human interaction may well hit its operational targets — and gut a brand promise that was never written into the project goals. The plant that grows fastest can shade out everything else around it. A thriving project does not necessarily mean a healthy garden. The technology working is sometimes the worst-case outcome, not the best-case.

The day-one answer is a "we would not be okay with" statement. Specific. Honest. Hard to walk back. *We would not be okay with the model issuing customer-facing communications that no human had read, even if accuracy stayed high.* Or: *We would not deploy this if the success state involves more than one in twenty interactions feeling impersonal to the customer.* The sentence puts a stake in the ground. The team knows what they are aiming for and what they would refuse, even at the cost of a successful pilot.

This stance is meant to be revised, not because the team gets weaker on it, but because reality teaches them what the line actually means in practice. The first version of the stance is almost always too vague. By the third revision, it is concrete enough to use as a decision rule.

### Autonomy and oversight

The fourth question asks: when the system is running, who is watching it?

Three levels are worth naming. *Human-in-the-loop*: every output the AI produces is reviewed by a human before it takes effect. *Human-on-the-loop*: a human supervises in aggregate and can intervene, but does not pre-approve each output. *Human-out-of-the-loop*: the system runs autonomously, with after-the-fact review at most. Most pilots in this framework start in-the-loop and only graduate to lower levels of supervision with evidence.

The day-one answer specifies which level the project starts at, and what would have to be true to move to the next one. The "what would have to be true" part is the important half. Without it, the autonomy level either drifts upward without scrutiny ("the system has been running fine, we stopped checking individual outputs three months ago") or stays unnecessarily heavy ("the human is rubber-stamping every output and not really reviewing it"). Both states are operationally fragile, and both produce bad outcomes when something does eventually go wrong.

A lightly sketched answer: *Starting human-in-the-loop; agents review every output before it goes to the customer. Move to human-on-the-loop only if override rate stays under 10% for four consecutive weeks and the team lead reviews a weekly sample without finding new failure modes.* That is testable. Either the conditions are met or they aren't.

### Risk questions are policy questions in disguise

The four risk questions get answered at the project level, but they are the questions most likely to surface patterns that belong in the Global Policy Layer.

When three projects in a row land on the same data consent question, that is evidence the question belongs to the organization, not to any individual project. When four projects in a row need to articulate a similar ethical stance, that is the seed of an organization-wide principle about what AI deployments will and will not do. When several projects in a row use the same autonomy progression, that progression has become a standing protocol.

The day-one questions stay sharp at the project level even as their patterns harden into policy above. Each project answers them honestly with what it currently knows, and the cumulative answers are what fill in the policy layer over time.

The next chapter expands the project canvas in a different direction — to capability projects, which run through the same canvas and the same questions, but exist to build the organization's capacity to use AI rather than to deploy it operationally.
