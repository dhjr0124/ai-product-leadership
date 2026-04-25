# The First 90 Days as an AI Product Leader

A field guide for senior product leaders joining a company that has decided it needs AI but has not yet figured out what that means. There is no AI strategy waiting for you. There is no team of fluent practitioners. There is, most likely, a CEO with a board mandate, an engineering org with mixed feelings, and a product team that has been told "we need to do something with AI" without being given the time or training to figure out what.

This is the most common scenario in 2026, and it is the job. The 90 days that follow are not a strategy exercise — they are a deliberate program for taking a non-fluent team and making them genuinely capable of building with AI, while shipping concrete operational wins along the way. Concrete is the operative word. Generalities will not get you anywhere with a team that needs to see what good looks like.

---

## Operating Principles

Before the plan, the principles it rests on:

**Show, don't tell.** A team becomes AI-fluent by watching their leader use AI on real work, in front of them. The fastest path to a capable team is a leader who pulls up Claude or Cursor in a meeting and says "let me show you how I'd do this." Slide decks about AI strategy do not teach AI fluency. Doing the work in the open does.

**Productivity wins build trust for the bigger work.** Before anyone trusts you to redesign their roadmap, they need to see AI save them an afternoon. The first 30 days are full of small, visible wins — Jira tickets drafted in seconds, release notes that write themselves, architecture reviews that catch what humans missed. These wins are the political capital you'll spend on harder changes in months two and three.

**Learning is the work, not in addition to it.** Teaching sessions, brown bags, paired building — these are not "extra" things the team does on top of their day jobs. They are the day job for the first quarter. A leader who treats learning as something that happens "when we have time" is signaling that AI fluency isn't real work. It is.

**Templates and skills compound.** Every prompt, template, and skill the team writes down becomes leverage for the next person who needs to do the same thing. A team that builds a shared library of reusable artifacts in month one is a team operating at 3x by month four. A team that does everything ad-hoc is still doing everything ad-hoc at month twelve.

**Fluency is measurable.** "We're getting better at AI" is not a metric. "Every PM ships at least one prompt-driven workflow per week" is. "Every engineer has reviewed code with AI in the last sprint" is. Define the baseline early, measure against it weekly, and the team's progress becomes visible to them and to leadership.

---

## Days 1–30: Establish the Baseline and Generate Quick Wins

The first month is about two things in parallel: understanding the business well enough to know where AI belongs, and getting the team using AI on their existing work immediately. These are not sequential. The team should be using AI on day five, not waiting for a strategy to be written.

### Understand the business

Run a structured listening tour with every direct report, every adjacent function leader, and at least three customer-facing roles. Ask the same questions to everyone:

1. Where do you waste the most time today — yours or the customer's?
2. What decisions in our product are made on judgment that's mostly pattern-matching?
3. What have we already tried with AI? What happened?
4. What has leadership promised that you're worried we can't deliver?
5. What is the most repetitive thing you do every week?

The fifth question is the most important. The answers point directly at where the first AI wins will come from.

### Assess current fluency, honestly

Within the first two weeks, run a structured fluency assessment with each team member. Not a test — a conversation. What tools have they used? What have they built? Have they shipped anything to production with an AI component? Have they written an eval? Have they used Cursor or Claude Code on real code? Most teams will land in three buckets: a few who are well ahead of the curve, a middle that has used ChatGPT but not built anything, and a few who are quietly avoiding AI altogether. Knowing precisely who is where is what makes the next 60 days plannable.

### Get the team using AI on real work — within two weeks

This is the most important thing in the first month. Start with three concrete uses of AI that should be happening across the team by week three, and add the others as the team is ready:

**Start here — three uses for week three:**

**Jira ticket creation.** PMs and engineers should be using Claude or Cursor to draft tickets from a one-line description, including acceptance criteria, edge cases, and test scenarios. This alone saves hours per person per week and produces better tickets than most teams write by hand. Low risk, immediate payoff, and a useful first exercise in writing prompts that produce structured outputs.

**Release notes and changelogs.** Generated from PR descriptions and commit messages, then edited for voice. A weekly task that used to take two hours becomes fifteen minutes. Another low-risk starting point — the human edit pass catches anything wrong before it ships, and the team builds reps on prompt iteration.

