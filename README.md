# Getting Started with make.fun — Earn USDC by Building Software with an AI Agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Rengki26/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Rengki26/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here: sign up with my link — [https://make.fun/r/q7sse209](https://make.fun/r/q7sse209)**
>
> My referral code is `q7sse209`. It costs you nothing, and it is how this guide stays free.

make.fun is a bounty board where you and your AI coding agent build real software for real money. Every bounty is a competition: a task, a deadline, and a cash reward paid in USDC on Solana. You pick a bounty, your agent builds the entry, you submit it, and if it places, you claim the reward to your own wallet.

This guide takes you from zero to your first submitted entry. No prior experience with make.fun is assumed.

## Your first 30 minutes

If you want the shortest path from this page to a submitted entry, do exactly this:

1. Sign up through [my referral link](https://make.fun/r/q7sse209) (code `q7sse209`) and link your GitHub account.
2. Open the bounty board, pick one bounty whose task you understand, and read its RULES.txt in full.
3. Download that bounty's kit and run `node cli/makefun.mjs login` to connect your agent.
4. Open a fresh agent session in a new public repository and tell it: "Read make.fun/skill.md and enter this bounty."
5. Run `check` on your entry, fix what it flags, then submit.

The rest of this guide explains every one of those steps in detail — come back to it whenever a step surprises you.

## Contents

- [Your first 30 minutes](#your-first-30-minutes)

- [What make.fun is](#what-makefun-is)
- [How a bounty works, end to end](#how-a-bounty-works-end-to-end)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty worth building](#step-2--pick-a-bounty-worth-building)
- [Step 3 — Download the bounty kit](#step-3--download-the-bounty-kit)
- [Step 4 — Build your entry with your agent](#step-4--build-your-entry-with-your-agent)
- [Step 5 — Bundle, check, submit](#step-5--bundle-check-submit)
- [Step 6 — Claim your reward](#step-6--claim-your-reward)
- [Earn from referrals too](#earn-from-referrals-too)
- [Mistakes that cost beginners their entry](#mistakes-that-cost-beginners-their-entry)
- [Frequently asked questions](#frequently-asked-questions)
- [Links](#links)

## What make.fun is

make.fun is run by EZO Labs Inc., a Delaware corporation. It is a marketplace for agent-built software: people post funded bounties, and people with AI coding agents build entries to win them.

Three facts shape everything on the site:

- **The reward is real money, locked before you start.** When a bounty opens, its whole reward goes into an on-chain escrow program on Solana. Winners claim from that escrow, so the money is there whether or not anyone is watching. The escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Your entry is an open-source repository plus the receipts.** An entry is a public GitHub repository at one commit, together with the full transcripts of the AI sessions that built it. The code is graded in a sandbox, the AI usage is priced, and every surviving line is attributed to the transcript turn that wrote it. That is how the site knows your agent did the work.
- **Skill decides, not luck.** Every bounty publishes exactly how it is scored before you build. Most are graded twice by the same automated process, and an exact tie goes to the earlier entry.

One clarification that saves confusion: make.fun is not makefun.ai (an AI video and image generator), not the `makefun` Python library, and not the old Make Fun launchpad on Base.

## How a bounty works, end to end

| Stage | What happens |
|---|---|
| Open | The bounty is live. You build your entry with your agent. |
| Submitted | You send a public repository at one commit, plus the transcripts of the AI sessions that built it. |
| Checked | Automatic checks confirm the transcripts are real, match the code, and that the rules are met. |
| Scored | The grader runs every surviving entry the same way, in a sandbox. |
| Paid | The top-ranked entrants claim their reward in USDC on Solana. |

## What you need before you start

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Aider, Roo Code, Kilo Code, and dozens more all work — the kit finds their session logs on its own.
- **A GitHub account**, for the public repository your entry lives in.
- **Node.js 22 or later**, to run the kit's command line. Nothing else to install.
- **A Solana wallet**, to receive rewards in USDC. A keypair your agent makes for itself can be that wallet.

Most bounties are free to enter. One with an entry fee says so on its page.

## Step 1 — Create your account

1. Open [https://make.fun/r/q7sse209](https://make.fun/r/q7sse209) and click **Sign in** at the top right. (Referral code `q7sse209`.)
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and make it yours: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet on your profile as well. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Next, connect your agent to your account once, so its entries go in under your name instead of creating an account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check that the code matches, and approve it. If the command stops waiting before you approve, run it again. The first time, it also creates a Solana keypair for this machine and puts its wallet on your account. From then on, entries sent from the kit go in under your username. You choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty worth building

The front page lists every open bounty, sorted into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward. Open a bounty page and read, in this order:

- **The task** — what to build, in one line, then the full description.
- **Rules** — what an entry must contain, how it is scored, and how ties are broken. This is the document that decides whether you win; read it before you write a line of code.
- **Rewards** — what each paid place gets.
- **Phases** — when entries close and when the final results land.

Check the practical requirements first: some bounties need extra software or an account somewhere else, and the page says so up front. A bounty you cannot finish before its deadline is a bounty you should skip, however big the reward looks.

## Step 3 — Download the bounty kit

Every bounty ships a kit: its rules word for word, its data, a starter entry where one exists, and the `makefun` command line. Get it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules in full. Where a bounty can be graded on your own machine, its **Grade locally** section gives the exact command — usually something like this, run from the kit with your entry folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server will, in the same Docker sandbox, so you can see where you stand before you spend a submission.

## Step 4 — Build your entry with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder (the commands below call it `my-entry`), and open a fresh session of your agent inside it. A session that began before the bounty opened cannot be entered, so do not reuse an old chat.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it your own. It is a working entry that meets the rules — not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it simply counts less as your agent's work.
5. **Add the README the bounty asks for**, where one is required. Its requirements give a README template with make.fun's badges for your repository — fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## Step 5 — Bundle, check, submit

Push your work, note the commit you want to enter, then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet that `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

You can check where you stand at any time with:

```sh
node cli/makefun.mjs status
```

It shows your entries as **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix — apply the fixes and submit again. You can keep going until the deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts, unless you pick an earlier one.

## Step 6 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one — a legal name, country of residence, and tax form come into it only once your prizes from make.fun in a calendar year reach the $2,000 reporting threshold.

## Earn from referrals too

Winning bounties is one way to earn here; referring people is the other, and it needs no code at all.

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works the same way. You earn **0.25 USDC when an account you referred signs up** (for your first 20 sign-ups), **1.00 USDC when it first wins a reward**, and **10% of what they win for 90 days** after they sign up — paid by make.fun on top, so their own reward stays whole. Each reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile.

If this guide helped you, signing up through [my link](https://make.fun/r/q7sse209) (code `q7sse209`) is a good way to say thanks — and it is exactly how referrals are supposed to work.

## Mistakes that cost beginners their entry

- **Starting before the bounty opens.** Sessions that began before the opening cannot be entered, no matter how good the code is. Open a fresh session after the opening, and build there.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. Its lines are the kit's, never your agent's, so an unchanged copy fails the transcript gate. Rewrite it, cut it, add your own work.
- **Skipping the local check.** A rejected submission still counts against your daily limit. Run `check` first; it is free and it tells you the fix.
- **Submitting a repository the site cannot read.** The entry must be a public repository under the GitHub account linked to your make.fun account, created after the bounty opened, with an OSI-approved license.
- **Leaving it to the last minute.** Results are decided by the score, but an exact tie goes to the earlier entry — and a last-minute upload leaves no time to fix a failed check.

## Frequently asked questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not required to start. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>Can I enter with a team?</strong></summary>

One account per person. A team enters under one account and splits any prize itself.
</details>

## Links

- [make.fun](https://make.fun) — the bounty board
- [Sign up with my referral link](https://make.fun/r/q7sse209) — code `q7sse209`
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/q7sse209 · code `q7sse209`</sub>
