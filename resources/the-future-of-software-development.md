# The Future of Software Development

*Source: Colin's presentation, `The Future of Software Development​.docx` (SharePoint, HgCapitalJumpStartProgramme site), converted to Markdown. This document explores how the software development industry will likely change as the ever-growing capabilities of agentic AI mean that more software will be written by AI than humans.*

## The growing role of AI in software development

### From Assistance to Autonomy (2022–2025)

The use of LLMs and Agentic AI systems to write code has unfolded rapidly over a four-year period, each year marking a distinct shift in how developers interact with machines.

In 2022, the release of ChatGPT and GitHub Copilot introduced AI into the developer workflow in a meaningful way. These tools operated primarily at the level of line-by-line or function-level assistance, offering autocomplete-style support within familiar environments. Developers remained firmly in control, and while productivity improved, the overall model of software development remained unchanged.

By 2023, the introduction of GPT-4 marked a clear step change in capability. Interaction models began to shift from passive assistance to more active collaboration. Developers increasingly worked through prompting, asking the model to generate, modify, or explain code, creating a more conversational and intent-driven workflow. This represented the first real break from traditional tooling paradigms.

In 2024, this trend accelerated significantly. Advances in model performance, context window size, and speed, alongside the emergence of tools such as Cursor, Bolt, and others, enabled an AI-first approach to development. The focus of software developers moved further away from writing code directly and toward interacting with systems that could generate and reason over entire codebases. Techniques such as Retrieval Augmented Generation (RAG) allowed these systems to operate over larger and more complex contexts, shifting AI from a supporting role to a central one in the delivery process.

By 2025, a new mode of working had emerged. Developers began to adopt structured, iterative workflows — plan, generate, test, refine — underpinned by increasingly sophisticated "agentic loops." These systems combine reasoning models with tools such as compilers and test suites, enabling them to operate autonomously toward defined goals. The role of the developer started to shift fundamentally: from directly producing code to designing the environments, feedback loops, and constraints within which AI systems operate.

### The 2025 Inflection Point

Toward the end of 2025, the industry reached what many describe as an inflection point. This was not triggered by a single model release or benchmark result, but rather a collective realisation: software development had fundamentally changed. For the first time, autonomous, agent-driven workflows proved capable of operating at repository scale, delivering substantial results with minimal human intervention. The act of software development began to shift from writing code to directing systems to produce it.

At the same time, the economics of software were upended. The cost of generating code, historically a significant constraint, often measured at tens of dollars per line, collapsed toward zero (under the right conditions). Tasks that once required teams and months or years of effort could now be executed in days.

However, this shift came with an important caveat. While the cost of producing code has diminished dramatically, the challenge of building the *right* thing remains. The most successful examples of AI-driven development rely on well-defined problems, strong validation mechanisms, and carefully constructed feedback loops. In less idealised environments, these constraints still limit outcomes.

Even so, the implications are profound. The ability to rapidly generate and iterate on software, experimenting with designs, refactoring systems, or exploring alternative architectures, has fundamentally expanded what is possible within a given timeframe.

### A Change in Foundations

Taken together, these developments point to a deeper conclusion: the processes and practices that have defined software engineering were built around human constraints — limitations in cognition, communication, and production speed. Those constraints are no longer the primary factor.

As a result, the discipline is entering a period of structural change. The question is no longer how to make developers more efficient within existing models, but how to redesign those models around the strengths and weaknesses of AI.

## Principles of Agentic AI for Software Development

### Shaping Systems over Writing Code

The shift from writing code to shaping systems is driven by the rapid collapse in the cost of code production and the rise of agentic AI workflows. Modern AI systems can autonomously plan, generate, test, and refine code when given the right tools and feedback loops, moving software development from a manual activity to a predominantly automated one (again, given the right conditions). This fundamentally changes where value is created. Writing code is no longer the limiting factor; instead, the challenge lies in defining the right problems, setting appropriate constraints, and creating environments in which AI can succeed. As a result, engineering effort naturally shifts upward, from implementation detail to system-level thinking, where humans design the architecture, goals, and feedback mechanisms that guide AI-driven development.