**Meeting prep and follow-ups.** Customer call summaries with action items extracted, internal meeting notes that surface decisions and owners, draft emails to follow up on commitments. The least glamorous use case and one of the highest-leverage. Risk is low because the human is reviewing before sending.

**Add as the team is ready — typically by end of month one or into month two:**

**Code and architecture review.** Engineers should be running existing code through Claude with prompts like "what are the failure modes I haven't considered" and "where is this architecture going to break at 10x scale." Not as a replacement for human review — as a first pass that catches the obvious things and frees humans for the subtle ones. Adding this earlier than the team is ready can produce false confidence in AI-generated reviews that miss real issues; wait until engineers have a few weeks of fluency under their belt and clear norms about what AI review is and isn't.

**Documentation drafts and gap analysis.** Run existing documentation through AI and ask "what would a new engineer need that isn't here." Use the output as the starting point for closing those gaps. Most teams discover their docs have 40% coverage of what they thought was 80%. This works best once the team has internalized the prompt-iteration cycle, which usually clicks somewhere in week three or four.

By end of month one, every team member should be doing the first three on a recurring basis, with the second pair starting to land. Not as an experiment — as how they work now.

### Establish the baseline training

Every team member completes a foundational set of AI courses in the first 30 days. This is non-negotiable and is paid time, not after-hours. Anthropic's courses on Claude and prompting are a strong foundation and the place I'd start most teams — they're well-structured, free, and produce shared vocabulary quickly. Pair them with one course from a different provider — DeepLearning.AI, OpenAI's documentation and cookbooks, or Maven cohorts — so the team gets a second perspective and isn't anchored to one model's framing. The goal is shared vocabulary by day 30. When someone says "context window" or "system prompt" or "eval," everyone should know what they mean.

### Introduce primitive eval thinking from day one

Even before the team can write a formal eval suite, they need the question "is this output actually good?" to be in the room every time they ship AI-generated work. From the first week, when someone uses AI to draft a Jira ticket or a release note, the practice is: define what "good" looks like before generating, spot-check the output against that definition, log the failures somewhere shared. This is not the formal eval discipline that comes later — it's the cultural seed of it. Without this in month one, the team builds habits of accepting AI output uncritically that take months to undo.

### Get the engineering hygiene in place — now, not later

A surprising number of teams new to AI also have weak Git and deployment practices, and AI development surfaces this immediately because the iteration cycle is so fast. Engineers and PMs are about to start editing prompts in the codebase, generating code with AI, and shipping changes faster than the team has been used to shipping. If the basics aren't solid by the end of month one, the team accumulates bad habits — committing directly to main, skipping PRs for "just a prompt change," no rollback discipline — that become much harder to fix in month three.

In the first 30 days: a working session on branching strategy, pull request hygiene, deployment practices, and rollback procedures. Engineers who think they know this often don't, and PMs who are now editing prompts in the codebase need to learn it from scratch. Pair the training with real practice — every team member should ship at least one PR by day 30, including PMs who haven't shipped one before. The deeper Cursor and Claude Code workflow training (CLAUDE.md, sub-agents, hooks, skills) comes in month three; the basics come now.

### Start the weekly teaching ritual

Beginning week two, hold a weekly 90-minute group session that everyone attends. The format is consistent: 30 minutes on a concept (rotating teacher each week), 45 minutes of paired building on real work problems, 15 minutes of show-and-tell where two people demo something they shipped that week using AI. This single ritual is the highest-leverage thing in the entire 90-day plan. It teaches, it builds shared culture, it surfaces what's working, and it makes AI fluency a public commitment rather than a private struggle.

The leader teaches the first session. Then it rotates. Anyone can be the teacher; some weeks the strongest teaching comes from the team member who learned a thing two days before they presented it.

### Begin the templates and skills library

By day 21, the team has a shared repo or workspace where every reusable prompt, template, system prompt, and reusable AI artifact goes. The Anthropic ecosystem makes this concrete with `.md` files, CLAUDE.md project conventions, and Claude Skills — these are useful starting structures and worth using as the team's organizing pattern if Claude is the primary tool. Teams using other tools have analogous patterns: Cursor's `.cursorrules`, OpenAI's custom GPT instructions, structured prompt libraries in Notion or a Git repo. The format matters less than the discipline of writing things down. Even crude versions count. The library at day 30 will be embarrassing; the library at day 90 will be one of the team's most valuable assets. Make adding to it a regular act, not a special occasion.

