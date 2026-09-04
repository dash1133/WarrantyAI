# Autoliv WarrantyAI

Warranty recovery and field-quality console for a Tier 1 automotive supplier. Static
prototype — no backend, no build step, no dependencies.

## The design premise

Every screen is a worksheet on the right and an agent on the left. The worksheet is a
normal SaaS application: fields, options, a submit button. The agent can complete any of
it. Both paths write the same values to the same record and the same activity trail, and
the user chooses between them task by task.

The agent proposes; a person confirms. Nothing with money attached bypasses the policy gate.

## Modules

| Module | What it holds |
|---|---|
| Claims Intake | OEM claim extracts, debit memos, part returns, field escalations |
| Case Management | Case desk, returned-parts analysis, recovery and dispute, provision |
| Triage & Improvement | Emerging-issue signals, containment, 8D and corrective action, predictive model |
| Insights | IPTV, CPV, NTF and recovery reporting over the same records |

## Demo users

Sign in with any user ID from the dropdown. Each lands on the same triage home, scoped to
what that role can action; areas outside scope stay visible but locked.

| User ID | Role | Owns |
|---|---|---|
| `e.vargas` | Warranty Claims Analyst | Feed mapping, debit-memo screening |
| `k.sato` | Customer Quality Engineer | Disposition worksheet, NTF adjudication |
| `i.halvorsen` | Field Quality & Warranty Manager | Containment decision, narrative clusters |
| `a.berg` | Product-Related Liabilities Controller | Provision position |
| `l.fischer` | Product Safety Lead | Safety referral |

Password field is decorative. Switch users at any time from the user chip, top right.

## Try the two paths

1. Sign in as `e.vargas` and open **Debit memo needs a validity screen**.
2. Expand finding 2 and set it by hand — that is the SaaS path.
3. Then ask the agent, in the left pane: *"Run the validity screen."*
4. Apply the proposal. All five findings are set, and the activity trail records that the
   agent proposed it and you confirmed it.

## Files

```
index.html      the application (single file, no dependencies)
features.html   AI capability brief - what the agent does and where AI is required
assets/         Infinite Possibilities logo
vercel.json     headers, clean URLs
```

## Deploy

```bash
# from this directory
npx vercel        # preview
npx vercel --prod # production
```

Or push the folder to a Git repo and import it in Vercel. Framework preset:
**Other**. Build command: none. Output directory: `./`.

Local preview:

```bash
npm run dev   # http://localhost:3000
```

## Notes

- Fonts load from Google Fonts (Archivo, IBM Plex Mono). The page degrades to system
  fonts without network access.
- The Infinite Possibilities logo is embedded as a data URI in `index.html` so the app is
  self-contained; `assets/` holds the file copy used by `features.html`.
- All figures are synthetic. Autoliv-specific numbers that appear in the brief (reserve
  balances, recall exposure ranges) come from public filings; everything at claim, lot and
  part level is invented for the prototype.

---

Built by Infinite Possibilities.
