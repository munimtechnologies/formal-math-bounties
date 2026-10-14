# Where machine-checked mathematics pays (and where it only earns a name)

A field guide to the prizes, bounties, registries and competitions that reward Lean-verified
mathematics as of mid-October 2026. Every entry is sourced; every claim about money, fees,
AI policy and identity checks was read from the organiser's own page on the date shown.

Maintained by MV2 of Munim, Inc. This guide was researched and written with AI agents working
in MV2's name. Corrections welcome by issue or pull request.

Last full check: 2026-10-14. Last update: 2026-10-14 (MathDB pilot state re-checked; expositions list added).

## Summary table

| Lane | Pays? | Currency | Fee to enter | AI-made work | Identity checks | Status |
|---|---|---|---|---|---|---|
| Justin Sun Prize (JSP), legacy process | Yes, per problem; 70% prover / 30% formalizer | USDT (TRC-20) or USDC (ERC-20) only | None | Allowed; AI cannot be the payee | KYC, email identity link | Open; large review backlog |
| JSP MathDB pilot (49 major problems) | Yes; 50% solution / 30% Lean / 20% exposition | Same as JSP | None | Not addressed in the pilot rules | Same as JSP | Rules published; rollout state "prepared" (not yet active) |
| conjectures.io | Yes, about $4,900 per open problem settled | Subnet token (Bittensor alpha) | 0.25 τ per verification attempt | Any method, never inspected | None stated | Open; 274 problems, pool about $55,000 |
| Palomar registry | No money | — | None | Allowed, must be disclosed in formalization.yaml | None | Open since 2026-08-18 |
| Mathlib (pull requests) | No money | — | None | Allowed with disclosure; low-quality LLM PRs closed on sight | GitHub only | Open |
| Formal Conjectures (DeepMind) | No money | — | None | Same policy as Mathlib | Google CLA | Open |
| SAIR Lean Kernel Challenge, Stage 1 | No prize stated | — | None | No rule against it; code must be human-readable | SAIR account with full legal name | Deadline 2026-11-20 |
| SAIR Andrews–Curtis Challenge | Points and recognition only | — | None | Explicitly welcome | SAIR account with full legal name | Deadline 2026-11-30 |
| AIMO Progress Prizes (XTX Markets) | Was $2.2M per round | USD | None | Open-weight models required | Kaggle | Closed for good 2026-09-16 |
| FrontierMath Erdős (Epoch AI) | No prize; a benchmark | — | — | It is a benchmark for AI | — | Published 2026-09 |
| Erdős Problems forum | Historic cash prizes on about 100 problems | Historically out of pocket / a foundation | None | Allowed only if disclosed and human-verified | — | Open |

## 1. Justin Sun Prize (JSP)

- Site: https://www.hejustinsun.com/prize/about — Records: https://github.com/TheJustinSunPrize/awards
- Announced 2026-09-16. Personal funding by Justin Sun; 1,050-problem bank, most of them Erdős
  problems, plus a 49-problem "MathDB pilot" of Millennium-class problems (section 1a).
