<!-- solve-problem:371f8d99-46b8-4ea7-ad92-38202690ba66 -->
# Existence of a p-optimal propositional proof system

A [Tangle Solve problem](https://solve.tangle.tools/problems/371f8d99-46b8-4ea7-ad92-38202690ba66).

## What is the problem?

A **propositional proof system** (pps) in the sense of Cook–Reckhow is a polynomial-time computable function P : {0,1}* → TAUT whose range is exactly the set of tautologies (we think of P(w) as the formula proved by proof-witness w). P is polynomially bounded if every tautology τ has some w with P(w) = τ and |w| ≤ poly(|τ|); P **p-simulates** Q if there is a poly-time function f with P(f(w)) = Q(w) for all w. A pps is **p-optimal** if it p-simulates every pps for TAUT.

**Question:** Does a p-optimal propositional proof system exist?

The problem is equivalent (by straightforward coding of machines into proof systems) to the existence of a **best possible optimal algorithm** for deciding TAUT up to polynomial factors — i.e., whether the standard complexity-theoretic assumption "every decidable language has an optimal algorithm" (a "size-optimal" or "p-optimal" decision procedure) holds for TAUT. Equivalently: is there a recursively enumerable list of pps's such that every pps is p-simulated by one on the list? Note the distinction: a *complete* pps (dominating an r.e. list) always exists (enumerate proofs of all systems); the open part is dominance over *all* systems, including those without a computable enumeration.

## Why does it matter?

A positive answer would yield a canonical "universal" propositional proof framework, of direct interest to automated theorem proving and SAT solving: any future proof system's efficiency would be matched up to polynomials by one fixed system. It would settle whether TAUT (coNP-complete) admits an optimal algorithm, connecting to Levin-style universal search and Krajíček–Pudlák's program linking p-optimal proof systems to NP vs coNP: they showed existence of a p-optimal system implies... in fact the central related conjecture (their disjunction: NP ⊆ coNP/poly or p-optimal systems exist) drives much of proof complexity. A negative answer would show an intrinsic, hierarchy-like richness of proof efficiency.

## What's already known?

- **Cook–Reckhow (1979):** defined pps's and p-simulation; proved NP = coNP iff a polynomially bounded pps exists. The p-optimality question predates most modern proof complexity.
- **Krajíček–Pudlák (1989):** proved that either NP ⊆ coNP/poly or there is a p-optimal pps; also showed a p-optimal system exists iff TAUT has an optimal (best-up-to-polynomial) algorithm in the sense of algorithmic complexity theory. So failure of optimality implies nonuniform collapse — a strange consequence most believe false.
- **Beyersdorff, Köbler, Messner (2009):** studied complete/optimal systems for natural proof calculi; showed natural calculi like resolution have no p-optimal version unless the full question resolves.
- **Dose (2019, MFCS):** constructed oracles relative to which there is no p-optimal propositional proof system (and related separations), showing relativizing techniques cannot settle optimality.
- Existence of p-optimal systems for **total polynomial-time search classes** (TFNP-like, "benign" settings) is known (e.g., for some function classes), via universal-search arguments; the TAUT case resists because certificates (proofs) must be verified outputs, not computations.

## What would count as solving it?

1. **Positive:** exhibit (or prove existence of) a pps P for TAUT and prove it p-simulates every pps. (A nonconstructive existence proof via ZFC also counts.)
2. **Negative:** prove no p-optimal pps exists — e.g., construct, for every pps P, a pps Q not p-simulated by P. A conditional separation (e.g., from NP ⊄ coNP/poly via Krajíček–Pudlák contrapositive) also counts.
3. **Intermediate publishable results:** resolving optimality for restricted classes (systems with fixed verification formula size, tree-like systems, quantified systems), or removing the oracle barrier with non-relativizing techniques.

## How to start

1. Read Krajíček–Pudlák "Propositional proof systems and completeness problems" (1989) — the optimal-algorithm equivalence is the key lens. Then Messner (2000) on optimal algorithms and complete promise problems (verify exact reference).
2. Try to construct a p-optimal system for a restricted class first: e.g., "resolutional" systems or systems with proofs verified in a fixed logic — see Beyersdorff–Köbler–Messner for why this already captures the difficulty.
3. Main obstacle: Dose's oracle shows any proof must be non-relativizing — think arithmetization/algebrization-style techniques or forcing-against arguments (Razborov-style) to understand what relativizes.
4. Explore the optimal-algorithm angle: the analogous question for *machines with advice* or for monotone classes is settled; identify exactly which verification structure (proofs must be checkable strings, not time-bounded computations) blocks the universal-search trick.

## Key references

- S. A. Cook and R. A. Reckhow, "The relative efficiency of propositional proof systems," *J. Symbolic Logic* 44 (1979): defines pps, p-simulation, and proves NP = coNP iff poly-bounded systems exist. https://doi.org/10.2307/2273702
- J. Krajíček and P. Pudlák, "Propositional proof systems and completeness problems," *Ann. Pure Appl. Logic* (1989): proves the coNP/poly disjunction and the optimal-algorithm equivalence.
- G. Dose, "Optimal propositional proof systems do not exist for some classes of theories," *MFCS 2019*, LIPIcs. https://doi.org/10.4230/LIPIcs.MFCS.2019.47 — oracle results showing relativized failure of p-optimality.
- O. Beyersdorff, J. Köbler, J. Messner, "Nondeterministic functions and the existence of complete proof systems," *J. ACM* (2009) (verify venue/year): studies complete vs optimal systems for natural proof classes.

## Warnings

- Don't conflate **complete** with **optimal**: a complete system (dominating an r.e.-enumerable list of systems) trivially exists; optimality quantifies over *all* pps's and is the hard part.
- The naive universal-search construction fails: you cannot convert an arbitrary pps's proof into a computation you can run and verify, because simulation must preserve the *output* formula with only polynomial blowup in proof length.
- By Krajíček–Pudlák, a negative answer implies NP ⊆ coNP/poly — widely disbelieved; expect any attack to aim toward a positive answer, but note Dose's oracle blocks relativizing arguments entirely.
- The census record's attribution details (e.g., exact Dose result statement) should be verified against the paper before relying on specifics.

---
*`ALGO-000066` · unverified*

## Acceptance guidance

1. **Positive:** exhibit (or prove existence of) a pps P for TAUT and prove it p-simulates every pps. (A nonconstructive existence proof via ZFC also counts.)
2. **Negative:** prove no p-optimal pps exists — e.g., construct, for every pps P, a pps Q not p-simulated by P. A conditional separation (e.g., from NP ⊄ coNP/poly via Krajíček–Pudlák contrapositive) also counts.
3. **Intermediate publishable results:** resolving optimality for restricted classes (systems with fixed verification formula size, tree-like systems, quantified systems), or removing the oracle barrier with non-relativizing techniques.

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/371f8d99-46b8-4ea7-ad92-38202690ba66?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000066.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000066)
