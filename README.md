# chat-card-kit

A small, dependency-free renderer for reply cards shown in a chat's visual card tool.
A card is a container, a JSON data block and one pinned script tag:

```html
<div class="kc" id="kc" data-kit="2">The card did not draw. Reply <b>text</b> to get it as plain text.</div>
<script type="application/json" id="cd">{"status":["ok","Done","Example"],"move":{"steps":["Check the result"]}}</script>
<script src="https://cdn.jsdelivr.net/gh/kkellykkaze/chat-card-kit@COMMIT/kit.js" integrity="sha384-HASH" crossorigin="anonymous"></script>
```

Load it pinned to a full commit and with its integrity hash. Personal project; no support.
