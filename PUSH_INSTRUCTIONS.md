# Before you push

1. Open the two Cloudflare dashboard pages named in wrangler.jsonc and fill in the
   two REPLACE_WITH_... values exactly. Do not guess either one.
2. Confirm no other required Worker settings exist that aren't captured here
   (custom domains/routes, environment variables, KV/D1 bindings). If the Worker
   uses any of those, list them in wrangler.jsonc too before the first deploy,
   or the new deploy could serve the site without them.

# Push (run inside this folder)

git init
git add .
git commit -m "Initial import of live qematalamn Worker source"
git branch -M main
git remote add origin https://github.com/fastdigitalksa/qematalamn.git
git push -u origin main

# Then in Cloudflare

Workers & Pages -> bold-hall-83be -> Settings -> Builds -> Connect to a repository
-> qematalamn / main -> Connect.

Trigger a deploy, then open the preview/production URL and compare it to the
live qematalamn.com pages before treating GitHub as the source of truth.