The impact of this shift is a redefinition of the day-to-day role of the engineer. Less time will be spent writing and reviewing code line-by-line, and more time will be spent designing system behaviour, building effective harnesses (tests, tooling, environments), and iterating on outcomes. Engineers will operate at a higher level of abstraction, focusing on intent, architecture, and validation rather than syntax. This increases individual leverage significantly but also places greater emphasis on skills such as systems thinking, problem framing, and judgment. In practice, successful teams will be those that can create the conditions for AI to reliably produce high-quality outputs, rather than those that are simply efficient at manual code production.

### Product Thinking Over Delivery Thinking

The shift from delivery thinking to product thinking is driven by the removal of delivery as the primary constraint. Historically, software engineering has been dominated by questions of efficiency — how to deliver features faster, cheaper, and with fewer resources — because writing code was slow and expensive. AI has dramatically accelerated delivery to the point where, in many instances, generating code is no longer the bottleneck. When implementation speeds are rapidly increasing, optimising the delivery pipeline yields diminishing returns. Instead, the critical question becomes whether the right thing is being built at all, shifting focus upstream to problem selection, user needs, and value creation.

The impact is a fundamental change in how engineers spend their time and how teams prioritise work. There will be less emphasis on completing tickets and more emphasis on understanding users, iterating on ideas, and validating whether solutions solve real problems. Skills such as communication, product intuition, and creativity become more important than execution efficiency. Engineers are expected to engage more directly with product decisions, blurring the boundary between engineering and product roles, and leading to a more outcome-oriented culture.

### Validating Outcomes Over Reviewing Code

The move from code review to outcome validation is driven by the changing role of code itself. Code review has historically served two purposes: identifying defects in the short term and maintaining long-term code quality for human maintainers. However, as AI becomes increasingly effective at identifying bugs and generating consistent code, the need for humans to inspect code line-by-line diminishes. At the same time, the volume of generated code increases significantly, making manual review less scalable and less valuable relative to automated approaches.

The impact is a shift toward automated validation as the primary quality control mechanism. Teams will invest more heavily in test automation, simulation environments, and observability to ensure systems behave correctly under real conditions. Code review will not disappear but will evolve toward higher-level concerns such as architecture and system design. Engineers will focus less on how the code is written and more on whether it achieves the desired outcomes, leading to faster iteration cycles and more robust, behaviour-driven development practices.

### Fast Feedback Over Upfront Certainty

The shift toward fast feedback over upfront certainty is driven by the reduced cost of iteration. Traditional software development has emphasised detailed upfront design and specification because changes were expensive and slow. With AI dramatically lowering the cost of generating and modifying code, this assumption no longer holds.

The impact is a move toward highly iterative workflows, where teams generate solutions quickly, test them, and refine them based on feedback. Rather than trying to get things right the first time, teams will explore multiple approaches in parallel and converge on the best solution. This leads to shorter development cycles, increased experimentation, and a greater tolerance for ambiguity early in the process. The emphasis shifts from planning accuracy to learning speed.

### Breadth of Perspective Over Narrow Specialism

The move from narrow specialisation to breadth of perspective is driven by the increasing accessibility of software development through AI. Traditionally, teams have relied on deep specialists — DevOps engineers, testers, business analysts — because of the complexity and effort required to work in different areas of the stack. AI reduces these barriers by enabling individuals to engage across domains more effectively, lowering the cost of switching contexts and acquiring capabilities.

The impact is a blurring of traditional role boundaries within teams. While deep expertise will still exist, more team members will be able to contribute across a wider range of activities, leading to more fluid and collaborative ways of working. Teams will benefit from diverse perspectives applied more broadly, rather than being constrained by rigid role definitions. This increases adaptability and reduces handoffs, but also requires individuals to develop a broader understanding of the system as a whole.

