# Experts vs. OCL invariants

Compares the expert labels from [`human_eval.xlsx`](human_eval.xlsx) with the invariant checks of [`General`](../../java/es/uma/Checks/General.java) on the `models-with-ocl` diagrams.

**Expert label.** A judge-unrealistic instance is unrealistic when the experts confirm at least one reported problem (Yes or Partial). A judge-realistic instance is unrealistic when the experts reject a statement of its explanation (specific statement not traceable, or generic statement judged No or Unknown). All other instances are realistic.

## Summary

| Metric | Value |
|---|---|
| Audited instances | 100 |
| Experts: unrealistic | 46 (44 judge-U with a confirmed problem + 2 judge-R with a rejected statement) |
| Experts: realistic | 54 |
| Instances with invariant failures | 45 |
| Agreement (experts match invariants) | 85/100 (85.00%) |

## Cross-table (experts × invariants)

|  | Invariant failures | No invariant failures |
|---|---|---|
| **Experts: Unrealistic** | 38 | 8 |
| **Experts: Realistic** | 7 | 47 |

## Experts unrealistic, invariants pass (8)

- **gpt_5_2 / cot / statemachine / gen5 / complex** — experts: U, judge: R, invariants: 0
- **gpt_5_2 / simple / hotelmanagement / gen14** — experts: U, judge: U, invariants: 0
- **gpt_5_2 / simple / restaurant / gen12** — experts: U, judge: U, invariants: 0
- **gpt_5_2 / cot / bank / gen1 / edge** — experts: U, judge: U, invariants: 0
- **gpt_5_2 / cot / myexpenses / gen6 / boundary** — experts: U, judge: U, invariants: 0
- **gpt_5_2 / cot / pickupnet / gen5 / boundary** — experts: U, judge: U, invariants: 0
  - _Human note:_ The concept of station is unclear. If its a local station it would be unrealistic because it cannot be in Japan and Norway at the same time
- **gpt_5_2 / cot / statemachine / gen6 / baseline** — experts: U, judge: U, invariants: 0
- **gpt_5_2 / simple / myexpenses / gen25** — experts: U, judge: U, invariants: 0

## Experts realistic, invariants fail (7)

- **gpt_5_2 / cot / addressbook / gen1 / complex** — experts: R, judge: R, invariants: 2
  - `checking invariant (3) `Relationship::CoworkerOnlyBetweenPersons': FAILED.`
  - `checking invariant (4) `Relationship::CoworkerSameCompany': FAILED.`
- **gpt_5_2 / cot / hotelmanagement / gen2 / baseline** — experts: R, judge: R, invariants: 1
  - `checking invariant (1) `Bill::SumOfExpenses': FAILED.`
- **gpt_5_2 / simple / bank / gen13** — experts: R, judge: R, invariants: 1
  - `checking invariant (2) `Account::ValidIbanCountry': FAILED.`
- **gpt_5_2 / simple / bank / gen21** — experts: R, judge: R, invariants: 1
  - `checking invariant (2) `Account::ValidIbanCountry': FAILED.`
- **gpt_5_2 / simple / pickupnet / gen18** — experts: R, judge: R, invariants: 1
  - `checking invariant (3) `Shipment::AssignedShouldHaveDriver': FAILED.`
- **gpt_5_2 / simple / bank / gen16** — experts: R, judge: U, invariants: 1
  - _Human note:_ Unsupported claim. Inferring nationalities from names is not a valid procedure
  - `checking invariant (2) `Account::ValidIbanCountry': FAILED.`
- **gpt_5_2 / simple / bank / gen20** — experts: R, judge: U, invariants: 1
  - _Human note:_ Unsupported claim.
  - `checking invariant (2) `Account::ValidIbanCountry': FAILED.`

