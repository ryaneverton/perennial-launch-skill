# Perennial Launch Planner

A Claude skill that turns a book, product, business, community or campaign into a structured launch plan, then writes the prompts an AI agent can run to do the work.

It is built on the long-game ideas in *Perennial Seller* by Ryan Holiday: make the thing good, say what it is clearly, name your first buyers, own your list, win champions with gifts not asks, concentrate the launch, and keep going for years.

## What you get

1. **PLAN.md:** a verdict, a ten-point readiness scorecard, your position in one sentence, a first-100 buyer spec, an asset inventory, a day-by-day timeline with a go/no-go gate, a launch-window calendar, three ideas to test, a "not doing" list and a weekly scoreboard.
2. **AGENT_PROMPTS.md:** a master prompt plus one prompt per workstream (research, outreach drafts, content, launch calendar, weekly report) with the rules baked in: draft only, cite sources, no invented facts, nothing goes out without your approval.

See [examples/worked-example.md](examples/worked-example.md) for a full run on a fictional book.

## Install

**Claude Code:** copy this folder to `~/.claude/skills/perennial-launch-planner/` (so `SKILL.md` sits directly inside it).

**Claude (web or desktop):** add the contents of `SKILL.md` as a skill in your settings, or zip the folder and upload it where skills are managed.

## Use it

Say something like:

- "Use the perennial launch planner on my book. Here's the manuscript."
- "Help me launch my SaaS. It's built, I have 300 users and no marketing yet."
- "Make me a launch plan for my community and the prompts to give my agent."

Share files, links or a repo if you have them. It reads those first and asks only for what's missing.

## How it works

1. Looks at what you've shared, then asks up to eight questions in one go.
2. Scores your project against ten readiness checks and names what blocks you.
3. Picks a stage: fix, quiet build (30 days), launch window (7 to 14 days) or sustain.
4. Writes the plan and the agent prompts.
5. Gives you the top three moves for this week and one thing you're doing that's low leverage.

## Limits

- The ideas come from creative-work examples, so B2B, marketplaces and regulated products need adapting. The plan says where.
- It gives you defaults for gates and thresholds. Change them.
- It never promises results.
- Agent prompts draft only. You approve every send, post and payment.

## Credit

Ideas are paraphrased and adapted from *Perennial Seller* (Ryan Holiday, 2017) and related talks. This project is not affiliated with the author. Buy the book for the full argument.

## License

MIT
