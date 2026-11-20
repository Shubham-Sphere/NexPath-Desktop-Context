# NexPath --- Product & Communication Context

> Purpose: This document is a portable context file for continuing
> NexPath-related work in another AI assistant or workspace.
>
> Scope: It contains product information, positioning, feature
> explanations, communication preferences, and outreach guidance only.
> It intentionally excludes personal user data, third-party identities,
> private conversations, and individual outreach histories.

## 1. Product identity

-   **Company / organization:** ParseOS
-   **Product:** NexPath
-   **Category:** AI developer tool for improving the reliability and
    quality of AI-assisted coding workflows.
-   **Core idea:** NexPath works alongside AI coding agents. It helps
    developers notice missing scope, requirements, verification, safety,
    rollback, and maintenance checks before AI-generated work is treated
    as ready to ship.
-   **Positioning:** NexPath is a workflow quality / behaviour-guidance
    layer, not another coding agent and not a replacement for the
    developer's judgement.
-   **Tagline used in the repository:** "Build Fast. Ship with
    Confidence."
-   **Main product page:** https://parseos.tech/nexpath/
-   **GitHub repository:** https://github.com/hi0001234d/nexpath
-   **Repository README:**
    https://github.com/hi0001234d/nexpath/blob/main/README.md
-   **Waitlist:** https://getlaunchlist.com/pages/nexpath
-   **Community invite used in outreach:** https://discord.gg/VRtwtZbdr

## 2. The problem NexPath addresses

AI coding agents make it easier to generate and change code quickly. But
speed can hide important gaps:

-   A task may be implemented without all requirements being covered.
-   A generated change may introduce bugs or regressions.
-   Testing, acceptance criteria, security, rollback, and verification
    checks can be missed.
-   A codebase can become harder to maintain after repeated AI-generated
    changes.
-   Developers may spend significant time manually reviewing decisions
    and reconstructing context.
-   Prompts may omit constraints, expected behaviour, or evidence needed
    to confirm completion.

NexPath aims to surface the checks relevant to the current task while
the work context is still fresh. It does **not** promise bug-free code
or replace developer review. It helps make review and judgement more
structured and less likely to skip important checks.

## 3. How the core product works

The repository describes NexPath's Prompt Quality Layer as a four-step
workflow:

1.  **Understand** --- Reviews the prompt, development stage, and
    relevant workflow signals while preserving the complete original
    request.
2.  **Structure** --- Builds an editable prompt with relevant sections
    such as scope, constraints, acceptance expectations, verification,
    or missing-practice guidance.
3.  **Safeguard** --- For higher-risk work, can add confirmation,
    safety, rollback, or evidence requirements. Complex work can receive
    a sequence-aware breakdown.
4.  **Review** --- The developer inspects and edits the enhanced prompt
    before sending it, or chooses to return to the original prompt. The
    developer retains the final decision.

A simple explanation:

> You continue coding with the AI agent you already use. NexPath reviews
> the task prompt and helps bring missing scope, verification, safety,
> and maintenance checks into it before the agent works on it.

### Workflow in brief

1.  Build with your AI coding agent.
2.  Review the task with NexPath's prompt-quality layer.
3.  Inspect or edit the enhanced prompt.
4.  Send the reviewed prompt to the coding agent, or use the original
    prompt.

NexPath is intended to fit into an existing development workflow rather
than make developers move their coding work into a separate environment.

## 4. Core capabilities described in the repository

### Prompt Enhancement (PE)

Prompt Enhancement is the first practical feature in NexPath's broader
behaviour-guidance vision. It helps users avoid manually writing every
development detail into each prompt while preserving their original
intent.

It can suggest relevant missing practices, verification steps, or
confirmation requirements when the task needs more rigour.

### Multi-Prompt Sequence (MPS)

For complex work, NexPath can help break a larger task into a current
task plus a compact, ordered sequence plan. This helps keep multi-step
work organised.

### Prompt Enhancement Feedback (PEF)

The README lists Prompt Enhancement Feedback as part of the core feature
set. Avoid inventing detailed behaviour beyond the current product
documentation when explaining it.

### Scope and acceptance expectations

NexPath can help make the task's scope, constraints, expected behaviour,
affected areas, and acceptance expectations more visible.

### Verification and testing guidance

