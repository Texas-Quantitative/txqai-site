# Contact Form Delivery — Web3Forms

The contact form ([contact.html](contact.html)) submits through
[Web3Forms](https://web3forms.com) — a static-friendly form backend. No server,
no account dashboard required; submissions are emailed to you, with spam
filtering and a stored record on Web3Forms' side.

## Getting / changing the access key

1. Go to <https://web3forms.com>.
2. Enter the email address where you want inquiries delivered.
3. Web3Forms emails you an **access key** (a UUID).
4. In [contact.html](contact.html), set that key as the value of the hidden field:
   `<input type="hidden" name="access_key" value="...">`

To change the destination email later, create a new key for the new address and
swap the value.

## How it works

- On submit, the page POSTs the form fields to `https://api.web3forms.com/submit`.
- Hidden fields: `access_key`, `subject`, `from_name`.
- `botcheck` is a hidden honeypot — bots fill it and get rejected; humans never see it.
- Same inline loading / success / error UX as before.

## Free tier

- 250 submissions / month, unlimited forms.
- Email delivery + spam protection included.
- Optional hCaptcha if spam ever becomes a problem.

## Notes

- The access key is **not a secret** — it only authorizes submissions to your form
  (it can't read past submissions). It's safe to ship in client-side code.
- For an extra instant-ping channel, an ntfy push can be added alongside Web3Forms.