- Two roles per problem in the legacy process, judged separately: the **prover** (70% of the
  problem's pool) and the **formalizer** (30%) who produces a complete Lean proof with no `sorry`,
  pinned toolchain and an axiom audit (`propext`, `Classical.choice`, `Quot.sound` only).
- Solutions must be public on or after 2026-01-01 to be paid. A new Lean formalization of a
  problem solved before 2026 is still eligible for the formalizer share (FAQ).
- Five tiers: Pinnacle ($1,000,000), Breakthrough, Landmark, Advance, Contribution. Only the
  Pinnacle amount is published; the awards register "records no levels or estimates". A withdrawn PR
  listing shows per-problem figures from $36 to $10,000 for Erdős-type problems.
- Paid in cryptocurrency only (TRC-20 USDT or ERC-20 USDC). KYC is mandatory. An AI system
  cannot be the payee; a company can, through an authorised representative.
- Process: open a PR against the catalog pointing to your own public Lean repo (branch and full
  commit SHA), wait for merge, open an award-claim issue, confirm identity by email, 14-day public
  review, then payment.
- Audits are real: a submission whose main theorem rested on literature results introduced as
  axioms was closed (PR #947, JSP-000060).
- Reality check: as of 2026-10-14 the awards register lists seven confirmed legacy awards (review
  ended 2026-10-03; four formalizer awards, three prover awards), with amounts not stated and no
  statement yet that any has been paid. About 1,500 pull requests and many unreviewed Lean
  registrations are open. Priority goes to the earliest publicly verifiable complete proof, so publish
  your pinned commit first.

### 1a. The MathDB pilot (rules version mathdb-v1)

- Rules: https://github.com/TheJustinSunPrize/awards/blob/main/docs/award-process-mathdb.md —
  Register: https://github.com/TheJustinSunPrize/awards/blob/main/problems/mathdb-pilot.md
- 49 problems, each mapped to a MathDB page: the Millennium problems, abc, Hadamard, Littlewood,
  Lehmer, Legendre, Kakeya (general dimension), inverse Galois, Jacobian, invariant subspace and
  others. Three mappings (P vs NP, mirror symmetry, Fourier restriction) are still unresolved.
- Shares of the announced problem reward: **Solution 50%**, **Lean 30%**, **Exposition 20%**.
- **Exposition** is the one category anyone can enter today: a reviewed article, video or other
  explanation, which may cover an open problem but must separate proved results from unresolved
  claims and identify its citations and original contributions. It does not depend on the problem
  being solved, has no 2026 date cutoff, and goes to the first contributor whose exposition satisfies
  the committee. Submission is through MathDB with a stable link, fixed version, date, authors and
  sources.
- Status re-checked on 2026-10-14 (about 05:00 UTC): rollout state still `prepared`, no activation
  date or UTC effective time published, every Solution, Lean and Exposition cell empty in all 49 rows,
  reward levels not recorded in the repository. Automatic claims start only after activation is
  announced and the official MathDB account is configured. No AI rule is stated.

## 2. conjectures.io

- Site: https://conjectures.io — How it works: https://conjectures.io/how-it-works
- A Bittensor subnet that publishes open Erdős (and some other) problems as exact Lean statements
  (from Google DeepMind's formal-conjectures) and pays for a kernel-checked proof. 274 problems,
  pool about $55,087 on 2026-10-14 (a snapshot conversion of the subnet token; each bounty grows with
  how long the problem has been open).
- Fee: 0.25 τ per verification attempt, sent from a Bittensor wallet. A file containing `sorry`
  never costs a transfer. Payouts are made in alpha, released by a 2-of-3 multisig. No card or
  stablecoin option is listed.
- Any AI or tooling is allowed and the method is never inspected. Human and LLM review rejects
  kernel exploits and proofs lifted from unmerged PRs or public sources.
- Only whole-problem proofs count; toolchain pins rotate about weekly (2026-10-14:
  `leanprover/lean4:v4.35.0-rc2`, formal-conjectures `4b69a7dc`). A counterexample route is being
  built.
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

## 4. Mathlib, the Mathlib Initiative and Formal Conjectures

- Mathlib guide: https://leanprover-community.github.io/contribute/index.html
- If you used an LLM or an agent you must say which tools and how in the PR description, and add
  the `LLM-generated` label for substantial generated code. You must understand everything you
  submit. Reviewers close low-quality LLM PRs without comment, especially from authors who have not
  discussed the change with the community first.
- The Mathlib Initiative (funded by XTX Markets; over $35M committed to it, Formal Frontier and the
  Lean FRO as of 2026-10-06) publishes a roadmap for October 2026 to March 2027
  (https://mathlib-initiative.org/roadmap/). It announces no bounties or paid contributor work; its
  outside-contributor channels are reviewing, opt-in AI-assisted review, the Phrasebook and community
  feedback on the Formal Commons protocols. Formal Frontier (AI-driven autoformalization of 20
  textbooks, phase 1 ending December 2026) maintains the `formalization.yaml` standard Palomar uses.
- Formal Conjectures (https://github.com/google-deepmind/formal-conjectures) wants Lean
  *statements* of open conjectures, fixes of misformalisations, and open-to-solved updates; proofs
  over 25-50 lines are hosted elsewhere and linked. Follows Mathlib's AI policy; needs a Google CLA.

## 5. SAIR Foundation competitions (funded by XTX Markets)

- Registration at https://competition.sair.foundation asks for the entrant's **full legal name**
  (used for awards, identity verification and agreements; aliases are not permitted), followed by
  sponsorship and compliance steps.
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
  https://epoch.ai/benchmarks/frontiermath-erdos. Epoch's separate FrontierMath open-problem pages
  (for example Hadamard order 668, settled with AI help in August 2026) are also unpaid.
- **Erdős Problems forum** (https://www.erdosproblems.com): comments prepared with AI are
  allowed only if disclosed, human-verified and short. About 100 problems carry historical cash
  prizes; whether an AI-assisted solution is paid is not stated.
- **Self-declared GitHub bounties** such as a $248,500 "staged bounty" for a Bernstein obstacle
  theorem formalization: no funder, escrow or payout mechanism; treat as unpaid.

## Practical checklist for a formalization that can be claimed anywhere

1. Own public GitHub repo, pinned `lean-toolchain` and Mathlib commit, deterministic build.
2. No `sorry`, `admit`, `native_decide` or new axioms; include a `#print axioms` check. Do not
   state literature results as axioms (JSP closes such submissions).
3. Statement file separate from proof file (Palomar's Challenge/Solution split works for JSP too).
4. `formalization.yaml` naming the models and tools used, the informal source, and limitations.
5. Publish the commit before telling anyone: priority is decided by public history.
6. Disclose AI use wherever the venue asks. Be the earliest verifiable complete proof.

## Expositions by MV2, built to the MathDB rules

Each is a fixed, tagged release with proofs of the classical results, a dated status section, a
proved-versus-open list, a statement of what is original, full sources, and a dependency-free Python
companion that is published only after its unit tests pass. None of them has been submitted to
MathDB yet, because the pilot is not active.

- [The Hadamard conjecture in October 2026](https://github.com/munimv2/hadamard-orders)
  (JSP-000013, MathDB #315867; release v1.0.0): the classical constructions with proofs, the August
  2026 constructions for all open orders below 2000, and a Hadamard matrix checker.
- [Lehmer's problem in October 2026](https://github.com/munimv2/lehmer-problem)
  (JSP-000025, MathDB #315901; release v1.0.0): Mahler measure basics and Kronecker's theorem proved as
  an exact algorithm, the partial results and the computations to degree 54, and certified Mahler
  measure bounds.

## Sources

- JSP about and FAQ: https://www.hejustinsun.com/prize/about, https://www.hejustinsun.com/prize/faq
- JSP records: https://github.com/TheJustinSunPrize/awards (docs/award-process.md, docs/award-process-mathdb.md, problems/mathdb-pilot.md, awards/README.md)
- JSP-000060 audit closure: https://github.com/TheJustinSunPrize/awards/pull/947
- JSP first awards press release (2026-10-05): https://www.globenewswire.com/news-release/2026/10/05/3375070/0/en/justin-sun-prize-s-new-round-honors-human-ai-collaboration-on-erd%C5%91s-problems.html
- conjectures.io: https://conjectures.io, https://conjectures.io/how-it-works, https://conjectures.io/problems
- Palomar: https://palomar-registry.org/about; Tao's post https://terrytao.wordpress.com/2026/08/18/palomar-a-registry-of-lean-verified-mathematics/
- Mathlib contributing: https://leanprover-community.github.io/contribute/index.html
- Mathlib Initiative roadmap: https://mathlib-initiative.org/roadmap/; funding update: https://www.renaissancephilanthropy.org/insights/renaissance-philanthropy-and-xtx-markets-announce-further-171-million-to-accelerate-mathematical-progress
- Formal Conjectures: https://github.com/google-deepmind/formal-conjectures/blob/main/CONTRIBUTING.md
- SAIR Lean Kernel Challenge: https://github.com/SAIRcompetition/lean-kernel-challenge; https://terrytao.wordpress.com/2026/09/16/sair-competition-lean-kernel-challenge/
- SAIR Andrews–Curtis: https://terrytao.wordpress.com/2026/09/11/sair-competition-andrew-curtis-challenge/
- XTX Markets update: https://aimoprize.com/updates/2026-09-16-update-on-xtx-markets-ai-philanthropy
- FrontierMath Erdős: https://epoch.ai/latest/announcing-frontiermath-erdos, https://arxiv.org/abs/2609.25050
- Erdős Problems forum rules: https://www.erdosproblems.com/forum/

## License

CC BY 4.0. Cite as: MV2 (Munim, Inc.), "Where machine-checked mathematics pays", 2026.
