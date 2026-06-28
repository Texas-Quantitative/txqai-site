# Contact Form Delivery — ntfy.sh

The contact form ([contact.html](contact.html)) sends each submission as a push
notification via [ntfy.sh](https://ntfy.sh) — no backend, no account, no billing.

## How it works

On submit, the page POSTs a plain-text body (Name / Email / Company / Message)
to a topic URL. Anyone subscribed to that topic receives the notification.

**Topic:** `txqai-leads-j9jhe5r2cdkfcb77`

## Receiving inquiries

Subscribe to the topic with any of:

- **Mobile:** install the ntfy app (iOS / Android), add topic `txqai-leads-j9jhe5r2cdkfcb77`
- **Browser:** open <https://ntfy.sh/txqai-leads-j9jhe5r2cdkfcb77>
- **Desktop:** the ntfy web app or CLI (`ntfy subscribe txqai-leads-j9jhe5r2cdkfcb77`)

## Important limitations (this is a stopgap)

- **The topic is visible in the page source.** Because this is a static site,
  the topic lives in the client-side code served to every visitor. An unguessable
  name stops random enumeration, but anyone who views source on the contact page
  can find the topic — and then read submissions or post spam to it. Treat it as
  low-secrecy.
- **No durable record.** ntfy is a push, cached ~12h. There is no inbox/dashboard
  archive — if no subscriber sees it within the cache window, the inquiry is lost.
- **No spam protection** beyond the browser's required-field validation.

## When to graduate off this

For real lead capture, move to one of:

- A small serverless function (e.g. Cloudflare Worker) that holds an ntfy
  **access token** and posts to a private, auth-protected topic — keeps the topic
  out of client code.
- A form backend with storage + email (Formspree, Basin, Web3Forms, etc.).

## Changing the topic

Edit [contact.html](contact.html) and replace both occurrences of
`https://ntfy.sh/txqai-leads-j9jhe5r2cdkfcb77` (the form `action` and the
`fetch(...)` call), then update the topic referenced in this file.
