---
name: "monolith-implement"
description: "Carry a stated job through to a finished, verified deliverable held to rigorous, present-day correctness: ground in the live work, verify every external assumption at the source, and eliminate or never introduce anything broken, obsolete, duplicated, incoherent, or worked-around. The job is whatever the user states, such as a feature, a fix, a subsystem, a document, an agreement, an assignment, a model, or a whole body of work, and it holds that job and everything in its blast radius to the same standard so the work is done right in one pass rather than patched and checked later. It works until the deliverable is ready for the people it is for, verifying itself along the way against up-to-date, authoritative references. This skill is strictly manual and must only be invoked by name, Monolith Implement."
metadata:
  author: "Leeor Nahum"
  version: "2.1.0"
---

# Monolith Implement

Treat this work as if you are accountable for every part of the body of work it belongs to. Your benchmark is *current intentionality*: what the work is meant to be right now, read directly from its present state, the contracts written in it, and the job the user handed you, not from memory, older plans, or past intent. Remove, and never introduce, anything that is broken, outdated, assumed-but-wrong, duplicated, unnecessary, or surviving as a leftover workaround. When done, everything you touched is accurate, essential, and clearly connected to the live contract.

This is intensive and uncompromising. No corner is skipped, no layer is assumed clean, no finding is left unanswered:

- Read widely and deeply across the present work, every reference it points to, and its other versions or branches.
- Verify every detail from first principles and at the source, never from memory.
- Spawn subagents and specialist checkers for parallelism, context isolation, or niche domains. Do not rely on a single context window.
- Anticipate downstream effects: build and fix root causes, not symptoms.

## Scope: The Stated Job And Its Blast Radius

The user states the job. It may be as wide as a whole body of work or as narrow as one feature, fix, section, clause, or part. When neither the invocation nor the conversation before it states a job, or the job is too vague to tell what finished means, ask what is wanted before starting.

An invocation covers every deliverable produced for the stated job, including work handed to a subagent, which is told to follow this skill by name. When later work in the same thread may or may not belong to the job, ask.

Apply this rigor to the job and everything in its blast radius, whatever depends on it and whatever it depends on, still judged against the whole work's current intentionality. Fix whatever the job cannot be correct without, wherever it sits. Report everything else you find wrong, and leave it unchanged. Ground and verify before you build, hold everything new to the same standard as the work it joins, and check as you go rather than patching first and cleaning up later. Doing the job this way means doing it right in one pass.

Scale Step 1 grounding to the job. A whole-work job grounds the whole of it. A narrower one grounds only what it depends on and delivers into, and skips any wider release the job does not need. Every other step applies in full at the job's scope: verify at the source, build or fix to the contract, confirm with subagents, and reconfirm after editing.

## Step 1: Fully Ground Your Work

Align your baseline with the true, current state of the work and the rules you will apply:

- Ensure what you are looking at matches the current state of the work and the tools in use. Do not proceed based on outdated files or stale assumptions
- Review documentation and the conditions the work lives under to confirm you are working with current and reliable information. Avoid acting on information you have not directly checked
- Pay close attention to where the work is actually in use, such as what is deployed, published, filed, or printed, so what you build reflects what is truly live. Never assume a local copy matches it
- Read the real and present work. Ignore planning, wishlists, and design history. Your reference is today's work, the contracts explicitly written in it, and the job as handed to you. Where the job decides something differently from what is written in the work, the job is the newer intent and wins. Where the work, its contract, or what is live disagree among themselves, the intended contract wins and you surface the discrepancy

## Step 2: Cross-Check Against First-Party Sources

Verify the present work against the authoritative source for everything outside it that it relies on, and correct what has drifted:

- For each outside thing the work depends on, such as a service, library, platform, protocol, standard, statute, rubric, or specification, open the current official first-party source, never memory and never third-party summaries, and check the work against it.
- Confirm the interfaces, shapes, terms, and contracts the work assumes still exist and behave as used. Flag and correct anything deprecated, removed, renamed, superseded, or misused.
- Seek working examples and reference implementations for ambiguous or critical behaviors, because prose sources often leave key details unstated.
- Treat as a defect any assumption the canonical sources or examples do not fully support.

