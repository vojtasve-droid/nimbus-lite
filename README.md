# Nimbus Lite — free AI chat UI kit (HTML, CSS, JS, no framework)

A clean, **framework-free chat interface for AI apps** — vanilla HTML / CSS / JS.
Open `index.html` and it's already running. Live token streaming, code blocks with
copy, markdown, a model picker, and light/dark + 5 accent themes. No build step,
no dependencies, no npm install.

![Nimbus Lite screenshot](preview.png)

Drop it into React, Vue, Svelte, or a plain HTML page and wire your model to the
composer. It's a front-end — bring your own backend (OpenAI, Anthropic, a local model,
anything).

## Quick start

```bash
git clone https://github.com/vojtasve-droid/nimbus-lite
cd nimbus-lite
# open index.html in your browser — that's it
```

No install, no bundler. Copy the markup you need into your project and swap the demo
streamer for your API call — append tokens to the assistant message as they arrive:

```js
const res = await fetch("/api/chat", { method: "POST", body });
const reader = res.body.getReader();
const dec = new TextDecoder();
while (true) {
  const { value, done } = await reader.read();
  if (done) break;
  appendToken(dec.decode(value)); // → renders live in the UI
}
```

## What's included (free)

- 💬 Full chat layout — sidebar, conversation list, header, composer
- ⚡ Live token **streaming** with a blinking caret
- 📝 Markdown message styling + **syntax-styled code blocks** with one-click copy
- 🎛️ Model picker, typing indicator, message actions
- 🌗 Light / dark themes + 5 accent colors — recolor with **one CSS variable**
- 📱 Responsive, keyboard-friendly, accessible focus states

## Free vs. full kit

Nimbus Lite is the free front-end. The **full Nimbus kit** adds the production pieces
most kits skip:

| | Lite (this repo) | Full kit |
|---|:---:|:---:|
| Streaming, markdown, code blocks | ✅ | ✅ |
| Light/dark + 5 themes | ✅ | ✅ |
| Sources & **citations** (inline + cards) | — | ✅ |
| Collapsible **reasoning / "thinking"** block | — | ✅ |
| **Tool-call chips** for agent apps | — | ✅ |
| **File & image attachments** | — | ✅ |
| **Error + retry** states | — | ✅ |
| Docs + commercial license + updates | — | ✅ |

👉 **Get the full kit — $19:** https://sventek7.gumroad.com/l/qyxave

## License

Free to use and modify in your own projects, personal or commercial. Please don't
resell the kit itself as-is.

---

Built by [Vojta](https://sventek7.gumroad.com). Found a bug or want a feature? Open an
issue — it's just me maintaining this and I read everything.