Depending on the task, NexPath can surface missing test expectations,
regression checks, reproduction evidence, acceptance criteria, or other
verification requirements.

### Safety and rollback guidance

For sensitive or higher-risk changes, NexPath can add explicit
confirmation, backup, rollback, or safety requirements. These should be
proportionate to the complexity and risk of the task.

### Developer control

The original request remains visible. The user can inspect and edit the
enhanced prompt, use it, or return to the original. NexPath does not
silently expand the developer's authority or treat an agent's response
as proof that work is complete.

## 5. Supported tools and agents --- distinguish versions

The public README currently lists the following support status for
NexPath CLI v0.1.58:

  Tool          README status
  ------------- ---------------------------------------
  Claude Code   Fully supported --- end-to-end tested
  Cursor        Fully supported --- end-to-end tested
  Windsurf      Fully supported --- end-to-end tested
  Replit        Fully supported --- end-to-end tested
  Lovable       Fully supported --- end-to-end tested
  Bolt.new      Fully supported --- end-to-end tested

The README describes NexPath CLI as being built for prompt capture
across AI coding agents.

Separate desktop-app context supplied by the product team for
outreach: - The desktop app is intended to let users work with and
switch between supported CLI-based coding agents from one place. -
Agents mentioned in the team's desktop-app outreach include Claude Code,
Codex, and Kilo Code. - Do not merge the desktop-app agent list with the
README's CLI v0.1.58 support table. They refer to different product
surfaces / contexts. - Do not claim support for an agent unless the
current release actually supports it. - Gemini was described by the team
as planned for a future update, not as currently available. Confirm
current status before making a fresh claim.

## 6. Desktop app --- team-provided product context

The team has described a NexPath desktop app built to deliver upcoming /
premium capabilities and make AI coding workflows easier to manage.

### Agent switching and workflow access

-   The app is intended to let users choose between supported CLI-based
    coding agents in one place.
-   Users can switch between agents depending on the task or workflow.
-   The team has mentioned Claude Code, Codex, and Kilo Code in
    desktop-app explanations. Confirm current compatibility before
    publishing definitive support claims.

### Data Privacy mode

Team-provided explanation for outreach: - Users can enable Data Privacy
mode when they need it. - The team's intended explanation is that
project data stays on the user's local system rather than being sent to
external AI model providers. - Describe the mode carefully and avoid
absolute claims such as "100% secure," "nothing ever leaves your
machine," or "complete privacy" unless verified against the current
technical implementation and documentation.

The public CLI README has a more specific privacy description: - NexPath
stores data locally under `~/.nexpath/`. - Only targeted LLM calls used
to classify or prepare relevant guidance leave the machine. - Automatic
secret redaction strips common API keys, bearer tokens, and PEM blocks
from prompts before storage. - Telemetry is off by default and remains
off unless the user enables it. - Local prompt capture and remote
telemetry are independent controls. - Users can disable capture, but the
README notes that doing so means NexPath will not work.

When explaining privacy, distinguish the desktop app's Data Privacy mode
as described by the team from the CLI README's documented storage and
network behaviour.

### Background Mode

Team-provided explanation: - Background Mode can suggest follow-up tasks
related to recently completed coding work. - Examples include creating
test scripts, setting up testing harnesses, and handling pending
verification tasks. - Users can choose which suggested tasks to run in
the background. - Do not imply that it silently or autonomously executes
arbitrary work without the user enabling or starting the relevant
action.

### Local LLM support

Team-provided explanation: - Users with capable hardware / a suitable
GPU can use local LLMs for simpler tasks. - This can reduce reliance on
paid hosted coding-agent or model subscriptions for every task and may
help manage costs. - Do not promise a specific amount of savings or
imply every computer can run local models effectively.

### Cost and subscription management

The desktop app has been described as helping users manage agent usage
and reduce overall costs by choosing appropriate agents and, where
supported hardware allows, using local models for simpler tasks. Phrase
this as a potential benefit, not a guaranteed saving.

## 7. Benchmark information in the public README

The README reports a comparison on 40 tasks from SWE-bench Verified
using Claude Code (`sonnet`), with and without NexPath-reviewed prompts.
It says the task, starting commit, container, model, time limit, and
tools were kept identical, with the prompt as the changed variable;
grading used the official SWE-bench harness.

