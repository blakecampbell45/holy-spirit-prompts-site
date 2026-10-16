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

Expanded after the 1.0 submission drew **Guideline 2.1 — Information Needed**, the routine request
Apple sends to developer accounts with limited review history. It is not a finding against the app;
it asks for a screen recording plus five written answers. Apple asked for that information to live
here permanently, "for reference on future submissions", so this is now the long version rather than
the two-feature note it started as.

The App Review Notes field caps at **4,000 characters**. What follows is 3,909. The fuller reply
sent to Resolution Center is below it and does not have to fit.

```
PURPOSE AND AUDIENCE
Holy Spirit Prompts is a private journal for Christians who want to write down a spiritual impression when it occurs and look back later to see whether and how it came about. Capture by text, photo, video or voice; tag it; note the scripture it came with; mark it Active, Future, Fulfilled or Discarded. The app then surfaces other entries sharing the same tags or verses, so a connection between entries written years apart is found rather than remembered. A second, simpler section holds "God Stories", short accounts of things that already happened. Single-user by design: no social component, no sharing between users, no community features.

NO ACCOUNT, NO PURCHASES, NO SHARED CONTENT
No sign-in is required and no credentials exist. There are no accounts of any kind, so there is no registration, login or account-deletion flow. There is no in-app purchase and no paid content. Everything a person writes stays on their own device and is never shared with or visible to another user, so there is no user-to-user content and no reporting or blocking mechanism is required.

ACCESSING THE MAIN FEATURES
No setup and no sample files are needed. The app opens to the Library tab with everything available.
- Library: all entries, searchable and filterable. "+" captures a new one.
- Open an entry: tags and scripture references are chips; tapping one shows every other entry filed under it. "Related Promptings" lists entries sharing its tags or verses.
- TRANSCRIPTION: open an entry with a voice recording, use the Transcript section, tap "Transcribe Audio". It runs on the device and iOS requires BOTH Siri and Dictation enabled: Settings > Apple Intelligence & Siri, and Settings > General > Keyboard > Enable Dictation. With either off, the app reports it and offers to send that one recording to Apple instead. That dialog is expected behaviour, not a failure.
- Related tab: browse by tag or by scripture passage.
- Stories tab: God Stories.
- Settings: "Export All Data" writes one backup file and hands it to the share sheet, uploading nowhere. "Restore from Backup" reads one back, adding entries and never overwriting. Export first to produce a file to test restore with.
Camera, microphone, photo library and speech permissions are each requested only on first use of that feature. The app works without granting any.

EXTERNAL SERVICES
None. No backend, no analytics, no advertising, no authentication provider, no payment processor, no AI service, and zero third-party dependencies or SDKs. Data is stored on the device with SwiftData. The app makes no network requests of its own and contains no networking code.
Apple frameworks reaching beyond the app's own storage: Photos/PhotoKit (attachments are stored as references to the person's own library, not copies); Speech/SFSpeechRecognizer (on-device by default; a single recording goes to Apple only if the person taps "Send to Apple for Transcription"); CryptoKit and CommonCrypto (only to encrypt an exported backup when a passphrase is chosen).

REGIONAL DIFFERENCES
None. The app functions consistently in all regions, with no region-gated content, no region-specific service and no geographic restriction. Interface is English only. On-device speech recognition varies by the languages a device supports rather than by region, and where unavailable the same optional fallback above applies.

REGULATED INDUSTRY AND THIRD-PARTY MATERIAL
Neither applies. The app contains NO Bible text: no translation is bundled, licensed, displayed or retrieved. It recognises the names and standard abbreviations of the books of the Bible ("John", "Jn", "1 Cor") so a reference a person types becomes a link between their own entries, and stores only that reference, being the book name and chapter and verse numbers. Verse content is never stored or shown. Any words beside a reference were written by the person using the app.
```

`3,909 / 4,000 characters`

Four claims in here are load-bearing, and each was checked against the code rather than assumed:

- **No third-party dependencies.** `XCRemoteSwiftPackageReference` appears zero times in
  `project.pbxproj`. The `dependencies:` entries in `project.yml` are target-to-target.
- **No networking code.** There is no `URLSession` or equivalent anywhere in the source. The one
  path off the device is `SFSpeechRecognizer`'s cloud fallback, which Apple's own framework makes.
- **No Bible text.** `bookAliases` is a list of book *names* and abbreviations;
  `ScriptureReference` stores `rawText`, `book`, and integers. No translation is bundled, and
  `Resources/` contains only assets, the Info.plist, the privacy manifest and preview/test seeds.
  This is the answer to the "protected third-party material" question and it has to stay true — do
  not bundle verse text without revisiting it.
- **No user-to-user content.** Nothing a person writes is shared with or visible to anyone else,
  which is why no reporting or blocking mechanism is required under 1.2.

### The Resolution Center reply

Sent in response to the 2.1 request. Same substance, longer form, and it opens with the screen
recording since that is what the request leads on.

