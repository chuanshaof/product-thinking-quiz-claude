# Product Thinking Quiz

A ten-question quiz on product thinking, built as a single self-contained HTML file.

**→ [Take the quiz](https://chuanshaof.github.io/product-thinking-quiz-claude/)**

Every question comes with the reasoning behind it, revealed the moment you answer — so
a wrong guess still teaches you something. The material comes from the Singapore
[Institute of Digital Government's Product Thinking pathway](https://www.idg.gov.sg/product-thinking/),
whose premise is that problems come before solutions, outcomes before outputs.

## What it covers

The ten questions work through the pathway's seven modules:

| # | Topic | Module |
|---|-------|--------|
| 1 | Why projects actually fail | Understanding the Problem |
| 2 | Telling an outcome from an output | Understanding the Problem / Key Takeaways |
| 3 | Picking which root cause to fix | Start with the Whys |
| 4 | The 4Cs of a problem statement | Craft a Clear Problem Statement |
| 5 | Leading vs. lagging indicators | Metrics |
| 6 | Value-Cost Ratio | Metrics |
| 7 | De-risking market risk cheaply | Assumptions and Risks |
| 8 | The 11-star framework | A Good Customer Experience |
| 9 | Nailing one problem before scaling | Understanding the Problem |
| 10 | Why compulsory services need better CX | A Good Customer Experience |

## Running it

Open `index.html` in a browser. That is the whole procedure — no install, no build step,
no server, no network requests at runtime. Cloning is optional; downloading the one file
is enough.

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `A`–`D` | Select an answer (in reading order) |
| `1`–`4` | Select an answer (by position) |
| `Enter` | Advance to the next question |

## Browser support

The page leans on `color-mix()` in CSS, so it needs a reasonably modern browser — a
current Chrome, Firefox, Safari, or Edge is fine; anything from more than a couple of
years ago may not render the gradients and borders correctly.

## How it is built

One file, roughly 900 lines: inline `<style>`, a markup shell, and inline vanilla JS.
No frameworks, no dependencies, no backend, no analytics, and nothing stored about you —
reloading the page starts the quiz over.

- **Editorial layout** — serif display type over a system sans body, warm paper palette,
  soft gradient backdrop.
- **Automatic dark mode** via `prefers-color-scheme`, and a full motion-free path under
  `prefers-reduced-motion`.
- **Keyboard driven** — `A`–`D` or `1`–`4` to answer, `Enter` to advance.
- **Accessible by default** — options are real buttons, correctness is signalled by icon
  and label rather than colour alone, and focus moves to the explanation on reveal.
- **Responsive** down to narrow phone widths.

## Editing the questions

All content lives in one `QUESTIONS` array near the top of the `<script>` block. Each
entry is self-describing:

```js
{
  question: "The 4Cs framework for writing a problem statement stands for:",
  options: [
    "Customer, Cost, Capability, Competition",
    "Clarity, Consequence, Cause, Confirmation",
    "Context, Constraint, Choice, Commitment",
    "Clarity, Collaboration, Consensus, Communication"
  ],
  answer: 1,                    // 0-based index of the correct option
  explanation: [                // one paragraph per string
    "Clarity — state the problem plainly. …"
  ],
  source: "Module 3 — Craft a Clear Problem Statement"
}
```

Add, remove or reorder entries freely — the progress rail, the counter and the results
screen all read their length from the array. Four options is the styled default, though
up to six will render.

To restyle it, the palette is a handful of CSS custom properties in the `:root` block
at the top of the file, with dark-mode overrides directly beneath.

## Deployment

GitHub Pages serves `index.html` from the root of `main`. Any push to `main` republishes
the site within a minute or two.

## Credits

Questions and explanations are drawn from the
[IDG Product Thinking learning pathway](https://www.idg.gov.sg/product-thinking/);
go there for the source material. Built with [Claude Code](https://claude.com/claude-code).
