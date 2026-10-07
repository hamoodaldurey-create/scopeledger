# ScopeLedger

Agency scope changes become priced, traceable quotes rather than invisible unpaid work.

Entry being prepared for **Galuxium Nexus V2**. Created October 7, 2026. Not submitted yet.

## Working implementation

The server computes quarter-hour effort, contingency, integer-cent pricing and contribution after delivery cost. D1 stores workspace-isolated projects, quotes and status histories. Guarded draft → review → approved/declined transitions prevent repeated approval. CSV exports escape formula-leading values.

## Run locally

Use Node 22.13 or later. Install the locked dependencies with `pnpm install --frozen-lockfile`. Run `pnpm db:generate` only after editing db/schema.ts. Run `pnpm build` to produce the Worker and D1 configuration. Apply the included migration to the local DB:

```sh
node --import ./scripts/sites-env.mjs ./node_modules/wrangler/bin/wrangler.js d1 execute DB --local --config dist/server/wrangler.json --persist-to .wrangler/state --file drizzle/0000_mixed_patriot.sql
pnpm dev
```

The dev command uses the configured execution profile. The standalone Worker preview uses `pnpm start`. The managed Sites environment uses its preview supervisor. Deploy through Sites or adapt the logical D1 binding for your own Cloudflare account.

## Tests

`pnpm test` bundles and runs tests/ledger.test.ts with Node’s test runner. 4 focused tests currently pass. `pnpm exec tsc --noEmit` checks source types.

## Data and access

The demo uses synthetic sample data. Anonymous demo state is isolated using an HttpOnly random capability cookie; authenticated Sites requests use the trusted Site-scoped user ID. No client-supplied owner ID is trusted. Same-origin checks protect write requests. Revision checks prevent lost updates in the household and quote workspaces. This is a hackathon MVP, not a production security certification.

## Current limitations

Client review is an internal demo preview, not a signed contract or externally authenticated client decision. Subscription tiers are a proposed monetization blueprint; payment collection and public review links are not implemented. No customer revenue or traction is claimed.

## Submission status

Public demo: https://scopeledger-hamood.hamood-al-du-3093.chatgpt.site

The complete source snapshot is included in `source.zip`. Extract it into a new directory before running the commands above:

```sh
mkdir source
cd source
unzip ../source.zip
```

The source snapshot matches the verified deployed implementation. Public video upload and official Devpost submission remain outstanding. This is not yet an officially submitted entry.

## License

MIT. Bundled dependencies retain their own licenses.
