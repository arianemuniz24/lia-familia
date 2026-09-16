# Lia — agente da familIA
A calm multilingual voice agenda. **Product lead: Ariane Figueiredo — FIGUEIRA.**

Demo: https://lia-familia-figueira.netlify.app/

Download and extract **Lia-Source-R06.zip** before running the project. The source folders are packaged in the archive.

## What works
- Six UI/conversation languages: Portuguese, English, Spanish, Italian, French and German.
- AssemblyAI voice conversation integration; task proposals require exact source quotes. Voice-to-task reliability is still under validation: the last live integration test produced transcription/audio but no task proposal.
- Tasks are never saved by the agent: review title/date/time and explicitly save.
- Today (including overdue), Tomorrow, Coming days, Completed; edit/complete/reopen.
- Morning overview, evening review, move unfinished tasks to tomorrow.
- Browser-local persistence, local-calendar `.ics` export, concise meal conversation.
- Narrator matched to selected language, adjustable volume defaulting to 45%.

## Run
Extract the source archive if supplied as ZIP. Node.js 22+ for tests:

```sh
node --test tests/core.test.mjs tests/day-clock.test.mjs
python3 -m http.server 8805 --directory public
```
Text agenda works on a static server. Voice requires Netlify functions. Set server-only `ASSEMBLYAI_API_KEY` and `LIA_ACCESS_CODE`; never publish `.env`. Deploy `public/` and `netlify/functions/` using `netlify.toml`.

## Honest limits
Prototype for testing with example data. Not yet submitted to a hackathon. Tasks remain in this browser, with no account sync. No background push notifications: calendar reminders must be configured in the user's calendar after import. No automatic morning/night notification. The three-minute voice session sends speech, current pending tasks and ingredients to AssemblyAI only after consent. Conversation transcripts remain in tab memory. Browser data is not encrypted by this app. No real sensitive family information in demos. Food ideas require the user to check allergies and restrictions.

AI task/date extraction can be wrong; the visible draft and Save step are deliberate safeguards. A blank date must be selected before saving. Six locales have dictionary-parity tests, but voice recognition has not been accepted in all six languages. Native Brazilian Portuguese voice availability depends on the provider.

## Daily browser experience (R05)
Approved R04 logo: elongated olive wordmark, sound symbol in the i dot, uppercase descriptor with final IA in terracotta. Cyan primary actions, purple voice panel, magenta daily review accents and neutral surfaces.
Responsive layout tested at 320, 390 and 1440 CSS pixels; touch controls at least 48px tall. Search, reversible task removal, preferences persistence and daily local date rollover without redeploy. Day clock refreshes at local midnight and after tab focus/resume. No offline/PWA installation claim.

## Validation
11 automated tests pass, including local date rollover, sleep catch-up, task validation, calendar export and six-language dictionary parity. Browser create/remove/undo/reload/search verified. No claim of fully accepted voice task creation; further live voice testing is required before final competition submission.

## License
MIT for project source. Original logo generated for this project.
