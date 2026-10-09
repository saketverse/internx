# InternX — Product Requirements Document (PRD)

**Product:** InternX  
**Team:** InternX  
**Audience:** Students in India seeking internships and early-career opportunities  
**Status:** Proposed requirements; implementation status must be verified in code.

## 1. Vision

Help students move from finding an internship to understanding its requirements, preparing for it, and managing the application process.

## 2. Problem statement

Opportunity discovery is only one part of the challenge. Students may struggle to interpret eligibility, prioritize skill development, know which documents are needed, and keep track of application deadlines and progress.

These are product hypotheses to validate with students, not claims that every student experiences the same problem.

## 3. Product goals

- Make relevant opportunities easier to discover.
- Present requirements in a consistent, understandable structure.
- Explain which eligibility facts are known, conflicting, or missing.
- Turn role-relevant gaps into concrete preparation tasks.
- Keep saved opportunities and user-entered application progress organized.
- Make opportunity provenance and data freshness visible.

## 4. Non-goals for the first version

- Guaranteeing placements, interviews, or employer responses.
- Submitting applications automatically on behalf of students.
- Predicting hiring decisions or selection probability.
- Building a broad, unsupervised web scraper.
- Training a custom machine-learning model before data and user needs are validated.
- Building native mobile apps, employer dashboards, or a full recruiting marketplace.
- Claiming that every listing is verified or always current.

## 5. Primary users

### Beginner student

Early in college, has limited portfolio experience, and needs role explanations, clear eligibility, and practical first steps.

### Busy student

Balances coursework and applications and needs clear deadlines, saved roles, next actions, and a compact tracker.

### Career explorer

Wants to explore a new field and needs help understanding transferable skills, entry requirements, and preparation options.

These personas are illustrative and should be validated through interviews.

## 6. Main user journey

1. Create or edit a student profile.
2. Search and filter opportunities.
3. Open a role and examine source details.
4. Review requirement-by-requirement eligibility results.
5. Review or create role-specific preparation tasks.
6. Save the role and add it to the tracker.
7. Update the user's own application stage and next action.

## 7. Functional requirements

### P0 — Core MVP

- Student profile with education, skills, interests, and preferences.
- Searchable internship list with filters.
- Internship details with source URL and last-checked date when available.
- Distinction between mandatory and preferred requirements.
- Eligibility result with an explicit unknown/confirmation state.
- Explainable relevance ranking, separate from hard eligibility decisions.
- Roadmap tasks with status and persistence.
- Saved opportunities and application-stage tracking.
- Clearly labelled demo data.
- Responsive interface and useful loading, error, and empty states.

### P1 — Improve the experience

- Optional reminders.
- CSV or structured listing import workflow.
- Listing feedback/reporting workflow.
- Better roadmap prioritization using deadlines and availability.
- Optional plain-language summaries grounded in source content.

### Later — Defer until validated

- Broad automated ingestion.
- Native mobile applications.
- Predictive machine learning.
- Employer dashboards and employer-side workflows.
- Direct application submission.
- Advanced social/alumni features.

## 8. Trust and product requirements

- Every real listing should preserve a canonical source URL where one exists.
- The UI should show listing freshness and known deadline status.
- Unknown dates must not be invented.
- Missing profile data must not automatically mean ineligible.
- Preferred qualifications must not act as hard eligibility rules.
- Users must be able to distinguish demo examples from current opportunities.
- Private profile, application, and task data must be protected.

## 9. Success measures

Measure real usefulness rather than only registrations or page views.

- Time required to find and save a suitable role.
- Whether users can explain eligibility results in their own words.
- Share of users completing at least one suggested preparation task.
- Share of active listings rechecked within the chosen policy.
- Rate of expired or broken links in audited samples.
- Coverage of recommendations with traceable requirement evidence.
- User rating of task usefulness.

Establish baselines before setting numeric targets. Do not fabricate results.

## 10. Validation assumptions

Validate whether students actually experience these problems, which parts are most difficult, and whether the roadmap changes what they do next. The desk-research snapshot did not include user interviews. See [`VALIDATION_PLAN.md`](VALIDATION_PLAN.md).

## 11. Acceptance criteria

The MVP is ready for a controlled demo when a user can complete the core journey end to end, see the reasons behind eligibility outcomes, distinguish demo records, retain application/task changes in the selected data provider, and navigate the experience on a phone-sized viewport.