### What you should have at day 30

A clear, written assessment of each team member's AI fluency baseline. Three recurring AI uses adopted across the team, with two more on the way. Every team member through the foundational courses. A weekly teaching ritual running with full attendance. A nascent templates and skills library with at least 15 entries. Basic engineering hygiene in place across the team, with every member having shipped at least one PR. Primitive eval thinking — "is this output good?" — visibly in the room when AI-generated work is reviewed. A list of five to ten candidate problems where AI might create real product value, ranked by impact and feasibility. Visible productivity wins — measured in hours saved per person per week — that you can point to in your first leadership review.

---

## Days 31–60: From Personal Productivity to Team Capability

The first month was about each person using AI on their own work. The second month is about the team using AI together — building real things, identifying systemic gaps, and starting to apply AI to the product itself, not just to internal workflows.

### Push every team member to audit and automate their daily work

By day 35, every team member produces a written audit of their own work: what do I do every week, every day, every hour, and which of these tasks could AI do partly or fully? The output is a personal automation backlog with three categories — "automate now" (this week), "automate soon" (within two weeks), and "needs help" (will pair with someone). This is reviewed in the weekly teaching session and revisited monthly.

The point is not just the time saved. The point is that team members start thinking like AI builders by default. Once you've automated your standup notes, your PRD draft cycle, your customer call follow-ups — you start seeing AI applications everywhere, including in the product.

### Start building proofs of concept on real product problems

In month two, the team graduates from internal productivity to product-facing builds. Pick two or three real workflow problems identified in the month-one listening tour and build proofs of concept for each. Not polished features — POCs. Working code, real data, real users (internal or design partners), enough fidelity to learn whether the approach is viable.

The team builds these in pairs or small groups, not solo. Pairing a fluent team member with a still-developing one is the fastest way to lift the whole team. The learning that happens in a four-hour pairing session is worth more than two weeks of solo experimentation.

### Build out the existing portals and surfaces so AI features can ship fast

A common failure mode in month two is that the team has ideas but the existing product can't host them quickly. Use this month to invest in the boring but essential infrastructure: a feature flag system if there isn't one, a way to A/B test responses, an admin surface where prompt and model changes can be made without a full deploy, a logging pipeline that captures inputs and outputs for later eval. This is not glamorous work, but skipping it is what turns month four into a swamp of "we can't ship this because the existing system can't handle it."

### Identify documentation gaps and close them with AI

Run a systematic AI-assisted audit of internal documentation. Architecture docs, runbooks, onboarding materials, customer-facing help content, API docs. For each gap identified, assign an owner and a deadline, and have them use AI to draft the closing content. The goal at day 60: documentation coverage that is materially better than at day 30, with the work distributed across the team, not concentrated on one person.

### Start mapping the voice of the customer with AI

By week six, begin a deliberate program of using AI to capture and synthesize customer voice. Customer call transcripts run through Claude to extract themes, pain points, and requested features. Support tickets categorized and clustered. Sales conversations mined for objections and use cases. The team should be experimenting with multiple approaches here — there is no single right way to do this in 2026, and finding the team's preferred patterns is part of the learning.

This work is also recruiting in disguise: it identifies which team members have a natural product instinct for working with AI-derived insights, which is information you'll need in month three when you're thinking about role assignments.

### Templates, skills, and reusable artifacts become a deliberate practice

The library that started informally in month one becomes structured in month two. Every recurring task gets a written artifact — a prompt, system prompt, and example outputs. For Claude-using teams, this typically takes the form of `.md` files and Claude Skills; teams using other tools structure their libraries differently but the discipline is the same. The library has an owner (a rotating role, week by week) whose job is to keep it organized and to nudge people to contribute. By day 60, the team should be reaching for the library before writing a new prompt from scratch.

### Continue the teaching rhythm, with deeper content

The weekly group session continues, but the content level rises. Topics now include: how to write a good eval, how to design a prompt for a multi-step workflow, how to use Cursor agent mode on a real codebase, how to work with structured outputs and Pydantic, how to chain prompts, how to build a simple RAG pipeline. Bring in an outside speaker once during the month — a practitioner from another company who can show the team how a more mature AI org operates.

