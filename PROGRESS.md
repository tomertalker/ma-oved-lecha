# Deploy progress: patient survey "מה עובד לך"

Brief: `/sdcard/Download/survey/DEPLOY.md`, with step 2 changed by Tomer (product list from Stage 1, GROWERS rebuilt, category tag from `p.cat`).
One line per finished step. On resume: read this, check what exists, don't rerun `schema.sql` on a project that already has the tables.

- [x] 2a. Product list: `reco-engine/out/survey_products.json`, 207 products (168 catalogue flowers, all categories, + 39 old-snapshot products no longer listed), deduped by SKU; fields s,h,e,g,c,cat (reco-engine 66d91df).
- [x] 2b. `index.html` = `survey.html` with three edits: PRODUCTS = that list, GROWERS = 30 unique non-empty growers (sorted), plistHTML tag `T22/C4` → `p.cat` (omitted if empty). Supabase keys still empty (preview mode).
- [x] 2d. Category shown next to picked product names: picked chips, rating card title, compare cards (grey tag); best/worst chips as "name · T15/C3"; recap summary. Payload unchanged.
- [x] 2e. License options = flower categories in the catalogue, THC high→low (tie: CBD low→high): T22/C4 (preselected), T18/C3, T15/C3, T10/C2, T10/C10, T3/C15, T1/C22, אחר. Dropped T20/C4, T1/C20.
- [x] 1. Supabase project created by Tomer, `schema.sql` run by Tomer in the SQL Editor (2026-09-25). URL https://yernxedmokifcmpakzgd.supabase.co, key is a publishable key (`sb_publishable_…`). Don't rerun schema.sql.
- [x] 2f. Key tested with curl (read-only probe): apikey-only and apikey+Bearer both reach Postgres as `anon` (select → 401 / 42501 permission denied, as intended). CORS preflight from tomertalker.github.io: 200, allows apikey,content-type,prefer. `post()` now sends the publishable key only as `apikey` (no `Authorization: Bearer`), per Tomer.
- [x] 2c. SUPABASE_URL / SUPABASE_ANON_KEY filled (publishable key only; no secret key anywhere). LIVE = true.
- [x] 3a. `gh` 2.46.0 installed with apt; logged in as tomertalker. gh is the git credential helper for this repo only (repo-local config); global git config unchanged.
- [x] 3b. Public repo https://github.com/tomertalker/ma-oved-lecha created, main pushed. Commits authored as tomertalker <tomertalker@users.noreply.github.com>.
- [x] 3c. Pages on from main root (after 2c), built 2026-09-25 14:11 UTC: https://tomertalker.github.io/ma-oved-lecha/ (HTTPS enforced). Live page is byte-identical to index.html at 7795255.
- [ ] 4. Live tests (insert ok ×2, select/update/delete denied ×2, `curl -I` 200, test rows deleted).
- [ ] 5. Report.