## Step 3: Apply Every Applicable Skill

- Read every skill that applies to the work, wherever it is available (system-wide, in any nested tree, or served by a connected skill library), from top to bottom, including every reference file it carries. Bias hard toward loading: when a skill might apply, read it in full, never a skim or its description alone, because reading deeply is cheap and acting on a topic blind is not.
- Execute all of their rules, especially the design, naming, and maintenance rules that touch the layers you are working in.
- Apply the audience-facing and design-coherence checks to everything a person will read, see, or use, walking a real end-to-end scenario.

## Step 4: Cover Every Layer In Depth

Name the layers the work has before building. They are the claims it makes, the steps it tells a reader or a user to take, and every surface those steps run on. Then vigilantly check, as you build and as you review, for anything broken, obsolete, unverified, dead, duplicative, patched, or otherwise unsound across each of them, held to the same standard.

For software, the layers are at least:

- Backend logic and contracts
- Data models and schema (look for drift between schema and usage)
- HTTP APIs and their actual and published contracts
- Protocol servers, transports, and handshakes
- Authentication, identity, and capability checks
- Environment contracts and stage isolation
- Background work, failure modes, and retries

For each change, map everything upstream and downstream that relies on it, the possible failures, and what future maintenance will assume about the behavior.

## Step 5: Build To The Present Standard

- Build new work, and rewrite every defect or gap, toward the current intended contract, not a workaround or a compatible shim.
- Tear out every workaround whose original reason no longer exists, and add none. Leave no orphaned workaround that might mislead a future reader.

## Step 6: Confirm With Adversarial Subagents

The builder never grades its own work, and loading a skill or rereading its own text against one is not a check. Every pass of this skill runs at least two independent checks before anything is called done, and waits for each check to return and its answer round to finish before ending the turn, because a session that ends while a critic is still running has skipped it. The report names, in one line, the model behind each check and what it checked. The job, a subagent's brief, or any later instruction can narrow the scope of the work, never this loop, and a subagent's brief carries the loop whole:

