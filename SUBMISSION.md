# ScopeLedger — submission draft

## Inspiration

Agency scope changes become priced, traceable quotes rather than invisible unpaid work.

## What it does

The server computes quarter-hour effort, contingency, integer-cent pricing and contribution after delivery cost. D1 stores workspace-isolated projects, quotes and status histories. Guarded draft → review → approved/declined transitions prevent repeated approval. CSV exports escape formula-leading values.

## What is implemented and what remains

Client review is an internal demo preview, not a signed contract or externally authenticated client decision. Subscription tiers are a proposed monetization blueprint; payment collection and public review links are not implemented. No customer revenue or traction is claimed.

## Architecture

React 19 client UI → same-origin Vinext Worker routes → Cloudflare D1. Tailwind CSS and Lucide icons. MIT licensed. Test source, database schema and migration are included.

## Validation

4 focused unit tests pass. Runtime and submission verification are tracked separately; unit tests do not establish live PayPal integration or official submission.

## Demo sequence

Show the initial workflow, execute the primary action, show its result and persistence, then demonstrate an invalid or unsupported case. Explain current limitations in English. All displayed sample data is fictional.

## Required before submission

- Public source repository accepted by this competition.
- Working demo access for judges.
- A real recorded demonstration, uploaded to the required public video provider.
- User confirmation of the specific competition’s official terms at the final submission step.
