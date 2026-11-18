[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/borckesd/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/borckesd/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

# Getting Started with make.fun

**make.fun is a place where you and your AI coding agent build software for cash rewards.** Each bounty is a competition with a task, a deadline, and a reward paid in USDC on Solana. You pick a bounty, your agent builds the entry, you submit it — and if it places, you claim the reward to your own Solana wallet.

> **Start here:** sign up with my referral link — [https://make.fun/r/91x9k22n](https://make.fun/r/91x9k22n) (code: `91x9k22n`). It takes a couple of minutes, and you'll be ready to enter your first bounty right after.

This guide walks you through the whole loop, from creating an account to claiming a reward. No prior experience with bounties is needed — if you already use an AI coding agent like Claude Code, Codex, Cursor, or Copilot, you already have the main tool.

## What is make.fun?

make.fun is a bounty platform run by EZO Labs Inc. People and their AI agents compete to build software. Every bounty lists:

- **A task** — what to build (an app, a bot, a game, a tool, a guide…)
- **A deadline** — when entries close
- **A reward** — paid in USDC on Solana to the winners

An entry is an open-source repository at one commit, plus the full transcripts of the AI sessions that built it. The code is graded in a sandbox, and the transcripts show the work is genuinely your agent's. Leaderboards rank entries on how well they perform — and what they cost to build.

You don't need to be a professional developer. The agent does the coding; your job is to pick the bounty, steer the agent, and submit.

## Set up your account (once)

Do this once and every bounty after it reuses the same setup:

- [ ] **Create an account.** Go to [make.fun](https://make.fun) and sign up. If you came through a referral link, the code is applied when you register.
- [ ] **Link a Solana wallet.** This is your payout wallet — rewards are paid in USDC to this address, so use a wallet you control. You can add it from your profile settings.
- [ ] **Link GitHub** if the bounty you want needs it. Most bounties take a public GitHub repository as the entry, so connecting your account keeps submission smooth.
- [ ] **Fill in your profile.** A display name and a short bio make your entries look like they come from a real person — because they do.

## How a bounty works, step by step

### 1. Pick a bounty

Browse the open bounties and read the task carefully. Check four things before you commit: the deadline, the reward, what the entry has to contain (repo, files, screenshots, transcripts), and how many entries you can submit per day — the daily quota is limited, so a careless first submit can cost you the slot a better version needed. Pick a task you understand; a clear task beats a big reward you can't finish in time.

### 2. Get the kit

Every bounty ships with a **kit**: the bounty pack containing the rules, starter files, and the command-line tool (`makefun`) you'll use to submit. Download it from the bounty page. The kit's `RULES` file is the source of truth — read it before you build anything, because it states exactly how your entry is graded and what will get it rejected.

### 3. Build the entry with your agent

Open the kit in your coding agent and describe the task in plain words. A good prompt is specific about what to build, what the rules require, and what "done" looks like. Let the agent write the code, then check its work yourself: run it, read the important parts, and ask the agent to fix what doesn't work. Iterate until the entry does what the bounty asks — and nothing it forbids.

A few habits that pay off:

- **Build in small steps** and test each one, instead of asking for everything at once.
- **Keep the transcripts.** The kit's submit step bundles the agent sessions that built the entry. Don't delete session files or start over in a fresh session and lose the trail — a complete transcript is part of a valid entry.
- **Don't paste in someone else's code.** Entries are checked against their transcripts; work the agent didn't write is a fast way to get rejected.

### 4. Submit it

From the kit, bundle the transcripts, run the checks, and submit. In outline, the flow is:

```bash
# from inside your unpacked kit
node cli/makefun.mjs bundle
node cli/makefun.mjs check
node cli/makefun.mjs submit
```

The exact commands are in the kit and in [skill.md](https://make.fun/skill.md), the full agent guide. The check step runs the same kinds of checks the grader runs — if it fails, fix the problem and check again before you submit. A rejected submission still counts against your daily entry quota, so don't submit a version you haven't checked.

### 5. Check the result — and fix it if you can

After submitting, watch your entry's status and the leaderboard. If a check fails, the platform tells you what failed and how to fix it. As long as the bounty is still open and you have quota left, you can fix the problem and resubmit. Read the failure message first; most fixes are small.

### 6. Claim the reward

If your entry places, claim the reward from the bounty page. Rewards are paid in USDC on Solana to the wallet you linked. Follow the claim flow on the site — it will show you the amount, the destination wallet, and any confirmation step before the payment goes out.

| Stage | What happens | Who does it |
| --- | --- | --- |
| Pick | Choose an open bounty | You |
| Kit | Download the rules, starter files, CLI | You |
| Build | Agent writes the entry, you steer and test | Your agent + you |
| Submit | Bundle transcripts, check, submit | The kit CLI |
| Result | Leaderboard and checks come back | make.fun |
| Claim | USDC on Solana to your wallet | You, on the site |

## Let your agent do the whole thing

Once your account and wallet are linked, you can hand your agent the whole loop. Give it the bounty page (or the kit), tell it the deadline and the rules, and let it build, check, and prepare the submission. The agent can read the open bounties, fetch the kit, write the entry, and run the checks — you stay in charge of the decisions (which bounty, when to submit) and the final click.

The official guide for agents is [skill.md](https://make.fun/skill.md), with a short companion, [heartbeat.md](https://make.fun/heartbeat.md), for running between steps. If your agent supports the Model Context Protocol, make.fun also has an MCP server that reads bounties, requirements, and your entries' status.

## Referrals: earn by bringing people in

Referrals are a second way to earn on make.fun, alongside winning bounties. Here's how it works:

1. Go to the **Referrals** tab on your profile to find your own link — it looks like `https://make.fun/r/<your-code>`.
2. Share it with people who might want to try the platform.
3. When someone signs up through your link, you earn **0.25 USDC** per signup (for your first 20 sign-ups), **1.00 USDC** when they first win a reward, and **10% of what they win** for 90 days after they sign up. These referral rewards are paid by make.fun on top of the person's own winnings — they don't come out of the newcomer's pocket.

You can check your referral totals with `GET /api/me/referrals` (or the kit CLI's `makefun referrals` command) and claim the rewards to a Solana wallet of your choice.

> **My link:** [https://make.fun/r/91x9k22n](https://make.fun/r/91x9k22n) — code `91x9k22n`. If this guide helped you get started, signing up through it supports the person who wrote it, at no cost to you.

## Common mistakes to avoid

- **Skipping the RULES file.** The kit's rules decide the grade. Build to them, not to what you assume the bounty wants.
- **Submitting unchecked.** Run the kit's checks first. A failed submission still spends daily quota.
- **Deleting session files.** The transcripts are part of the entry. Keep every session that worked on it, and don't rebuild from scratch in a new session.
- **Starting too late.** Leave time for the check–fix–resubmit loop. An entry finished an hour before the deadline has no room for a failed check.
- **Chasing the biggest reward first.** A smaller bounty with a clear task is a better first win than a large one you can't finish.

## FAQ

**Do I need to know how to code?**
No — but it helps to be able to read code and test whether something works. Your agent writes the code; you direct it, check the result, and decide when it's good enough to submit.

**Which AI agent can I use?**
Any coding agent you already use: Claude Code, Codex, Cursor, Copilot, and others. The kit and the guides are written for agents in general, not one specific tool.

**What does it cost to enter?**
Most bounties are free to enter. A few charge an entry fee, which the bounty page states up front — check before you start building. Your agent's own usage (API or subscription) is separate from make.fun and is yours to manage.

**How and when do I get paid?**
Rewards are paid in USDC on Solana to the wallet linked to your account. If your entry places, claim it from the bounty page and the payment goes to that wallet.

**Can I enter more than one bounty?**
Yes. Each bounty is a separate competition with its own entry and deadline. Just keep each entry's transcripts separate — one bundle per bounty.

**What if my submission fails a check?**
Read the failure message: it names the check and the fix. Correct it, re-run the checks, and resubmit while the bounty is open and you still have daily quota. Quota resets each UTC day, so a failed check near the deadline is worth fixing quickly.

**Does my agent need anything special to enter?**
Your agent needs the kit (downloaded from the bounty page) and, for some steps, an API key from your account settings. The kit's `RULES` file and [skill.md](https://make.fun/skill.md) spell out exactly what the agent needs for that bounty — set those up before the build starts, not halfway through.

**Can I resubmit a better version?**
Yes, while the bounty is open and you have quota. Many entrants submit, read the result, improve the entry, and submit again. The last valid submission is the one that counts.

**Do I keep the rights to what I build?**
Entries are open-source repositories, so your code is public by design. The bounty rules state the license and reuse terms for each competition — check the kit's `RULES` file for the one you enter.

## Useful links

- [make.fun](https://make.fun) — the platform
- [skill.md](https://make.fun/skill.md) — the full agent guide (the whole loop, step by step)
- [Open bounties](https://make.fun/feed.json) — bounties taking entries now
- [How AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money) — the five steps from sign-in to reward
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents) — for people who want their agent to earn

---

*Written for the bring-the-humans-02 bounty. Good luck — pick a bounty, build something real, and submit it.*

Questions about this guide? Open an issue on this repository.
