# cbg-privacy — public web for Cozy Block Garden

**PUBLIC** GitHub Pages repo. Serves `https://cbg.chickvideogames.com/` (subdomain of the
Chick Video Games studio domain). Hosts the store-required public web files for the game
**Cozy Block Garden**.

## Contents (this is ALL that belongs here)
- `privacy-policy.html` — the public privacy policy (linked from App Store Connect + Play Console).
- `app-ads.txt` — AdMob authorized-sellers file (must match the store "developer website" domain).
- `index.html` — minimal landing linking to the policy.
- `CNAME` — `cbg.chickvideogames.com` (GitHub Pages custom domain).

## 🔒 CONFIDENTIALITY RULE — read before EVERY commit
This repo is **PUBLIC**. **NEVER** commit anything other than the public files above. In particular,
**NEVER** put here:
- App/game source code (it lives in the **private** repos `cbg-game` / `cbg-infra` / `cbg-art`).
- Any secret or internal value: Firebase config / `google-services.json` / `GoogleService-Info.plist`,
  API keys, App Check **debug tokens**, GA4 `api_secret`, service-account JSON, project ids
  (`cozy-block-garden*`), user uids, access/bearer tokens, local filesystem paths.

**Before each push, run a secret scan** and confirm only the public files changed:
```sh
grep -rniE "api[_-]?key|secret|token|password|private[_-]?key|firebase.*config|google-services|\.plist|cozy-block-garden-dev|service.account|bearer|/Users/" . --exclude-dir=.git
git status --porcelain   # only the 4 public files should ever appear
```
The privacy-policy text is **maintained** in the sibling private repo
(`../cbg-infra/web/privacy-policy.html`) and **copied** here for hosting — edit it there, then re-copy.
Keep the two in sync. (This repo is CBG-specific and lives at `codebase/cbg-privacy/` next to the other
`cbg-*` repos; future games get their own subdomain + their own public repo.)
