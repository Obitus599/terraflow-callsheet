# Terraflow call sheet

The page Alex opens each morning to work the day's 25 Dubai cold-call leads.

It is a static shell and nothing more: no leads, no notes, no credentials live in this repo.
Every row is fetched at open time from the Terraflow growth engine, and that request is rejected
without a key that only exists in the bookmarked URL. Opening this page without the key shows an
empty list.

It is hosted here rather than alongside the engine because Supabase rewrites `text/html` to
`text/plain` on its shared domain, an anti-phishing rule that makes a browser display the source
instead of the page.

Regenerate after any change to the engine's `call-sheet` function, which holds the canonical copy:

    curl -s "https://<project>.supabase.co/functions/v1/call-sheet?k=<key>" -o index.html
