# InternX

**Tagline:** From Finding Internships to Becoming Application-Ready.  
**Built by:** Team InternX  
**Project:** Personalized internship discovery and preparation platform for students in India.

> **Project status:** Prototype / development. This repository describes the intended product and proposed technical design. Update this status and the feature checklist as implementation is verified. Do not describe a feature as complete until it has been built and tested.

## What is InternX?

InternX is designed to help students move beyond finding internship listings. It connects opportunity discovery with understandable eligibility checks, role-specific preparation tasks, and application tracking.

**Core journey:** Discover → Understand → Check Eligibility → Prepare → Apply → Track.

## The problem

Students may need to check many websites and communities to find opportunities. Even after discovering a role, they may not know which requirements are mandatory, how their skills compare, what to prepare next, or how to organize deadlines and application progress.

## Our approach

InternX aims to provide:

- **Internship Radar:** Search and filter opportunities.
- **Internship Explained:** Present role requirements in a clearer structure.
- **Eligibility Checker:** Compare documented requirements with a student's profile and show uncertainty explicitly.
- **Personalized Roadmap:** Turn relevant gaps into practical preparation tasks.
- **Application Command Center:** Save roles and track the student's own application stages.
- **Trust Layer:** Preserve official source links and show listing status and last-checked dates when known.

InternX does not guarantee internships, interviews, or selection. Relevance scores are not hiring probabilities.

## Current scope

The first version should focus on one complete, reliable journey:

1. Create or edit a student profile.
2. Discover a relevant internship.
3. Read its documented requirements and source information.
4. Check eligibility with outcomes such as **Meets**, **Does not meet a known requirement**, or **Needs confirmation**.
5. Generate or create preparation tasks tied to the role.
6. Save the role and track application progress.

A rules-based engine and a small curated dataset are sufficient for an initial prototype. AI-powered summaries and natural-language search are optional later enhancements.

## Suggested technology stack

Use this stack unless the existing codebase has a suitable alternative:

- **Frontend:** React, Vite, TypeScript
- **Styling:** Tailwind CSS
- **Routing:** React Router
- **Icons:** Lucide React
- **Backend/database:** Supabase and PostgreSQL
- **Authentication:** Supabase Auth, when configured
- **Deployment:** Vercel or an equivalent host
- **Optional AI:** Server-side LLM API integration, only after the core workflow works

See [`docs/TECHNICAL_ARCHITECTURE.md`](docs/TECHNICAL_ARCHITECTURE.md) for the proposed design.

## Run locally

These instructions assume the project contains a Node.js package manifest (`package.json`). Adjust the commands if the implementation uses a different setup.

1. Install a supported Node.js LTS version.
2. Clone this repository and open the project folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Create a local environment file from the template:

   ```bash
   cp .env.example .env
   ```

   On Windows Command Prompt, use `copy .env.example .env`.

5. If using Supabase, set the URL and public anon/publishable key in `.env`. Do not put a service-role key in frontend variables.
6. Start the development server:

   ```bash
   npm run dev
   ```

7. To see the scripts available in this project, run:

   ```bash
   npm run
   ```

Run the build and test commands actually defined in `package.json`. Do not assume a test script exists until it has been configured.

### Demo mode

The app should support a clearly labelled local demo mode so the main user journey can be demonstrated before Supabase credentials are configured. Demo listings must be visibly identified as illustrative and must not be represented as verified live openings. Check the current implementation and README instructions before relying on demo persistence or authentication behavior.

## Environment variables

See [`.env.example`](.env.example). The expected frontend variables are:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_ANON_KEY`

The anon/publishable key is intended for client applications when database access is correctly protected by Row Level Security. **Never expose a Supabase service-role key or other private server secret in frontend code.**

## Repository guide

```text
.
├── README.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── CHANGELOG.md
├── .env.example
├── .gitignore
├── docs/
│   ├── PRODUCT_REQUIREMENTS.md
│   ├── FEATURE_SPECIFICATION.md
│   ├── TECHNICAL_ARCHITECTURE.md
│   ├── DATABASE_SCHEMA.md
│   ├── ELIGIBILITY_AND_MATCHING.md
│   ├── DATA_QUALITY_POLICY.md
│   ├── SECURITY_AND_PRIVACY.md
│   ├── ROADMAP.md
│   ├── COMPETITOR_ANALYSIS.md
│   ├── VALIDATION_PLAN.md
│   ├── DEMO_GUIDE.md
│   └── FAQ.md
└── .github/
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
        ├── bug_report.md
        └── feature_request.md
```

The actual implementation may use a different directory structure; keep this guide synchronized with the repository as it evolves.

## Documentation

- [Product requirements](docs/PRODUCT_REQUIREMENTS.md)
- [Feature specification and MVP scope](docs/FEATURE_SPECIFICATION.md)
- [Technical architecture](docs/TECHNICAL_ARCHITECTURE.md)
- [Proposed database schema](docs/DATABASE_SCHEMA.md)
- [Eligibility and matching logic](docs/ELIGIBILITY_AND_MATCHING.md)
- [Data quality and source policy](docs/DATA_QUALITY_POLICY.md)
- [Security and privacy](docs/SECURITY_AND_PRIVACY.md)
- [Development roadmap](docs/ROADMAP.md)
- [Competitor analysis](docs/COMPETITOR_ANALYSIS.md)
- [Validation plan](docs/VALIDATION_PLAN.md)
- [Hackathon demo guide](docs/DEMO_GUIDE.md)
- [Frequently asked questions](docs/FAQ.md)

## Research and limitations

The product concept is based on desk research captured on 9 October 2026. The research identifies reliable data, transparent eligibility explanations, and requirement-linked preparation as the most promising focus areas. It also notes that student demand for this exact workflow still needs to be validated directly; no user interviews had been completed in that research snapshot.

Market statistics in the research are historical and attributed to their original reports or reporting outlets. They are not a census of every internship in India. Competitor notes are qualitative, not an exhaustive or permanent feature audit. See [`docs/COMPETITOR_ANALYSIS.md`](docs/COMPETITOR_ANALYSIS.md).

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). Please include tests for changes to eligibility rules, ranking logic, and data handling.

## License

A license has not yet been selected for this project. Add an appropriate `LICENSE` file before allowing others to reuse, distribute, or modify the code. Do not assume that public availability alone grants reuse permission.
