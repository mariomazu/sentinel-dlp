# Sentinel DLP — Privacy Policy

**Effective date:** June 4, 2026
**Extension:** Sentinel DLP (Chrome Web Store)
**Contact:** mazuniga11@gmail.com

## Summary

Sentinel DLP runs entirely on your device. It reads the text you are about to send through supported AI chat tools and webmail providers, checks that text for patterns indicating sensitive information, and warns you (or blocks the send) before the text leaves your browser. **No prompts, emails, detected values, or other user content are ever transmitted to us, to any third party, or to any external server by this extension.**

## What data the extension reads

To do its job, Sentinel must look at the text you type into supported composers, on these hosts only:

- AI chat tools: `chatgpt.com`, `chat.openai.com`, `claude.ai`, `gemini.google.com`, `copilot.microsoft.com`, `www.bing.com/chat`
- Webmail: `mail.google.com`, `outlook.live.com`, `outlook.office.com`, `outlook.office365.com`, `mail.yahoo.com`

On those hosts, Sentinel reads only the contents of the active prompt/composer/email body and the email subject line (where applicable). It does not read other parts of those pages, and it does not run on any other website.

The data the extension processes may include, by category:

- **Personally identifiable information** (e.g., social security numbers, dates of birth, phone numbers, addresses, email addresses)
- **Health information** (e.g., medical record numbers, provider IDs, ICD-10 diagnosis codes)
- **Financial and payment information** (e.g., credit card numbers, IBANs, bank routing numbers)
- **Authentication information** (e.g., API keys, tokens, passwords, private key material)
- **Personal communications** (the text of the email or prompt you are about to send)

Processing means: scanning the text with locally-stored regular expressions to determine whether sensitive content is present. The scan happens entirely inside your browser, in the extension's content script.

## What data the extension stores

The extension stores the following on your device:

1. **Your settings** (which detection categories are enabled, any custom regex rules you have added, the enforcement mode) — stored in `chrome.storage.sync`, which Chrome may sync across your own signed-in Chrome instances under your Google account. We never receive this data.
2. **An event log** — stored in `chrome.storage.local`, never synced. Each entry records: a timestamp, the surface name (e.g., "ChatGPT"), the URL of the page, your action ("cancel", "proceed", or "blocked"), and for each finding the rule name, category, severity, and a **masked** representation of the matched text (first two and last two characters only). **Raw sensitive values are never written to the log.**
3. **Administrator policy** (only if your organization deploys Sentinel via Chrome enterprise group policy) — read from `chrome.storage.managed`. This is set by your IT administrator, not by you, and not by us.

You can clear the event log at any time from the toolbar popup or the options page, and you can export it as JSON or CSV for your own records.

## What data we collect

**We do not collect any data.** The extension makes no outbound network requests of its own. It does not send analytics, telemetry, crash reports, usage statistics, or any other information off your device. We — the publisher — never see your prompts, emails, settings, event log, or any sensitive content the extension detects.

## How we share data

We do not share user data, because we do not have any user data to share.

Specifically, we certify that:

- We **do not sell** user data to third parties.
- We **do not transfer** user data to third parties for purposes unrelated to the extension's single purpose.
- We **do not use or transfer** user data to determine creditworthiness or for lending purposes.

## Permissions and why they exist

| Permission | Purpose |
|---|---|
| `storage` | Persist your settings and the local event log; read managed (enterprise) policy if your organization deploys one. |
| `activeTab` | Let the toolbar popup act on the tab you are currently viewing (open settings, show recent events for that tab). |
| `scripting` | Re-inject content scripts on already-open tabs after the extension updates, so you don't have to reload tabs. |
| Host permissions on the listed AI chat and webmail sites | Run the detection content script in the composer on those sites. The extension does not access any other sites. |

## Children

Sentinel DLP is not directed at children under 13 and we do not knowingly process information from them.

## Changes to this policy

If we ever change this policy materially, we will update the "Effective date" at the top and update the version of the extension that points to this URL.

## Contact

Questions about this policy: **mazuniga11@gmail.com**
