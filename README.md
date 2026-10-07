# holy-spirit-prompts-site

The public pages for the **Holy Spirit Prompts** iOS app: a landing page, the privacy policy, the
support page, and the App Store listing copy.

## Why this is a separate repo

The App Store requires a **privacy policy URL** and a **support URL** for every app, with no
exception for apps that collect nothing. Both have to be reachable public pages — not a PDF in a
Drive folder.

The app's own repo (`holy-spirit-prompts`) is private, and GitHub Pages does not serve private
repositories on a free account. Rather than make the app source public just to host two static
files, those files live here. The app code stays private; only these pages are public.

**Nothing secret belongs in this repo.** No keys, no signing material, no Team ID, no backup files.
Assume anything committed here is permanently public, including in the commit history.

## Live URLs

Once Pages is enabled (see below):

| Page | URL |
|---|---|
| Landing | `https://blakecampbell45.github.io/holy-spirit-prompts-site/` |
| Privacy policy | `https://blakecampbell45.github.io/holy-spirit-prompts-site/privacy.html` |
| Support | `https://blakecampbell45.github.io/holy-spirit-prompts-site/support.html` |

These are the URLs that go into App Store Connect. They can be changed later without submitting a
new build, so a typo here is cheap to fix — but a URL that 404s during review is a rejection, so
**open all three in a browser before pasting them in.**

## First-time setup: enabling GitHub Pages

Once, in this repo on github.com:

1. **Settings → Pages**
2. Under *Build and deployment*, set **Source** to `Deploy from a branch`
3. Set **Branch** to `main` and the folder to `/ (root)`
4. **Save**

The first deploy takes a minute or two. Pages then rebuilds automatically on every push to `main`.
A green checkmark on the latest commit means the deploy finished; the Pages settings screen shows
the live URL once it's up.

There is no build step, no Jekyll config and no dependencies — these are plain static HTML files
and Pages serves them as-is.

## Files

| File | What it is |
|---|---|
| `index.html` | Landing page. Describes the app and links to the other two. Doubles as the App Store marketing URL. |
| `privacy.html` | The privacy policy. **Required** by the App Store. |
| `support.html` | Support page: contact address plus the questions users actually hit. **Required** by the App Store. |
| `listing.md` | Everything pasted into App Store Connect — name, subtitle, keywords, description, categories, review notes, screenshot specs. Not published; it's a reference. |

Each HTML file is self-contained: its own CSS inline, no external fonts, no JavaScript, no network
requests. They render correctly in light and dark mode and on a phone. That's deliberate — a
privacy policy that depends on a CDN is a privacy policy that can break or quietly phone home.

## Making a change

```sh
git pull
# edit the file
open index.html          # previews locally; no server needed
git commit -am "Describe the change"
git push
```

Pages redeploys on push. Hard-refresh if you see a stale version — it caches briefly.

## Keeping the claims in step

This is the part that actually matters, and the reason these files are version-controlled rather
than typed into a web editor.

**Three places make the same privacy claims, and they have to agree:**

1. `privacy.html` in this repo
2. The **Settings → About** copy in the app ("The only things that ever leave it are…")
3. `Resources/PrivacyInfo.xcprivacy` in the app repo, where every array is empty

If the app's behaviour ever changes — a new permission, anything that touches the network, any
analytics, anything stored outside the device — all three need updating together, and the App
Privacy answers in App Store Connect along with them. A privacy policy that contradicts the
privacy manifest is both a review rejection and a false statement made in your name.

**Two specific tripwires**, carried over from the app's own notes:

- **Required-reason APIs.** `NSPrivacyAccessedAPITypes` in the manifest is empty, which is true only
  as long as nothing reads a file's creation or modification date, checks free disk space, reads the
  active keyboard, or touches `UserDefaults`. `.fileSizeKey` is exempt; its siblings
  `.creationDateKey` and `.contentModificationDateKey` are not. The build stays green and the upload
  gets rejected, so there's no local signal — check deliberately when new code touches the filesystem.
- **The transcription answer.** `listing.md` records the judgment call about whether the
  cloud-transcription fallback counts as collected Audio Data. Whichever way that's answered in App
  Store Connect, `privacy.html` has to say the same thing.

## Updating the policy date

Both `privacy.html` and `support.html` carry a "Last updated" line. Change it when you change the
content — it's the only signal a reader has that the document is current.