- **An adversarial critic, from a different provider than the builder when the user has one**, running that provider's strongest model of the kind it uses by default, never one above that unless the user names it, chosen and spawned by the subagent-spawn-book skill where it is available, installed or read at [![subagent-spawn-book on RemoteSkill](https://remoteskill.md/subagent-spawn-book-3XELJKmGsF1U/badge.svg)](https://remoteskill.md/subagent-spawn-book-3XELJKmGsF1U), and told plainly that its job is to find what is wrong, not to validate. Its task says what finished means and the point at which it hands back what it has, since a critic with an open goal runs until its usage allowance is spent. It receives the goal, the changed work and what depends on it, every instruction the builder was given, the skills, the instruction files that govern the work, the user's own words, and the first-party sources from Step 2. It does not receive the builder's justifications for its choices, so it judges the work against the goal rather than against the story told about it. The builder gives its reasoning in the answer round. It returns a ranked list with the evidence for each finding, and where it sees a better shape for the work than the one built, it says so as a proposal. Another provider is preferred because a critic from the builder's own model shares its blind spots. When none is reachable, a fresh session on the builder's own provider is a complete check, and the missing provider is not raised as a finding, a risk, or an open point.
- **A separate anti-backrooms pass over every kind of deliverable the change produces**, whatever a person or agent will read, use, or build on, down to its names, notes, and leftovers that read as machine-made. For software that includes the code itself, its structure, comments, and commit messages. It applies the anti-backrooms skill, installed or read at [![anti-backrooms on RemoteSkill](https://remoteskill.md/anti-backrooms-9tQgwGsGh24y/badge.svg)](https://remoteskill.md/anti-backrooms-9tQgwGsGh24y), and reports what reads wrong, not what the source says. When the work has an effect that only shows in use, first operate it once for real the way its audience will, launching, clicking, and typing through the path they take, or reading, printing, or assembling it as they would, and give the pass that actual result beside the same thing produced the normal way, by a model that can see it. Review of the source and validation of its format both miss what only the finished result shows. The pass reads twice:
  - **Cold**, first, in a fresh session given only what the deliverable's real audience will have, and nothing else the builder worked from, such as the specification, the plan, the briefs, or the instructions, until its findings are written down.
  - **Against what it was made from**, afterwards, with those materials beside the result, for whatever crossed from them into it.
- Recursively assign further subagents to complex, cross-cutting, or niche findings, and split the surface among them. No single context is comprehensive enough for a true monolith pass.
- Only claim a finding with direct evidence: a file, a first-party source, or a reproduced interaction. The builder answers every finding and every proposal in writing, and a refusal with a reason is a valid answer. A finding read and not answered launders the decision.
- The answer goes back to the same critic, resumed by its session id so it keeps its context, and it says which findings it withdraws and which it holds. Two rounds settle most disagreements. What is still held after that goes to the user as an open point, not silently dropped. A held finding that reopens a decision the user already made is answered by that decision.
- Run this loop per unit of work, not once per delivery. Tell the critic to separate what blocks delivery from what should merely be recorded and, when it has a workspace it is authorized to write to, to keep one findings file there, adding each finding as it confirms it, verdict first, so a run that dies still leaves its report.
- Aim later rounds at the seams. Each unit is verified alone, so where two verified units meet is the part nobody has reviewed, and it is where the real defects live.
- Expect a critic's list to undercount. When a critic names several instances of a problem, ask why the rule was enforced in each place separately, and find the others. Prefer moving the rule to one place everything must cross, such as a single record or gate, over adding the same check at one more place.

## Step 7: Reconfirm After Edits

After applying changes, do not move on. Re-read everything changed and what relies on it:

- Confirm the change matches the intended contract, introduces no new smell, and aligns with applicable skill rules and first-party sources.
- Spawn a fresh adversarial critic, chosen as in Step 6, over anything changed after a critic's last round, and a fresh anti-backrooms pass, cold first, over everything that changed. Nothing is delivered that no critic has seen.
- Catch regressions, partial fixes, and newly exposed issues before declaring a layer clean.
- Whoever delivers the work reads or uses the finished result itself, the way its audience will, before handing it over. A pile of passing reports is not a look at the thing.
- Map every explicit intention and requirement the user stated, corrections given earlier in the thread included, to where it is met on each affected surface, integration, contract, and test, whether or not the user named that surface. A requirement that is missing from any of those places is not done.

**Check the checks that support the verdict.** Assume some checks verify something adjacent to what they claim, because that failure is common and invisible. Ask of each check what would have to be true for it to pass while the thing it names is broken. Then, on a copy kept apart from the work, break the thing on purpose, see that the check notices, and restore it. For software this is a mutation check: break a guard in an isolated test copy and confirm its test fails for that defect. A check that survives the break has a gap in its evidence. Strengthen it before trusting its claim, and retain any protection the work needs in use. Bound the run so a hang or resource failure remains a distinct result, not proof that the check caught the defect.

## Step 8: Close Out

Deliver what the stated job authorized, and nothing past it:

- Do the work to this standard in one pass, follow the verification and release process the job defines, and commit, publish, or hand over only as it directs. Leave nothing half-done and no new workaround behind.
- Report what you found wrong and left unchanged, each with its rationale and where it is, so the user can decide.
- A fact that looking can settle is looked up before the work is called done, never passed to the user as a request or reported as unchecked.
- Hand work to an outside review or approval queue only after every planned check has run, since a later change restarts the wait.
- Reconfirm before declaring done, and never make an outward-facing or irreversible change the user has not sanctioned. A reversible step the user already authorized is done, not asked about again.

Run this with absolute thoroughness and no tolerance for partial or low-impact work. Do it right the first time: exterminate accidental complexity, legacy deadweight, and every violation of present best practices, reconfirming at every stage until the work is truly clean.
