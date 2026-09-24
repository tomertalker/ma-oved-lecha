# Deploy progress: patient survey "מה עובד לך"

Brief: `/sdcard/Download/survey/DEPLOY.md`, with step 2 changed by Tomer (product list from Stage 1, GROWERS rebuilt, category tag from `p.cat`).
One line per finished step. On resume: read this, check what exists, don't rerun `schema.sql` on a project that already has the tables.

- [x] 2a. Product list: `reco-engine/out/survey_products.json`, 207 products (168 catalogue flowers, all categories, + 39 old-snapshot products no longer listed), deduped by SKU; fields s,h,e,g,c,cat (reco-engine 66d91df).
- [x] 2b. `index.html` = `survey.html` with three edits: PRODUCTS = that list, GROWERS = 30 unique non-empty growers (sorted), plistHTML tag `T22/C4` → `p.cat` (omitted if empty). Supabase keys still empty (preview mode).
- [x] 2d. Category shown next to picked product names: picked chips, rating card title, compare cards (grey tag); best/worst chips as "name · T15/C3"; recap summary. Payload unchanged.
- [x] 2e. License options = flower categories in the catalogue, THC high→low (tie: CBD low→high): T22/C4 (preselected), T18/C3, T15/C3, T10/C2, T10/C10, T3/C15, T1/C22, אחר. Dropped T20/C4, T1/C20.
- [ ] 1. Supabase project (Frankfurt) + `schema.sql`: BLOCKED, no Supabase CLI or access; waiting for Tomer to send the Project URL + anon key.
- [ ] 2c. Fill SUPABASE_URL / SUPABASE_ANON_KEY (anon only).
- [ ] 3. GitHub repo `tomertalker/ma-oved-lecha` + Pages from main root: BLOCKED, `gh` not installed; waiting for Tomer to decide on GitHub access.
- [ ] 4. Live tests (insert ok ×2, select/update/delete denied ×2, `curl -I` 200, test rows deleted).
- [ ] 5. Report.
