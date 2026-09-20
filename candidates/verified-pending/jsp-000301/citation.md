# Candidate citation: JSP-000301

## English

Consecutive powerful numbers need not be squares (Erdős problem, catalog JSP-000301).

Status of this candidate record:

- Mathematical status: solved by explicit counterexample (12167 = 23^3, 12168 = 2^3·3^2·13^2 — both powerful and consecutive, neither a square).
- Lean formalization: available (formalization contributor: Shiqiang Chen, independent researcher) in the public repository `github.com/shunfeng8421/jsp301-lean` at commit `9bc23f09dcd91731b6df194644c0ff14e323c67f`, file `Jsp301.lean`.
- Eligible to claim: yes, subject to independent verification and review.

Formal disproof (first public release 2026-09-16 19:09 UTC):

1. `Jsp301.powerful_12167` and `Jsp301.powerful_12168` establish both integers are powerful (every prime divisor has exponent ≥ 2).
2. `Jsp301.not_square_12167` and `Jsp301.not_square_12168` establish neither is a square.
3. `Jsp301.JSP_301` assembles the counterexample: two consecutive powerful numbers, not both squares.
4. Axiom audit reports exactly `[propext, Classical.choice, Quot.sound]`; no `sorry`/`admit`/`axiom`.

See `verification/record.yaml`, `verification/statement.yaml`, and `verification/build-current-release.log`.