### Empowered Individuals Over Bloated Teams

The shift toward smaller, more empowered teams is driven by the disproportionate increase in individual productivity enabled by AI. Team size has historically been a balance between individual output and communication overhead, leading to conventions like "two-pizza teams." AI significantly increases the output of each individual without reducing the cost of coordination, breaking this balance. As a result, larger teams become inefficient relative to smaller, highly capable ones.

The impact is a reduction in team size and a corresponding increase in individual responsibility and autonomy. Teams may shrink from 6–10 people down to 2–4, enabling faster decision-making, fewer meetings, and reduced coordination overhead. Individuals will take on broader responsibilities and have greater influence over outcomes. This creates more agile and responsive teams but also places higher expectations on each team member's capability and judgment.

### Contextual Judgement Over Standardised Process

The move from standardised processes to contextual judgement is driven by the breakdown of the cost assumptions that underpin traditional software processes. Standardisation has historically been used to manage risk in environments where change is expensive and difficult to reverse. With AI making changes cheaper and more transparent, a single, rigid process becomes less effective. Instead, the appropriate level of rigor depends on the specific risk profile of the system or change being made.

The impact is a more flexible, risk-based approach to software development. Teams will tailor their processes based on factors such as user impact and failure cost, applying lightweight approaches to low-risk work and more rigorous validation to high-risk systems. This reduces unnecessary overhead and allows teams to move faster where appropriate but requires stronger judgment and decision-making capabilities. Process becomes a tool to be adapted rather than a rule to be followed.

### Continuous Transformation Over One-Time Change

The shift toward continuous transformation is driven by the pace and persistence of change in AI capabilities. Unlike previous technological shifts, which could often be addressed through discrete transformations, AI is evolving rapidly and continuously. Many organisations are still in early phases of adoption — introducing tools and adapting workflows — while the broader reshaping is still ahead. This creates a moving target, where any static transformation effort quickly becomes outdated.

The impact is that organisations must adopt an ongoing mindset of change rather than treating transformation as a one-off initiative. This includes investing in foundational capabilities such as test coverage and environments, allowing time for individuals to develop new skills, and continuously evolving organisational structures and practices. Success depends on the ability to adapt repeatedly and incrementally, rather than executing a single large-scale change programme.

## What the future holds

### For the Individuals

For software engineers the most prominent shift in their role will be the move from writing code to shaping systems and outcomes. This is not to say that they will no longer write any code; there are certain situations where a more manual approach will still be necessary, but over time, these instances will continue to diminish. As a result, engineers will spend less time on the implementation itself, and more time on framing the problem itself so that AI can proceed with the implementation. Furthermore, they will have less direct ownership of the code itself — less line-by-line engagement.

This represents a shift to a higher level of abstraction, something we've seen in the past as we've moved from assembly language to C, or from C to Java. However, there is a notable difference in this case: the use of AI to generate code from natural language is not a deterministic process. It is a leaky abstraction, which needs to be handled with care.

Software engineers will still undertake 'engineering' in the future, but the focus of their efforts will change. Much of their engineering skills will be focussed on creating the environment that allows AI to be successful. We're already seeing new practices emerge that are directionally aligned, for example agentic loops, context engineering and harness engineering. As with everything, there will be a balance, and engineering practices and principles will still be applied to the code. However, engineering that 'unlocks' the full capability of agentic AI will have a strong multiplier effect.

Architectural thinking becomes a key skill; it is these more high-level qualities of a system that ensure it is a good fit for the business both new and in the future. System-level reasoning will become more important than implementation, and as a result, code-review will elevate from line-by-line inspection to validating that suitable patterns or system constraints are being followed.

A significant challenge we will face in the future is the creation of effective learning pathways. We will need to identify novel ways in which junior engineers can start learning the skills that have traditionally been acquired through many years of hands-on coding. There is also a related risk of shallow understanding through over-reliance on AI. Learning through doing is still essential.

