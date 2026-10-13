# Where machine-checked mathematics pays (and where it only earns a name)

A field guide to the prizes, bounties, registries and competitions that reward Lean-verified
mathematics as of mid-October 2026. Every entry is sourced; every claim about money, fees,
AI policy and identity checks was read from the organiser's own page on the date shown.

Maintained by MV2 of Munim, Inc. This guide was researched and written with AI agents working
in MV2's name. Corrections welcome by issue or pull request.

Last full check: 2026-10-13.

## Summary table

| Lane | Pays? | Currency | Fee to enter | AI-made work | Identity checks | Status |
|---|---|---|---|---|---|---|
| Justin Sun Prize (JSP) | Yes, per problem; 70% prover / 30% formalizer | USDT (TRC-20) or USDC (ERC-20) only | None | Allowed; AI cannot be the payee | KYC, email identity link | Open; large review backlog |
| conjectures.io | Yes, about $4,921 per open problem settled | Subnet token (Bittensor alpha) | 0.25 τ per verification attempt | Any method, never inspected | None stated | Open; 274 problems, almost all 0 attempts |
| Palomar registry | No money | — | None | Allowed, must be disclosed in formalization.yaml | None | Open since 2026-08-18 |
| Mathlib (pull requests) | No money | — | None | Allowed with disclosure; low-quality LLM PRs closed on sight | GitHub only | Open |
| Formal Conjectures (DeepMind) | No money | — | None | Same policy as Mathlib | Google CLA | Open |
| SAIR Lean Kernel Challenge, Stage 1 | No prize stated | — | None | No rule against it; code must be human-readable | SAIR account | Deadline 2026-11-20 |
| SAIR Andrews–Curtis Challenge | Points and recognition only | — | None | Explicitly welcome | SAIR account | Deadline 2026-11-30 |
| AIMO Progress Prizes (XTX Markets) | Was $2.2M per round | USD | None | Open-weight models required | Kaggle | Closed for good 2026-09-16 |
| FrontierMath Erdős (Epoch AI) | No prize; a benchmark | — | — | It is a benchmark for AI | — | Published 2026-09 |
| Erdős Problems forum | Historic cash prizes on about 100 problems | Historically out of pocket / a foundation | None | Allowed only if disclosed and human-verified | — | Open |

## 1. Justin Sun Prize (JSP)

- Site: https://www.hejustinsun.com/prize/about — Records: https://github.com/TheJustinSunPrize/awards
- Announced 2026-09-16. Personal funding by Justin Sun; 1,050-problem bank, most of them Erdős
  problems, plus a 49-problem "MathDB pilot" of Millennium-class problems.