Reported results:

  Measure                                   Claude Code   Claude Code + NexPath
  ------------------------------------- --------------- -----------------------
  Tasks solved                            27/40 (67.5%)           29/40 (72.5%)
  Issue's own tests pass                  27/40 (67.5%)           29/40 (72.5%)
  Ran project tests before submitting     38/40 (95.0%)           39/40 (97.5%)

Paired outcomes reported: - Solved by both: 27 - Solved only with
NexPath: 2 - Solved only without NexPath: 0 - Solved by neither: 11

When using these figures publicly: - Attribute them to the README's
40-task benchmark. - Keep the sample size and setup visible. - Do not
generalise the result into a universal performance guarantee. - Link the
README / full benchmark report for methodology and raw files.

## 8. Technical and installation details in the public README

The README currently describes NexPath CLI installation as:

``` bash
npm install -g nexpath-cli
nexpath install
nexpath --version
```

-   Package name: `nexpath-cli`
-   Commands installed: `nexpath` and `nexpath-serve`
-   Requirement: Node.js 18 or later
-   During installation, users choose how NexPath should run: with their
    own OpenAI API key or a NexPath token from a free account.
-   If both credentials are configured, the README says the OpenAI key
    is used.
-   During install, users choose a project role so NexPath can tailor
    guidance to their work.
-   The README lists PE, MPS, and PEF as core features.

These are CLI instructions, not necessarily desktop-app installation
instructions. For desktop app installation, direct users to the current
product page and follow the instructions shown there.

## 9. Open-source and premium positioning

Team-provided explanation: - The core NexPath project is open-source and
its repository is public. - The desktop app was built for upcoming
premium features that extend the existing functionality. - The public
repository README lists the Apache License 2.0.

A concise explanation for a developer: \> The core project is
open-source, and you can explore the code on GitHub. We've also built a
desktop app for upcoming premium features that extend the existing
functionality.

Do not imply that every premium desktop feature is already part of the
open-source repository. Clarify the scope if someone asks which exact
components are open-source.

## 10. Product links

  Purpose                      Link
  ---------------------------- -----------------------------------------------------------
  Main NexPath page            https://parseos.tech/nexpath/
  GitHub repository            https://github.com/hi0001234d/nexpath
  README                       https://github.com/hi0001234d/nexpath/blob/main/README.md
  Upcoming-features waitlist   https://getlaunchlist.com/pages/nexpath
  NexPath Discord community    https://discord.gg/VRtwtZbdr

The desktop app was described as ready for selected users to try while
the team was fixing minor issues and polishing the experience before a
fuller release. Treat release status, pricing, waitlist terms, and
feature availability as time-sensitive; verify before repeating them.

## 11. Communication style and outreach principles

The team's communication preferences:

-   Keep conversations healthy, natural, and respectful.
-   Never push NexPath aggressively.
-   First understand the other person's interests, work, and needs.
-   Keep messages short and human.
-   Do not copy the other person's exact writing style.
-   Do not use emojis in every message. Use them only when they
    genuinely fit.
-   Avoid repeatedly adding "haha".
-   Avoid generic sales language, exaggerated claims, or long feature
    dumps.
-   Do not make every conversation about NexPath. Build a genuine
    connection first.
-   Do not assume someone needs the product just because they are in a
    coding community.
-   Do not over-explain. Give one useful point at a time and let the
    conversation develop.
-   Avoid phrases the team has explicitly disliked, such as "feel free"
    and "get a chance," when a simpler alternative works.
-   Avoid repeatedly asking "Did you get a chance to...?" Prefer direct,
    natural questions such as "Did you download and try the desktop app?
    How did you find it?"

### Preferred tone

Casual, friendly, direct English. "Bro" can be used when it fits the
existing relationship, but should not be forced into every message.

### A good outreach sequence

1.  Start with a genuine question about what the person is building or
    working on.
2.  Briefly introduce that you work with a startup building AI developer
    tools.
3.  Mention one relevant NexPath benefit only if it connects to their
    workflow.
4.  Ask whether they would like to hear more before sending a link.
5.  If they show interest, explain the relevant feature in a separate
    short message.
6.  Share the product page / download instructions.
7.  Ask them to try the app during their normal coding workflow.
8.  Ask for practical feedback, especially if they notice a problem or
    confusing behaviour.