We will also see a convergence of roles and the boundaries blur. Traditional software development teams are typically composed of ~50% software engineers, with the other half being a mix of specialist skills, including test, business analysis, UX design — with the exact mix depending on the system being developed and organisational culture. Through the use of AI, it is much easier for anyone within the team to have a direct impact on the code, resolving issues, or experimenting with new features. It is unlikely we will see a complete convergence to a homogenous 'software developer', however, in future, the roles will be more aligned to an individual's mindset than a concrete list of skills.

At a deeper level software engineers will face a change of identity and motivation — moving from being a "builder" to an orchestrator, designer and problem solver. This will naturally cause tension, with some expressing a loss of enjoyment due to this shift. However, a perceived loss in some areas is compensated by new opportunities: the ability to build things that would previously have been too costly or simply impractical for an individual contributor.

### For Teams

The software industry has settled on teams of 6–10, or a "two pizza team". With an agile methodology, this size of team is optimised for peer-to-peer communication, code review and governance, cohesion and trust, sub-system ownership and a number of other constraints. As AI increases individual output, these constraints still apply, but some are lessened while others heightened. Given the significant increase in the amount of code each individual can produce, teams will likely reduce in size. However, more fundamentally, the speed of code production will no longer be the limiting factor — instead decision bandwidth will become a key constraint. Teams will optimise for clarity of intent, not capacity.

Conversely, with AI reducing the on-boarding time for an engineer when tackling an unfamiliar system, we may see increased organisational fluidity. When tackling a hard or time-sensitive challenge, engineers may "swarm" together.

A key shift in team behaviour will be a move away from inspection, through code-review, to validation. We'll see a move towards testing, validation, and behavioural assurance. For many organisations this will be a challenge, where automation testing is often quite limited. However, validation will be more than just ensuring the system meets a set of functional and non-functional requirements. An important team responsibility will be maintaining a suitable architecture, one that is a good fit for the business both now and in the future. AI systems are currently quite weak when it comes to architectural decision making. While this will likely improve over time, a key challenge they will face is the lack of context — human architects spend as much time talking to the broader business as they do the engineering team.

With AI able to create code many orders of magnitude faster than humans, our current collaboration patterns will become a bottleneck. The current hand-off culture (tickets → dev → test) that still persists in many agile teams is simply too slow. We will likely see new patterns emerge, for example real-time co-creation and collaborative interactions with AI.

Another by-product of the speed of code creation is the ability to explore multiple solutions quickly. Currently teams are incentivised to commit to a specific approach (e.g. architecture, tech stack) early due to the cost of change. In the future, the cost of change is significantly reduced, allowing branched approaches rather than committing early. More fundamentally, experimentation will become a core behaviour of high-performing teams, with creativity and curiosity being key attributes.

The boundaries between developers, testers, designers and analysts will blur as these roles move closer together, with AI tools giving everyone the ability to meaningfully iterate on the product. However, diversity of thought will become more important, not less. There is a risk that over-reliance on homogeneous AI output will lead to products that lack differentiation.

### For Organisations

Organisations shouldn't expect to get an immediate productivity boost by adopting the latest-and-greatest AI tool. As described in the previous sections, there is a lot of change required to "unlock" the velocity-increasing potential of AI. However, as individuals and teams adapt, the overall velocity will increase, by multiples. The historical constraint, based on developer capacity, will become less crucial over time, with bottlenecks moving to clarity of requirements and decision making.

This transformation requires far more than just giving developers access to AI tools — it requires a fundamental re-think of the entire software development process. Current systems and processes are optimised for the strengths and weaknesses of humans. These need redesigning around the strengths and weaknesses of AI. Content needs to be AI-consumable as well as human-consumable, with documentation and data becoming first-class concerns. There will be a reduced need for handoffs and sequential phases, with a movement toward more fluid, adaptive operating models.

As the velocity increases, creating suitable guardrails will become a significant challenge for organisations. There will be a growing need to balance speed with responsibility, and automation with human oversight.
