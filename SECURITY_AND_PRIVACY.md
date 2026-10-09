# InternX — Security and Privacy

**Status:** Product-level guidance, not legal advice or a security certification.

## 1. Data minimization

Collect only information required to personalize internship discovery and track a student's own progress. Avoid unnecessary identity documents, sensitive information, and detailed personal data that do not serve the product.

Explain why profile fields are requested and make nonessential fields optional.

## 2. Environment and secrets

- Commit `.env.example`, not a real `.env`.
- Keep private server credentials outside the browser.
- Never expose a Supabase service-role key in a `VITE_` variable.
- Rotate any credential that is accidentally committed or disclosed.
- Do not log passwords, access tokens, private notes, or unnecessary profile fields.

## 3. Authentication and access control

When Supabase is used:

- Use the supported authentication provider flow.
- Enable and test RLS for all user-owned data tables.
- Scope profile, saved role, application, and roadmap access to the correct user.
- Test with two separate user accounts to detect cross-user access.
- Do not rely on hidden UI elements as a security boundary.

Demo mode is not production authentication and should be clearly labelled.

## 4. Data privacy principles

- Explain what is collected, why it is needed, and how users can request correction or deletion.
- Keep profiles, notes, and activity records private by default.
- Avoid unnecessary third-party sharing.
- Provide a practical deletion process where supported.
- Restrict administrative listing updates to an appropriately controlled path.

## 5. AI and external services

If AI is added:

- Call the provider from a trusted server-side environment.
- Do not send unnecessary user profile data to an AI provider.
- Do not include secrets in prompts or logs.
- Validate AI-generated content against the source.
- Explain when a summary or task is AI-generated.
- Do not let AI authoritatively decide eligibility from ambiguous information.

Review the privacy and retention practices of every external service before production use.

## 6. Listing and application trust

- Preserve source URLs and check dates.
- Avoid implying an application was submitted when the user only changed a tracker stage.
- Provide a path to report suspicious or incorrect listings.
- Avoid storing employer credentials or automating applications in the MVP.

## 7. Relevant legal review

The research snapshot identifies India's Digital Personal Data Protection Act, 2023 and the Digital Personal Data Protection Rules, 2025 as relevant considerations. Before a public launch, verify current commencement notifications, applicable obligations, age-related requirements, retention practices, and required notices with qualified counsel. Publication of a law or rule should not be treated by this document as proof that every provision has commenced or applies in the same way to every deployment.

## 8. Incident handling

Before public release, define a maintainer contact and a procedure for receiving and responding to security reports. Do not publish a known exploitable vulnerability or exposed personal information in a public issue.

## 9. Release checklist

- [ ] No secrets are committed.
- [ ] RLS policies are enabled and tested where Supabase is used.
- [ ] Cross-user access tests pass.
- [ ] Authentication and error states are checked.
- [ ] Data deletion and correction flows are documented.
- [ ] External service data handling has been reviewed.
- [ ] Demo records cannot be confused with real verified listings.
- [ ] Security reporting contact/process is established.