### Begin a second tier of training

Building on the foundational courses everyone took in month one, team members now branch by interest and role. PMs go deeper on AI product management, evals, and prompting. Engineers go deeper on agent frameworks, MCP, and production AI patterns. Designers go deeper on AI UX and designing for uncertainty. Anthropic's intermediate courses, Maven cohorts, and DeepLearning.AI specializations are all reasonable paths. Each team member presents what they learned back to the team in the weekly session.

### What you should have at day 60

Every team member with a personal automation backlog and visible progress against it. Two or three product-focused POCs underway, built by pairs or small groups. Materially improved internal documentation coverage. An active program for mining customer voice with AI. A structured templates and skills library with 50+ entries that the team actively uses. A weekly teaching ritual that has matured beyond foundations into real production patterns. A second-tier training plan in motion. The team visibly more confident than they were at day 30.

---

## Days 61–90: Build the Operating Discipline and Organize the Team

The third month is where you take the productivity, the literacy, and the early POCs and turn them into something that resembles an actual AI product organization. The shape of the team becomes clearer. The roadmap gets re-examined with AI-fluent eyes. Hiring becomes a credible conversation because you finally know what gaps you actually have.

### Re-evaluate fluency and organize the team accordingly

By day 65, run the same fluency assessment you ran in month one. Compare. The progress will be uneven, and that's the point — the assessment tells you who has accelerated, who has plateaued, and who is positioned for what kind of work going forward.

Use this to organize the team into role specializations:

- **Feature builders** — the team members who have shown they can take a problem and ship a working AI-enhanced feature, end to end. They get the smaller, faster product builds.
- **API and infrastructure builders** — team members who gravitate toward the backend, the eval pipelines, the agent infrastructure, the integration work. They build the foundations that the feature builders ship on top of.
- **Reporting and tracking builders** — team members who excel at building the internal tools that measure what's happening: dashboards on AI feature performance, eval result tracking, cost monitoring, model usage analytics. This work is essential and consistently underestimated.

These are not titles or permanent assignments — they are how you slice work for the next two quarters based on demonstrated strengths. People can move between groups, and good leaders rotate them deliberately to build breadth.

### Address the team members who haven't progressed

The fluency reassessment will surface a small group who haven't moved meaningfully since day 30. Before treating this as a performance issue, ask the diagnostic question honestly: did the training and resources actually fit them? Some team members need a different format than group sessions — a structured course they can work through alone, a one-on-one paired week with a fluent peer, a different kind of project to apply skills against. If the training didn't land, it's worth one more deliberate attempt with a different approach before drawing conclusions.

If a second round of well-matched resources still doesn't produce progress, then it's a different conversation. Some people need to move to roles where AI fluency is less central; a small number may need to leave. Don't act precipitously, but don't let the dynamic harden either — a team member who is visibly not engaging with AI work after a fair, supported attempt sends a signal to the rest of the team that has to be addressed.

### Deepen the engineering tooling — Cursor and Claude Code workflows

The basic engineering hygiene from month one is in place; this is where the deeper tooling work happens. By month three, people are using Cursor and Claude Code on production codebases with real consequences, and the difference between casual use and skilled use becomes significant. The teaching session in week ten or eleven should be a deep dive on Claude Code workflows — how to set up a CLAUDE.md, how to use sub-agents, how to write skills, how to set up hooks. Teams using Cursor primarily can run an equivalent session on `.cursorrules`, agent mode, and rule composition. This is the difference between using AI as a chat interface and using it as an engineering tool.

### Use AI to pressure-test the roadmap

By week eleven, run a structured exercise: take the existing product roadmap and use AI to play devil's advocate against it. What are the assumptions? What are the unstated risks? What would a competitor do that we're not? Where is the roadmap weak? Where is it overbuilt? Do this as a group session, with the team feeding the AI different framings and arguing with the outputs. The goal is not for the AI to give you the answer — the goal is to surface tensions in the roadmap that human politeness has been suppressing.

### Measure AI velocity vs. traditional development