9.  Keep the relationship going even if they do not use the product
    immediately.

### Writing rules for replies

-   When asked to draft a reply to a screenshot or pasted conversation,
    read the whole context before writing.
-   Reply to what the other person actually said; do not send a generic
    pitch.
-   Do not repeat the person's message back to them.
-   Do not invent facts, technical details, availability, partnerships,
    or commitments.
-   If the user asks for a shorter version, shorten it rather than
    adding explanations.
-   If the user asks for multiple separate messages, keep them separate.
-   For a practical message they can copy and send, provide the complete
    draft in a chat-message writing block.
-   If the user explains in Gujarati transliteration, briefly explain
    the intent in Gujarati transliteration if useful, then write the
    sendable message in English.

## 12. Short message examples

These are reusable patterns, not mandatory scripts. Adapt them to the
recipient and context.

### Starting a conversation

> Hey! Saw your intro in the server. Are you currently working on any
> coding projects?

### Briefly introducing NexPath

> I'm working with a startup building an AI developer tool. We're trying
> to make AI-assisted coding workflows more reliable.

### Checking interest before sharing the desktop app

> We've also built a desktop app for AI coding workflows. It might be
> useful for your setup. Would you like a quick overview?

### Explaining CLI-agent switching

> The desktop app lets you use and switch between supported CLI-based
> coding agents in one place, depending on what you're working on.

### Explaining Data Privacy mode

> It also has a Data Privacy mode that you can enable when needed. It's
> designed to keep your project data on your local system rather than
> sending it to external AI models.

Use only if this description matches the current implementation.

### Explaining Background Mode

> Background Mode can suggest follow-up tasks based on your recent
> coding work, such as test scripts or verification checks. You can
> choose which tasks to run.

### Explaining local LLMs

> If your system has capable hardware, you can run local LLMs for
> simpler tasks instead of relying on paid models for everything.

### Sharing the product page

> Here's our website for a quick look: https://parseos.tech/nexpath/

### Clarifying desktop app vs browser extension

> Just to clarify, you need to download the desktop app from the
> website, not use the Chrome extension. We want you to try the desktop
> version.

### Asking for feedback after trying it

> Did you download and try the desktop app? How did you find it?

### Inviting someone to report issues

> Whenever you're coding or working on a project, you can try it out. If
> you run into any issues, let me know.

### Inviting someone to the community

> We also have a Discord community where our team and other developers
> connect and discuss ideas: https://discord.gg/VRtwtZbdr

### Explaining the open-source core and premium desktop app

> The core project is open-source, and you can explore the code on
> GitHub. We've built the desktop app for upcoming premium features that
> extend the existing functionality.

## 13. Accuracy guardrails

Before explaining or promoting a feature, check which product surface it
belongs to:

-   **NexPath CLI / core repository:** Use the public README for
    documented behaviour, supported tools, installation, privacy, and
    licensing.
-   **Desktop app:** Use the team's current desktop-app documentation or
    confirmed release notes. Do not assume every CLI feature and desktop
    feature behaves identically.
-   **Planned features:** Clearly label as planned or upcoming. Do not
    describe them as available.
-   **Premium features:** Do not imply they are all open-source.
-   **Privacy:** Avoid absolute security guarantees. Explain only the
    documented local-storage, targeted model-call, redaction, telemetry,
    or desktop privacy-mode behaviour that applies.
-   **Cost savings:** Say "can help reduce reliance on paid models"
    rather than promising a fixed saving.
-   **Background Mode:** Make user control clear; do not imply
    unapproved autonomous execution.
-   **Benchmarks:** State the test setup and sample size; do not
    generalise beyond the reported evaluation.
-   **Current status:** Release dates, pricing, supported-agent
    versions, waitlist benefits, and availability can change. Verify
    before making current claims.

## 14. Source notes

This context is based on: - The team's communication-guidance note. -
The team's feature-introduction note. - The team's waitlist link. - The
public NexPath GitHub README at
https://github.com/hi0001234d/nexpath/blob/main/README.md - Product and
desktop-app details explicitly supplied by the team in the project
context.

Where the public README and team-provided desktop-app descriptions refer
to different product surfaces, this document keeps them separate rather
than treating them as interchangeable.