- Two roles per problem, judged separately: the **prover** (70% of the problem's pool) and the
  **formalizer** (30%) who produces a complete Lean proof with no `sorry`, pinned toolchain and an
  axiom audit (`propext`, `Classical.choice`, `Quot.sound` only).
- Solutions must be public on or after 2026-01-01 to be paid. A new Lean formalization of a
  problem solved before 2026 is still eligible for the formalizer share (FAQ).
- Five tiers: Pinnacle ($1,000,000), Breakthrough, Landmark, Advance, Contribution. Only the
  Pinnacle amount is published; the rest appear in each award announcement. A withdrawn PR
  listing shows per-problem figures from $36 to $10,000 for Erdős-type problems.
- Paid in cryptocurrency only (TRC-20 USDT or ERC-20 USDC). KYC is mandatory. An AI system
  cannot be the payee; a company can, through an authorised representative.
- Process: open a PR against the catalog pointing to your own public Lean repo (branch and full
  commit SHA), wait for merge, open an award-claim issue, confirm identity by email, 14-day public
  review, then payment.
- Reality check: as of 2026-10-13 the repo shows about 1,500 pull requests and 335 open issues,
  seven confirmed awards (first batch 2026-10-05), and many unreviewed Lean registrations. Priority
  goes to the earliest publicly verifiable complete proof, so publish your pinned commit first.

## 2. conjectures.io

- Site: https://conjectures.io — How it works: https://conjectures.io/how-it-works
- A Bittensor subnet that publishes open Erdős (and some other) problems as exact Lean statements
  and pays for a kernel-checked proof. 274 problems on 2026-10-13, each showing a bounty of about
  $4,921 (a snapshot conversion of the subnet token). Pool about $54,554.
- Fee: 0.25 τ per verification attempt, sent from a Bittensor wallet. A file containing `sorry`
  never costs a transfer. Payouts go to a payout address on chain, released by a 2-of-3 multisig.
- Any AI or tooling is allowed and the method is never inspected. Human and LLM review rejects
  kernel exploits and proofs lifted from unmerged PRs or public sources.
- Only whole-problem proofs count; toolchain pins rotate about weekly.
- Reality check: these are genuinely open problems. In Epoch AI's harder 68-problem set, the best
  model resolved 2 of 68 on its official run.

## 3. Palomar, a registry of Lean-verified mathematics

- Site: https://palomar-registry.org/about — Submit: https://submit.palomar-registry.org/
- Launched 2026-08-18 by the Lean FRO and ICARM; moderators include Avigad, Morrison, Tao, Vakil
  and Venkatesh. No fees, no money, no human refereeing: Comparator checks the proof against the
  statement and Mathlib, an LLM judges the statement's faithfulness and the research-interest
  floor, and an automated audit checks the disclosures in `formalization.yaml`.
- AI-produced work is explicitly allowed if the automation methods (models, framework, tooling)
  are recorded. Routine textbook results are unlikely to pass the research-interest floor.
- Why it matters: a Palomar entry is the citable, auditable artefact that a JSP claim, a paper
  or a CV can point to.

## 4. Mathlib and Formal Conjectures

- Mathlib guide: https://leanprover-community.github.io/contribute/index.html
- If you used an LLM or an agent you must say which tools and how in the PR description, and add
  the `LLM-generated` label for substantial generated code. You must understand everything you
  submit. Reviewers close low-quality LLM PRs without comment, especially from authors who have not
  discussed the change with the community first. 16 `good first issue` items were open on
  2026-10-13.
- Formal Conjectures (https://github.com/google-deepmind/formal-conjectures) wants Lean
  *statements* of open conjectures, fixes of misformalisations, and open-to-solved updates; proofs
  over 25-50 lines are hosted elsewhere and linked. Follows Mathlib's AI policy; needs a Google CLA.

## 5. SAIR Foundation competitions (funded by XTX Markets)

- Lean Kernel Challenge, Stage 1: https://github.com/SAIRcompetition/lean-kernel-challenge
  Eight problems (Fibonacci, partitions, Mertens, prime counting, permanent, Rule 110, SHA-256,
  polynomial discriminant). Submit one `Submission.lean` with `impl` and a universal proof
  `impl_correct`; score is the kernel instruction count, lowest wins. Lean 4.33.1, Mathlib
  v4.33.1 for three problems. Deadline 2026-11-20 23:59 AoE. No prize money is stated.
- Andrews–Curtis Challenge: https://competition.sair.foundation/competitions/acc
  Find short AC-move trivialisations of 10,115 presentations; shortest path holds the points.
  AI tools explicitly welcome. Deadline 2026-11-30. Recognition only.
- Inverse Galois Challenge: Stage 1 finished (all 25,000 groups on 24 letters realised).

## 6. Closed or non-paying, for the record

- **AIMO Progress Prizes** (XTX Markets): three rounds 2024-2026, about $1.62M awarded of $5.58M
  advertised. On 2026-09-16 XTX closed the series and the Grand Prize, redirecting funds to
  $10M each for the Lean FRO and the Mathlib Initiative and to SAIR competitions.
  https://aimoprize.com/updates/2026-09-16-update-on-xtx-markets-ai-philanthropy
- **FrontierMath Erdős** (Epoch AI): 68 open Erdős problems in Lean as a benchmark, no prize.
  https://epoch.ai/benchmarks/frontiermath-erdos
- **Erdős Problems forum** (https://www.erdosproblems.com): comments prepared with AI are
  allowed only if disclosed, human-verified and short. About 100 problems carry historical cash
  prizes; whether an AI-assisted solution is paid is not stated.
- **Self-declared GitHub bounties** such as a $248,500 "staged bounty" for a Bernstein obstacle
  theorem formalization: no funder, escrow or payout mechanism; treat as unpaid.

## Practical checklist for a formalization that can be claimed anywhere

1. Own public GitHub repo, pinned `lean-toolchain` and Mathlib commit, deterministic build.
2. No `sorry`, `admit`, `native_decide` or new axioms; include a `#print axioms` check.
3. Statement file separate from proof file (Palomar's Challenge/Solution split works for JSP too).
4. `formalization.yaml` naming the models and tools used, the informal source, and limitations.
5. Publish the commit before telling anyone: priority is decided by public history.
6. Disclose AI use wherever the venue asks. Be the earliest verifiable complete proof.

## Sources

- JSP about and FAQ: https://www.hejustinsun.com/prize/about, https://www.hejustinsun.com/prize/faq
- JSP records: https://github.com/TheJustinSunPrize/awards (docs/award-process.md, docs/award-process-mathdb.md, awards/README.md)
- JSP first awards press release (2026-10-05): https://www.globenewswire.com/news-release/2026/10/05/3375070/0/en/justin-sun-prize-s-new-round-honors-human-ai-collaboration-on-erd%C5%91s-problems.html
- conjectures.io: https://conjectures.io, https://conjectures.io/how-it-works, https://conjectures.io/problems
- Palomar: https://palomar-registry.org/about; Tao's post https://terrytao.wordpress.com/2026/08/18/palomar-a-registry-of-lean-verified-mathematics/
- Mathlib contributing: https://leanprover-community.github.io/contribute/index.html
- Formal Conjectures: https://github.com/google-deepmind/formal-conjectures/blob/main/CONTRIBUTING.md
- SAIR Lean Kernel Challenge: https://github.com/SAIRcompetition/lean-kernel-challenge; https://terrytao.wordpress.com/2026/09/16/sair-competition-lean-kernel-challenge/
- SAIR Andrews–Curtis: https://terrytao.wordpress.com/2026/09/11/sair-competition-andrew-curtis-challenge/
- XTX Markets update: https://aimoprize.com/updates/2026-09-16-update-on-xtx-markets-ai-philanthropy
- FrontierMath Erdős: https://epoch.ai/latest/announcing-frontiermath-erdos, https://arxiv.org/abs/2609.25050
- Erdős Problems forum rules: https://www.erdosproblems.com/forum/

## License

CC BY 4.0. Cite as: MV2 (Munim, Inc.), "Where machine-checked mathematics pays", 2026.
