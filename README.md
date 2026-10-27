# chat-card-kit

A small, dependency-free renderer for reply cards shown in a chat's visual card tool.
A card is a container, a JSON data block and one pinned script tag:

```html
<div class="kc" id="kc" data-kit="2">Loading the card…</div>
<script type="application/json" id="cd">{"status":["ok","Done","Example"],"move":{"steps":[["Check the result","why it matters"]]}}</script>
<script src="https://cdn.jsdelivr.net/gh/kkellykkaze/chat-card-kit@COMMIT/kit.js" integrity="sha384-HASH" crossorigin="anonymous"></script>
```

## Using it

- Always pin a full 40-character commit and its integrity hash; never a branch or tag.
- One card per page: the ids `kc` and `cd` are fixed.
- The data is strict JSON. Write every `<` inside a string as `\u003c`.
- Data keys: `status` `[tone, chip, text]`; `blocks` (points, metrics, progress, compare, rows, timeline, detail, note);
  `move` (`steps`, `ask`); `side` (`next`, `nv`, `wait`, `opus`, `allow`). Points and steps take a string or
  `[headline, detail]`.
- Button text is sent with a `(card) ` prefix; buttons whose label reads as an approval phrase are refused.

## Releasing a new version

1. Build `kit.js` from the source page with the builder script, kept outside this repo (mechanical, byte-for-byte repeatable).
2. Commit, push, and note the full commit id.
3. Hash the exact file served at that commit: `openssl dgst -sha384 -binary kit.js | openssl base64 -A`.
4. Update the commit and hash in the card template together.

Personal project; no support.
