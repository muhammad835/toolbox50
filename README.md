# Toolbox — 50 useful tools

A complete, mobile-friendly website in one `index.html` file. It includes real tools for making images, writing, coding, everyday calculations, and studying. No build step, package installation, account system, or paid API key is needed.

## Put it on GitHub

1. Create a repository, for example `toolbox50`, or open one you already have.
2. Choose **Add file → Upload files**. Upload `index.html` at the top level of the repository, then commit. You can also upload this README, LICENSE, and `.nojekyll`; the website itself needs only `index.html`.
3. Open **Settings → Pages**. Set the source to **Deploy from a branch**, choose **main** and **/ (root)**, then **Save**. Use the branch you uploaded to if its name differs.
4. GitHub will show the website address when publishing finishes, usually `https://YOUR-USERNAME.github.io/toolbox50/`.

For GitHub Free, Pages needs a public repository. Follow [GitHub's official Pages instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) if your settings look different. Upload the extracted files, not the ZIP archive itself.

## Try it before uploading

Double-click `index.html` to open it in your browser. For the complete experience, use the HTTPS website from GitHub Pages. Some browser features, including hashing and on-device AI, need a secure context and browser support.

## All 50 tools

| Create | Write | Code | Everyday | Learn |
| --- | --- | --- | --- | --- |
| Poster maker | Word counter | JSON formatter | Calculator | AI translator |
| Image resizer | Case converter | CSV ↔ JSON | Unit converter | Flashcards |
| Image compressor | Text cleaner | URL encoder/decoder | Percentage calculator | Quiz maker |
| Image cropper | Line sorter | Base64 encoder/decoder | Tip & bill splitter | Study planner |
| Image rotator | Find & replace | HTML escape/unescape | Simple budget | Focus timer |
| Meme maker | URL slug maker | Regex tester | Date difference | Quick notes |
| Gradient maker | Lorem ipsum | Password generator | Age calculator | To-do list |
| Palette generator | Markdown preview | UUID generator | Countdown | Random picker |
| Drawing board | Text difference | Text hash | Stopwatch | Dice roller |
| Avatar maker | Reading time | Color converter | Time zone converter | Typing speed test |

Search tools, filter by category, save favourites, and copy or download results. Images export as actual PNG/JPG/WebP files; gradient and palette tools also export CSS/SVG where shown.

## AI translation

The translator integrates the **on-device browser Translator API**. It does not call a paid cloud AI service or use your ChatGPT allowance. It needs a supported desktop browser, supported language pair, and a usable local model. The first translation may require a language-model download. Availability is checked in the browser, and errors appear clearly.

When browser AI is unavailable, **Open in Google Translate** opens the text and selected languages in Google's external translation service. This happens only when you click that button. This fallback does not translate inside Toolbox. See [Chrome's Translator documentation](https://developer.chrome.com/docs/ai/translator-api) for current requirements.

## Data and limits

- Image editing and text calculations run locally in the browser; uploaded files are not sent to a server.
- Notes, tasks, budgets, flashcards, study plans, and favourites save in this browser's local storage. They do not sync between devices. Clearing browser data clears those saves. Use export/download to back up important work.
- There are no trackers, ads, paid integrations, secret keys, databases, or remote fonts.
- Image uploads accept PNG/JPG/WebP/GIF up to 15 MB. Images larger than 4096 pixels are scaled down. Animation uses one frame. JPEG exports cannot keep transparency.
- Markdown preview supports a safe subset: headings, emphasis, links, simple lists, quotes, and code. Raw HTML is escaped.
- Text comparison accepts up to 400 lines per side. Regex tests have input/match limits and a worker timeout to keep the page responsive.
- Word counts and reading times are estimates, particularly for languages without spaces between words.
- Timers run while the tool is open. They are visual timers, not reliable background alarms. Changing tools stops them.
- Time zone conversion uses your browser's time-zone rules and handles missing or repeated daylight-saving times.
- Review translations, generated content, and important calculations before using them.

## Customise the code

Everything is in `index.html`:

- The `<style>` block controls colours, layout, and mobile styling.
- The final `<script>` block contains shared helpers, the 50 registered tools, and navigation.
- Every tool is registered with `addTool({ id, title, category, description, icon, render })`.
- Change the visible brand text, page `<title>`, description, or theme colours to make the site yours.

This is a working starting website. It does not include payments, monetisation, user accounts, a general AI chatbot, or guaranteed income.

## Licence

MIT. You may use, change, and share the code; see `LICENSE`.

## Verification

All 50 tool screens were opened in an isolated desktop browser without JavaScript errors. Functional browser checks exercised all 49 regular tools, including image/text downloads, CSV quoting, Unicode encoding, secure randomness, SHA hashes, date/DST calculations, saved data, and timer cleanup. The home and poster screens were checked at phone width without horizontal overflow.

Translator API wiring was checked with a deterministic test substitute, and the unsupported-browser fallback was checked. A live browser translation model was not downloaded or verified. Translation availability depends on the visitor's actual browser and language pair.