```
Thank you for reviewing Holy Spirit Prompts. The requested information follows.

1. SCREEN RECORDING

A screen recording captured on a physical iPhone running the latest iOS is attached. It begins with launching the app and shows the typical user flow.

Regarding the specific flows listed:
- There is no account registration, login, or account deletion. The app has no accounts of any kind, no sign-in, and no server, so these flows do not exist.
- There is no user-generated content in the sense the guideline addresses. Everything a person writes is stored only on their own device and is never shared with, visible to, or transmitted to any other user. There is no feed, no social component, and no user-to-user interaction, so no content reporting or blocking mechanism is required.
- There is no paid content and no in-app purchase. The app is free in full.

2. PURPOSE AND TARGET AUDIENCE

Holy Spirit Prompts is a private journal for Christians who want to write down a spiritual impression at the moment it occurs, and look back later to see whether and how it came about.

The problem it solves: these impressions are fleeting and usually get lost. Kept in a general notes app they become an undifferentiated list, with no way to connect something written today to something written two years ago, and no way to record how it turned out.

The value it provides: capture in whatever form is fastest, by text, photo, video, or voice. Tag it and note the scripture it came with. Mark it Active, Future, Fulfilled or Discarded as the outcome becomes clear. The app then surfaces other entries sharing the same tags or scripture references, so a connection between two entries written years apart is found rather than remembered.

A second, deliberately simpler section holds "God Stories": short written accounts of things that have already happened.

Target audience: individual Christians keeping a personal record. The app is single-user by design, with no social component, no sharing between users, and no community features.

3. SETUP AND ACCESS INSTRUCTIONS

No setup is required and no credentials exist. There is no account, no sign-in, no paywall, and no server. The app opens directly to the Library tab with every feature available immediately. No sample files are needed.

- Library tab: all entries, searchable, filterable by status. The + button opens capture, where you can type a note, add tags, add a scripture reference, attach a photo or video, or record audio.
- Opening an entry: tags and scripture references appear as chips; tapping one shows every other entry filed under it. The status control sets Active, Future, Fulfilled or Discarded. "Related Promptings" lists other entries sharing its tags or verses.
- Transcription: open any entry that has a voice recording and use the Transcript section, then "Transcribe Audio". This runs on the device and requires BOTH Siri and Dictation to be enabled on the test device: Siri at Settings > Apple Intelligence & Siri, and Dictation at Settings > General > Keyboard > Enable Dictation. If either is off, the app reports the error and offers to send that one recording to Apple to be transcribed instead. That dialog is expected behaviour, not a failure.
- Related tab: browse everything filed under a given tag or scripture passage.
- Stories tab: God Stories, with + to add one.
- Settings tab: "Export All Data" writes a single backup file and hands it to the iOS share sheet; the app uploads it nowhere. "Restore from Backup" reads such a file back, adding entries and never overwriting existing ones. To test restore, use Export All Data first to produce a file. "Recordings on This Device" lists the audio files the app stores.

Permissions for camera, microphone, photo library, and speech recognition are each requested only when the relevant feature is first used. The app is fully usable without granting any of them.

4. EXTERNAL SERVICES, TOOLS, AND PLATFORMS

The app uses no third-party services of any kind. It has no backend, no analytics, no advertising, no authentication provider, no payment processor, and no AI service. The project has zero third-party dependencies: no Swift packages and no SDKs. All data is stored on the device using SwiftData.

The app makes no network requests of its own and contains no networking code.

The only Apple frameworks it uses that involve anything beyond the app's own storage are:
- Photos (PhotoKit), for displaying photos and videos the person selects from their own library and saving ones captured in the app back into it. Attachments are stored as references to the person's library rather than copies.
- Speech (SFSpeechRecognizer), for transcribing voice recordings. This runs on the device by default. If on-device recognition is unavailable, the app shows a dialog and the person may choose "Send to Apple for Transcription", which sends that single recording to Apple's speech recognition service. It is never sent automatically, and nothing else is ever transmitted.
- CryptoKit and CommonCrypto, used only to encrypt an exported backup file when the person chooses a passphrase.

5. REGIONAL DIFFERENCES

The app functions consistently across all regions. There is no region-gated content, no region-specific service, and no geographic restriction of any feature. The interface is English only.

The one capability that varies is on-device speech recognition, which depends on the languages a given device supports rather than on the person's region. Where it is unavailable, the app offers the same optional, explicitly confirmed fallback described above.

6. REGULATED INDUSTRY AND PROTECTED THIRD-PARTY MATERIAL

The app does not operate in a regulated industry and includes no protected third-party material.

On scripture specifically: the app contains no Bible text. No translation is bundled, licensed, displayed, or retrieved. It recognises the names and standard abbreviations of the books of the Bible, such as "John", "Jn", and "1 Cor", so that a reference a person types can become a link between their own entries. It stores only the reference itself, which is the book name and the chapter and verse numbers. Verse content is never stored or shown. Any words appearing next to a reference were written by the person using the app.
```

`6,292 characters`

## Screenshots

iPhone 6.9" only — `TARGETED_DEVICE_FAMILY` is `"1"`, so no iPad set is needed.

- **1320 × 2868** or **1290 × 2796**, portrait, 1–10 images
- Capture in the iPhone 17 Pro Max simulator so dimensions come out exact
- Seed the simulator with realistic content first; a library of two test entries reads as unfinished

Lead with what's distinctive: a prompting with tags and a scripture chip, the Related tab, a
transcript, and the God Stories list.