By the end of month three, the team has enough shipped work to start measuring something important: how much faster (or not) is AI-assisted development on different kinds of work? Some categories will be 5x faster — boilerplate, documentation, ticket generation, simple feature scaffolding. Some categories will be roughly the same speed — complex business logic, anything requiring deep system context. Some categories may actually be slower — work where the cost of debugging AI-generated code exceeds the savings.

Knowing where the multiplier is real and where it isn't shapes everything: how you scope projects, how you estimate, how you make hiring decisions, and how you set expectations with leadership. Without this measurement, AI velocity becomes a story; with it, it becomes a planning input.

### Set the next two-quarter direction

By day 80, you have enough to set a focused, defensible plan for the next 6 months. Two or three named bets, each tied to a measurable quality bar, each staffed against the role specializations established earlier in the month, each with infrastructure and eval requirements named explicitly. Get explicit alignment from your CEO and your peers; misalignment surfaces here, which is the right time for it to surface.

### Make hiring credible

This is when hiring earns its place, and not before. The operating principle of "the team you have is the team you build with" wasn't a permanent stance — it was a discipline for the first 60 days, when you didn't yet know what you needed. By month three, that's changed. The literacy program, the role specializations, and the velocity measurements have made the gaps visible. You're no longer guessing.

Common gaps at this point: a senior engineer with deep production AI experience to set technical patterns, a designer who specializes in AI UX, an additional AI PM if the surface area is widening, or a data engineer who can own the eval and customer-voice pipelines. Hire one or two people, not five. The team's capacity to absorb new hires is real and limited, and the people you have are now genuinely productive — which means new hires are joining a working team, not rescuing a stuck one.

### Continue the teaching ritual — and start having team members run it independently

The weekly session is now a fixture. By the end of month three, team members should be running it without you in the room some weeks. This is the test of whether the culture is real or performative. If the session continues at the same quality when you're traveling or in another meeting, the team has internalized the practice. If it falls apart, you have more work to do.

### What you should have at day 90

A team organized by demonstrated strengths into clear working groups. Substantial improvement in engineering tooling fluency, building on the hygiene foundation laid in month one. A roadmap that has been pressure-tested with AI and revised accordingly. A real measurement of AI velocity versus traditional development across multiple categories of work. A 6-month direction with named bets, quality metrics, and staffing. One or two thoughtful hires in motion or in seat. A weekly teaching ritual that runs with or without you. A working eval discipline, with at least one feature that doesn't ship without passing its eval suite. A leadership team that trusts your judgment because the team has visibly transformed in 90 days.

---

## A Note on Training and Group Learning

The thing I would push back hardest on, in any company that hires me, is the idea that training is something the team does "in their spare time" or "next quarter" or "once we get through this release." It is the work. A team that spends two hours a week in structured group learning for a quarter ends that quarter capable of things that no amount of solo struggling would have produced. A team that doesn't, doesn't.

The structure that works:

- **Weekly 90-minute group session, every week, no exceptions.** This is the ritual described above. Concept teaching, paired building, show-and-tell. Same time every week. Calendar-blocked across the team.
- **Foundational courses in month one.** Anthropic's courses on Claude and prompting are a strong foundation — well-structured, free, and effective at building shared vocabulary quickly. Pair them with one course from a different provider (DeepLearning.AI, OpenAI's resources, Maven cohorts) for a second perspective. Paid time, completed in the first 30 days, no exceptions.
- **Specialization in month two.** Each team member picks a deeper track aligned with their role and their growth direction. They go through the course on company time and present what they learned to the team.
- **Production tooling deep-dive in month three.** Cursor, Claude Code, MCP, agent frameworks. By the end of month three, every team member should be using these tools on real work, not just in tutorials.
- **Pairing as a default.** Whenever someone is doing something they haven't done before with AI, they pair. This single practice doubles the speed of fluency development across a team.

The leader's role in all of this is not to be the smartest person in every session — it is to be the person who shows up, sets the standard, builds in the open, and refuses to let learning be deprioritized. The team will follow the energy the leader brings to it. If the leader treats learning as central, the team will. If the leader treats it as optional, the team will absorb that signal within a week and behave accordingly.

The 90 days are short. Used well, they produce a team that ships AI-enhanced product confidently for years. Used poorly, they produce another company that "tried AI" and concluded it wasn't ready.
