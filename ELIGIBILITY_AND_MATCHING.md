# InternX — Eligibility and Matching Logic

## Purpose

Provide understandable decision support based on documented internship requirements and user-provided information. The system must not predict an employer's hiring decision.

## 1. Requirement model

Every requirement should be classified as:

- **Mandatory:** Explicitly required by the listing.
- **Preferred:** Desirable, but not a hard eligibility condition.
- **Unknown/ambiguous:** The source does not give enough information to classify or evaluate reliably.

Where possible, retain a source excerpt or link to the relevant official page.

## 2. Eligibility outcomes

Evaluate mandatory requirements individually.

1. If at least one documented mandatory requirement conflicts with known profile information, return **Does not meet a known requirement**.
2. Otherwise, if any mandatory requirement is missing, ambiguous, or cannot be evaluated from the profile, return **Needs confirmation**.
3. Otherwise, return **Meets known requirements**.
4. If the listing has no usable mandatory requirement data, state that eligibility cannot be fully assessed; do not imply confirmed eligibility.

A missing profile field is not proof of failure. A preferred-skill gap is not a hard disqualifier.

## 3. Requirement-level output

For each requirement, show:

- The requirement text
- Mandatory/preferred classification
- Outcome
- The profile fact used, if any
- Supporting source excerpt, if available
- A next action when useful

Avoid shaming language. Prefer clear statements such as “Your profile does not yet confirm this requirement.”

## 4. Relevance ranking

A proposed starter formula is:

`S = 0.40K + 0.25I + 0.20A + 0.15P`

Where each component is normalized to 0–100:

- `K` — overlap with role skills, weight 40%
- `I` — field and interest alignment, weight 25%
- `A` — availability, schedule, and timing fit, weight 20%
- `P` — location, work mode, and preference fit, weight 15%

These weights are initial product assumptions, not validated predictive parameters.

## 5. Missing ranking data

Do not automatically assign a score of zero to an unknown component. Either:

- Mark the score unavailable until enough inputs exist, or
- Calculate a provisional score from available components only, renormalizing the available weights and visibly marking the score as partial.

If a partial score is shown, disclose that it may not be directly comparable with scores based on complete information. Encourage profile completion without blocking discovery.

## 6. Separation of concerns

Hard eligibility decisions and relevance ranking are separate:

- A relevance score cannot override a known mandatory conflict.
- A high score is not a probability of being selected.
- Results should explain the factors that were actually used.
- Missing data and source uncertainty must remain visible.

## 7. Example

Hypothetical role requirements:

- Python — mandatory
- SQL — mandatory
- Basic data analysis — preferred

Student profile:

- Reports Python experience
- Has not entered SQL experience
- Data-analysis experience is unknown

Expected behavior:

- Python: Matches reported profile
- SQL: Needs confirmation unless the profile explicitly confirms it is not met
- Basic data analysis: Preferred; not a hard eligibility condition
- Overall eligibility: Needs confirmation if SQL is an unevaluated mandatory requirement
- Roadmap suggestions: Assess SQL requirements and practice relevant concepts, clearly labelled as InternX recommendations

This is an illustrative test case, not a real job opening.

## 8. Testing checklist

Cover:

- All known mandatory requirements met
- One known mandatory conflict
- Missing profile field
- Ambiguous listing text
- No mandatory requirements provided
- Preferred requirement not met
- All ranking components available
- One or more ranking components unavailable
- Empty profile
- Conflicting source updates

Test the domain logic independently of the UI.
