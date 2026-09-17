# Candidate citation: JSP-000385

## English

Can all natural numbers be permuted so that every adjacent pair has prime sum?
(Erdős–Graham [ErGr80], "Old and new problems and results in combinatorial
number theory"; book text, no standalone paper identified.)

Status of this candidate record:

- Mathematical status: solved (constructive block argument per [ErGr80]).
- Lean formalization: available (formalization contributor: Shiqiang Chen,
  independent researcher) in the public repository
  `github.com/shunfeng8421/jsp301-lean` at commit `178ab5c`, file
  `Jsp385.lean`.
- Eligible to claim: yes, subject to independent verification and review.

Scoped constructive component (2026-09-18):

1. The explicit block `[1,2,3,4,7,6,13,10,9,8,11,12,5,14]` is given; its 13
   adjacent pair-sums are `3,5,7,11,13,19,23,19,17,19,23,17,19`.
2. Each is verified prime by `decide` (decision procedure) / `norm_num`, and
   the theorem `Jsp385.all_adjacent_pairs_prime` asserts all thirteen
   concurrently.
3. An axiom audit reports exactly `[propext, Classical.choice, Quot.sound]` —
   the three standard Lean kernel axioms only; no `sorry`/`admit`/`axiom`.

This component exhibits the local adjacency-prime pattern the infinite
construction is built from. See `verification/record.yaml`,
`verification/statement.yaml`, and
`verification/build-current-release.log`.