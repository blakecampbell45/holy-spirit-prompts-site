# App Store listing copy

Everything that gets pasted into App Store Connect, kept here so changes have a history and
so the claims stay in step with `privacy.html` and the app's own Settings → About screen.

Character counts are Apple's limits. Re-count after editing — App Store Connect truncates
silently in some fields rather than refusing the paste.

---

## App name

```
Holy Spirit Prompts
```

`19 / 30 characters` · Must be unique across the whole App Store.

## Subtitle

```
Promptings and God stories
```

`26 / 30 characters` · Shows under the name in search results and on the product page.

## Keywords

```
prayer,journal,devotional,scripture,bible,verse,faith,testimony,quiettime,discernment,notes,voice
```

`97 / 100 characters` · Comma-separated, no spaces after commas — a space costs a character.

Words already in the app name and subtitle are indexed automatically, so "prompts", "prompting",
"holy", "spirit", "god" and "stories" are deliberately absent. Don't add them back; it wastes the
budget. Singular forms generally cover plurals.

## Promotional text

```
Everything stays on your phone. Capture a prompting by text, photo, video or voice — then watch the tags and verses connect it to what you wrote months ago.
```

`155 / 170 characters` · Editable at any time **without submitting a new build**, which makes this
the line to change seasonally or to highlight something new. The description is not editable that
way outside of a release.

## Description

The first three lines are all that shows before someone taps "more", so they carry the weight.

```
Holy Spirit Prompts is a quiet place to write down what you sense, and to keep what God has done.

Capture a prompting the moment it comes: a few words, a photo, a video, or your own voice. Tag it, note the verse it came with, and let it sit.

Everything stays on your phone. No account, no subscription, no server.

CAPTURE IT HOWEVER IT COMES
• Type a note, take a photo, film a video, or record your voice
• Import an audio file you already have
• Transcribe a recording on your device, so you can find what you said later

TRACK IT TO AN OUTCOME
• Mark a prompting Active, Future, Fulfilled or Discarded
• Add a note when it comes to pass
• Discarded promptings stay in your library but stop surfacing

SCRIPTURE THAT LINKS ITSELF
• Type a reference and it becomes a way into every other prompting that shares the passage
• Mention a verse in your note and the app quietly offers it
• It knows full book names and abbreviations, and stays silent on words that are also ordinary English, so a note about a new job doesn't turn into the book of Job

SEE WHAT CONNECTS
• The Related tab lists everything filed under a tag or a passage
• Each prompting surfaces others sharing its tags and verses, with a shared verse weighted above a shared tag
• Something from two years ago surfaces as readily as last week's — age breaks ties, it never buries

GOD STORIES, KEPT SIMPLE
A separate tab for short accounts of what God has done. A date, a few sentences, and one photo if you want it. No tags, no status, nothing to track. You write it once.

YOURS, AND ONLY YOURS
• Nothing to sign in to
• No analytics, no tracking, no ads
• Photos and videos are referenced from your own library, never duplicated
• Export everything to a single file whenever you like, protected with a passphrase if it's going somewhere you don't control
• Restoring adds rather than overwrites, so an old backup can only give things back

The only two things that ever leave your phone are a backup you export yourself, and a single recording you choose to send to Apple to be transcribed. Nothing else, ever.
```

`~1,900 / 4,000 characters`

Note what this deliberately avoids: it never calls the app simple, minimal, beautiful or powerful.
Describing real behaviour is also what keeps **Guideline 4.2 (Minimum Functionality)** from being
raised — 4.2 catches apps that amount to one text field, and the way to never meet it is to be
specific about what the app actually does.

---

## Categories

| | |
|---|---|
| Primary | **Lifestyle** |
| Secondary | **Reference** |

iOS has no Religion category — that's Google Play. Devotional apps sit under Lifestyle, and
Reference is the defensible second. Productivity would also pass review but competes against a
far harder category.

## URLs

| Field | Value | Required |
|---|---|---|
| Privacy policy URL | `https://blakecampbell45.github.io/holy-spirit-prompts-site/privacy.html` | Yes |
| Support URL | `https://blakecampbell45.github.io/holy-spirit-prompts-site/support.html` | Yes |
| Marketing URL | `https://blakecampbell45.github.io/holy-spirit-prompts-site/` | No |

Confirm these resolve before pasting them in — a privacy policy URL that 404s is a rejection, and
it's the kind that costs a full review cycle. All three can be changed later without a new build.

## Age rating

Expect **4+**. Nothing in the app triggers a rating concern: no user-generated content shared
between people, no web view, no ads, no purchases, no gambling, no unrestricted web access.

## App privacy

**Data Not Collected**, across every category. There is no server, no account and no analytics,
and `PrivacyInfo.xcprivacy` in the app repo makes the same claim.

The one judgment call is the cloud-transcription fallback. Apple asks about data collected by you
*or your third-party partners*; a recording sent to Apple's speech service is the user moving their
own data through a platform API rather than you collecting anything, and most apps using
`SFSpeechRecognizer` declare nothing for it. If you'd rather be conservative, declare **Audio Data**
as collected, not linked to identity, used for App Functionality.

Either answer is defensible. The inconsistent one is declaring it here and not in `privacy.html`,
so if you change this, change that too.

## App Review notes

```
No sign-in is required — the app has no accounts, so no demo credentials are needed.

Two features are worth pointing out because they aren't obvious from tapping around:

BACKUP AND RESTORE (Settings tab)
"Export All Data" writes a single file and hands it to the iOS share sheet. The app makes
no network request of its own to do this and uploads nothing anywhere. "Restore from Backup"
reads such a file back; restoring adds by default and never overwrites existing entries.

TRANSCRIPTION (open any prompting with a voice recording, Transcript section)
Transcription is triggered manually and runs on-device. iOS requires BOTH Siri and Dictation
to be enabled for on-device recognition:
  • Siri — Settings > Apple Intelligence & Siri
  • Dictation — Settings > General > Keyboard > Enable Dictation
With either disabled, the app reports the error and offers to send that one recording to
Apple's servers to transcribe instead. That prompt is the expected behaviour, not a failure.
```

The Siri-and-Dictation note is there because a reviewer with Siri off will hit
`kLSRErrorDomain` 201 and may read a working feature as broken.

## Screenshots

iPhone 6.9" only — `TARGETED_DEVICE_FAMILY` is `"1"`, so no iPad set is needed.

- **1320 × 2868** or **1290 × 2796**, portrait, 1–10 images
- Capture in the iPhone 17 Pro Max simulator so dimensions come out exact
- Seed the simulator with realistic content first; a library of two test entries reads as unfinished

Lead with what's distinctive: a prompting with tags and a scripture chip, the Related tab, a
transcript, and the God Stories list.
