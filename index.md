# VirtuLayer Privacy Policy

**Effective date:** October 9, 2026  
**Last updated:** October 9, 2026  
**Developer:** SchmidtWorks  
**Contact:** schmidtworksdeveloper@gmail.com

## 1. Scope and purpose

VirtuLayer is an independently developed Chrome and Microsoft Edge extension that accelerates supported contact-record sections in Virtuous CRM. This policy describes the information processed by VirtuLayer version 0.1.2, including its temporary prefetch cache and cleanup functions.

VirtuLayer works inside an existing authenticated Virtuous session. It does not create an independent CRM account, bypass Virtuous access controls, or grant additional permissions.

## 2. Information processed

While a user views supported Virtuous contact records, VirtuLayer may retrieve and temporarily process information available to that user, including:

- Contact identifiers and other personal information in supported CRM responses.
- Gift transactions, donation histories, and pledge information.
- Contact notes, note text, authors, dates, and related metadata, which may include personal communications.
- Active tasks and reminders.
- Request addresses and parameters needed to associate responses with the appropriate CRM section and contact.

The extension does not independently request passwords, payment card details, or authentication credentials. The authenticated browser session is used to make requests to Virtuous.

## 3. How information is used

VirtuLayer prefetches contact Notes, Gifts, active Tasks, and Pledges, then reuses matching responses to improve loading performance. Notes may be loaded progressively in groups of 10, 30, and 100.

For accelerated Notes lists, a single exceptionally long note body may be replaced with a placeholder in the temporary response presented to the interface. The original note stored in Virtuous is not changed.

The extension processes this information for CRM performance improvements only, not advertising, profiling, lending, or creditworthiness assessments.

## 4. Temporary in-memory caching

In version 0.1.2, prefetched CRM response bodies are kept in a JavaScript memory cache associated with the current loaded page document. They are **not written by this version to** `sessionStorage`, `localStorage`, IndexedDB, or extension storage.

The cache uses these validity periods:

- Gifts, active Tasks, and Pledges: **2 minutes**.
- Contact Notes: **5 minutes**.

The cache holds at most **20 entries** and limits each cached response to **2 MiB** measured as UTF-8 text. Expired entries are removed when accessed or during a periodic check approximately every 15 seconds.

The cache is cleared when the page document ends, when the user leaves the supported contact-record area, or when the extension detects certain sign-out, sign-in, and authentication-failure events. The extension also prevents results from requests started before a detected cache reset from being inserted into the new cache.

A full-page navigation or reload does not preserve this in-memory response cache. Ordinary browser and Virtuous application behaviour may independently retain information outside VirtuLayer's cache. Clearing a JavaScript cache does not guarantee immediate erasure of all memory copies by the browser.

## 5. Earlier-version storage cleanup

Version 0.1.2 attempts to remove known Virtuous-prefetch keys previously written to the website's `sessionStorage` by supported earlier script versions. It does not intentionally remove unrelated website storage. This cleanup may be limited by the browser's access and storage lifecycle.

## 6. Data transmission, sharing, and analytics

VirtuLayer sends the supported prefetch requests directly to the Virtuous CRM website through the user's existing authenticated session. These requests may include contact identifiers and request parameters needed to retrieve records.

The reviewed version does **not** send CRM responses, donor information, notes, gifts, or usage telemetry to SchmidtWorks, a separate analytics provider, or an advertising network. SchmidtWorks does not sell this CRM data or use it for unrelated purposes. Virtuous and the organization operating the CRM remain responsible for their own platform operations and data practices.

Debugging messages may appear in the local browser developer console; the extension does not automatically send them to SchmidtWorks.

## 7. Security and permissions

Version 0.1.2 operates on `https://app.virtuoussoftware.com/*` and executes a content script in the webpage's main JavaScript context to integrate with Virtuous's request-handling code. Page scripts on that origin may interact with that execution context. The response cache is not separately encrypted by VirtuLayer.

The extension makes authenticated, read-oriented requests and is designed not to alter the underlying Virtuous donor records, gift transactions, or permissions. Users should follow their organization's security requirements for CRM access, shared devices, and sensitive records.

## 8. Retention, deletion, and user controls

VirtuLayer does not maintain an external CRM-data database. Its version 0.1.2 response cache expires and is cleared as described above. Closing or reloading the relevant page ends that document's in-memory cache. Uninstalling the extension prevents its further processing but does not delete records held by Virtuous or necessarily remove data created by older versions in site storage.

Users can manage browser extensions through their browser settings. Requests to access, correct, or delete CRM information should be directed to the organization responsible for that information.

## 9. Contact inquiries

Questions about VirtuLayer or its privacy practices can be sent to **schmidtworksdeveloper@gmail.com**. Information voluntarily provided in support emails will be used to respond to the inquiry and manage related correspondence.

## 10. Children

VirtuLayer is intended as a professional CRM productivity tool, not as a service directed at children. Information about minors that may exist in authorized CRM responses is subject to the relevant organization's controls.

## 11. Policy changes

SchmidtWorks may revise this policy as VirtuLayer changes. The most recent version and its update date will be published on this page. Material changes in data practices should also be reflected in the browser-store disclosures.

## 12. Independent development

VirtuLayer is developed independently by SchmidtWorks and is not affiliated with, endorsed by, or officially supported by Virtuous Software.
