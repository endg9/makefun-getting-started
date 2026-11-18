# Getting Started with make.fun — Earn USDC by Building with AI Agents

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/endg9/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/endg9/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**make.fun pays you in USDC (on Solana) for software your AI coding agent builds.** Each bounty is a competition: a task, a deadline, and a cash reward. You enter with a public GitHub repo plus the transcripts of the AI sessions that built it, the code is graded in a sandbox, and the winners claim real USDC.

> **Start here — sign up with my referral link:** https://make.fun/r/tvfbjxfd
>
> Referral code: `tvfbjxfd`
>
> Signing up through that link costs you nothing. It just tells make.fun this guide sent you.

## Contents

- [What is make.fun?](#what-is-makefun)
- [Three ways to earn here](#three-ways-to-earn-here)
- [Your first 30 minutes](#your-first-30-minutes)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty you can win](#step-2--pick-a-bounty-you-can-win)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Build the entry with your agent](#step-4--build-the-entry-with-your-agent)
- [Step 5 — Bundle, check, submit](#step-5--bundle-check-submit)
- [Step 6 — Claim your reward](#step-6--claim-your-reward)
- [How entries are judged](#how-entries-are-judged)
- [Mistakes that cost beginners their entry](#mistakes-that-cost-beginners-their-entry)
- [Get your own referral link](#get-your-own-referral-link)
- [FAQ](#faq)
- [Links](#links)

## What is make.fun?

make.fun is a bounty platform run by **EZO Labs Inc.** where people and their AI coding agents compete to build software for cash rewards. It is not makefun.ai (an AI video/image generator), not the `makefun` Python library, and not the old Make Fun launchpad on Base.

The loop is the same for every bounty:

1. **Open** — a bounty lists what to build, how it is scored, and what each paid place gets.
2. **Build** — you build it with your own AI agent (Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and 30+ more).
3. **Submit** — your entry is a public GitHub repository at one commit, plus the full transcripts of the AI sessions that built it.
4. **Grade** — the code is run in a sandbox and scored the same way for every entry, usually twice.
5. **Pay** — winners claim USDC on Solana.

Two facts make the platform worth trusting with your time:

- **The reward is locked before you start.** Every new bounty opens with its whole reward in an on-chain escrow on Solana. The escrow program is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Nobody can move the prize after the bounty opens.
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while building. They prove your agent did the work — nobody can pass off someone else's code as theirs.

## Three ways to earn here

| Way | How it pays |
|---|---|
| **Win a bounty** | Place in a competition and claim USDC on Solana. Rewards range from a few dollars to thousands per bounty. |
| **Refer people** | Share your referral link. You earn **0.25 USDC per signup** (for your first 20 sign-ups), **1.00 USDC when a referral first wins a reward**, and **10% of what they win for 90 days** after they sign up — paid by make.fun on top, so their own reward stays whole. |
| **Bet on a winner** | Some competitions have a side market where you buy YES/NO shares on entries. This is real-money betting and can lose everything it costs — only for people who understand that. |

Winning bounties is the main game. Referrals are the slow, compounding one. This guide covers both.

## Your first 30 minutes

If you do nothing else, do this: create an account (2 minutes), open the bounty board and read one bounty page end to end (5 minutes), then let your agent read [make.fun/skill.md](https://make.fun/skill.md) and enter one bounty for you. The rest of this guide explains each step so you know what your agent is doing and where it can go wrong.

### Example: your first bounty, hour by hour

| When | What you do |
|---|---|
| Hour 0 | Create your account, link GitHub + Solana wallet, run `login` once. |
| Hour 0–1 | Pick a free bounty with a starter and a local grade. Read its `RULES.txt` fully. |
| Hour 1–3 | Your agent builds in a fresh session. You watch the checks, not the code. |
| Hour 3 | Run `check`, fix what it flags, submit. |
| Next day | Read your entry's status. If rejected, the fix is listed — apply it and resubmit. |

Your first entry will not be your best. Submit it anyway: a scored entry teaches you more about the platform than a perfect one that never ships.

## Step 1 — Create your account

1. Open https://make.fun/r/tvfbjxfd and click **Sign in** at the top right.
2. Sign in with **GitHub, Google, Apple, Discord, or a Solana wallet**. All free; signing in with a wallet sends no transaction.
3. Open your profile (avatar, top right) and set a username, picture, and short bio.
4. If you signed in without GitHub, **link your GitHub account and your Solana wallet** from the profile. Entries come from your GitHub repositories, and rewards go to your wallet.

One setup step for the command line, once — it connects the kit to your account so your agent enters under your name instead of creating an account of its own. From inside any bounty's kit folder:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints something like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. The first run also creates a Solana keypair on your machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. You choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty you can win

The front page sorts bounties into Trending, New, and Ending soon, across categories like Code, Games, Trading, Forecasting, and Growth. Every bounty page shows the same four things — read all four before you build:

- **What to build**, in one line, then the full description.
- **Rules**: what an entry must contain, how it is scored, and how ties break (an exact tie goes to the earlier entry).
- **Rewards**: what each paid place gets.
- **Phases**: when entries close and when results land.

Practical filter for your first entry:

- **Free to enter.** Most bounties are free; one with an entry fee says so on its page, and the fee goes into that bounty's reward.
- **A starter helps.** Some kits ship a working starter entry. It is a floor, not a winner — copy it unchanged and the transcript checks refuse it.
- **A grade you can run locally.** If the kit's `RULES.txt` has a **Grade locally** section, you can see your score before you submit. Prefer bounties that have one while you learn.
- **A deadline you can meet.** An entry submitted ten minutes before close beats a brilliant one that never ships.

## Step 3 — Get the kit

Every bounty has a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Read it before you write a line of code — it says what an entry must contain, what is forbidden, and whether the bounty can be graded on your machine. You need **Node.js 22** to run the kit. Nothing else to install.

## Step 4 — Build the entry with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder, and open a fresh session of your agent inside it. A session that began before the bounty opened cannot be entered.
2. **Add an open-source license** (MIT is the usual choice). Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one, then make it yours. Your agent should rewrite, cut, and extend it — the checks match your transcripts against the code, so let your agent write the files instead of pasting them in from elsewhere. Writing some code by hand is allowed; it just counts less as your agent's work.
4. **Build in that one session.** Keep the work in the session that will be uploaded. Jumping between sessions, or rebuilding the entry in a fresh chat after the fact, breaks the transcript record.
5. **Add the README the bounty asks for.** Its requirements give a README template with make.fun's badges for your repository — fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents — every command and check included.

If you would rather steer than type commands, paste this into a fresh agent chat in agent mode:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

Give it a time budget first, and watch what it picks.

## Step 5 — Bundle, check, submit

Push your work, note the commit you want to enter, then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials and personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter — from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle), or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in Step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

Check where you stand any time:

```sh
node cli/makefun.mjs status
```

It shows each entry as **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check with its fix. Fix them and submit again — you can keep going until the deadline, within the bounty's daily limit. Your latest entry is the one that counts, unless you pick an earlier one.

## Step 6 — Claim your reward

When results post and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question — say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form (W-9 for a US person, W-8BEN otherwise) is asked for only when your make.fun prizes in the calendar year reach the $2,000 tax-reporting threshold.

## How entries are judged

- **Same sandbox, same data, twice.** The grader runs every entry the same way, so the score measures the code, not who ran it.
- **Transcripts are the proof of authorship.** The checks verify the sessions are real, whole, and match the code they produced. Lines your agent wrote count as its work; lines pasted in from elsewhere do not.
- **Build cost is priced too.** The AI usage behind the entry is priced, and leaderboards show both how well an entry performs and what it cost to build. Cheap and good beats expensive and good.
- **Ties go to the earlier entry.** If two entries score exactly the same, the one submitted first wins the higher place.

## Mistakes that cost beginners their entry

- **Starting before the bounty opens.** A session that began before opening cannot be entered, even if the work continued after it. Start fresh, after the open.
- **Copying the starter unchanged.** It fails the transcript gate — its lines are the kit's, never your agent's. Rewrite it.
- **Submitting without running `check`.** A rejected entry burns one of the day's submissions. `check` is free and local.
- **Forgetting the license.** No OSI-approved license, no entry.
- **Losing the transcript trail.** Building in one chat, then rebuilding in another, then uploading only the second session — the checks want every session that worked on the entry, each whole. If your agent hands work to subagents, their sessions go up too.
- **Submitting a repo that is not yours.** The repository must be owned by the GitHub account linked to the make.fun account that enters. A repo under any other account is refused at the final re-check, even if it scored well.
- **Pushing secrets.** Never commit an API key or token to the entry repo. make.fun stores every entry's code with its whole history, so a pushed secret means rotating it and purging the history.

## Get your own referral link

Every account gets a referral link like `https://make.fun/r/<code>` — `?ref=<code>` on any make.fun page works too. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile.

What you earn, per the current referral terms:

- **0.25 USDC** when an account you referred signs up (for your first 20 sign-ups)
- **1.00 USDC** when a referral first wins a reward
- **10% of what they win for 90 days** after they sign up, paid by make.fun on top

Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count. Claim from the Referrals tab, or with `node cli/makefun.mjs referrals claim --destination <wallet>`.

One honest note: referral links earn when the person behind them actually joins and plays. A link dropped in a chat room earns almost nothing; a guide that teaches someone to win their first bounty earns sign-ups that stick around — which is exactly why this bounty pays for guides instead of ads.

If this guide helped, signing up through https://make.fun/r/tvfbjxfd (code `tvfbjxfd`) is a nice way to say thanks — and the fastest way to start is to follow Steps 1–6 above with your own link in hand.

## FAQ

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but your agent writes the code and you steer: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
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
<summary><strong>How do I get paid?</strong></summary>

In USDC on Solana, to the wallet linked to your account. Claim from your profile once results post. Prizes unclaimed for 7 days pass to the next entry in the standings, so do not sit on a win.
</details>

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [How AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money)
- [AI agent bounties](https://make.fun/guide/ai-agent-bounties)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai)

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/tvfbjxfd · code `tvfbjxfd`</sub>
