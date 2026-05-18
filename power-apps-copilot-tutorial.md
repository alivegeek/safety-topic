# Power Apps Copilot Tutorial — Safety Topic Briefer

Use SafetyTopic as a tutorial project for the Power Apps **"Start with Copilot"** feature.
The first Copilot box wants a description of the *app and its data* — it generates a
Dataverse table plus screens from that description.

## Primary prompt

Paste this into the Copilot "describe your app" box:

> Build an app called **Safety Topic Briefer** that helps team leads pull a quick
> safety topic to read aloud at the start of a meeting. Create a table named
> **Safety Topics** with these columns: Title (text), Category (choice: Chemicals &
> Hazardous Materials, Driving & Travel Safety, Ergonomics & Body Mechanics, Fire &
> Emergency Safety, Health & Wellness, Hygiene & Environment, Personal Protective
> Equipment, Safety Culture, Security & Personal Safety, Walking & General Safety),
> Source (choice: OSHA, DOE, NIOSH), Source Reference (text), Duration (text, e.g.
> "1-2 min"), Summary (multiline text), Key Points (multiline text), Did You Know
> Stat (multiline text), Discussion Prompt (multiline text). The app should let a
> user browse all topics, filter by Category, search by keyword in Title and
> Summary, and open a topic to see a clean read-aloud view with the summary, key
> points, stat, and discussion prompt. Add 5–10 sample safety topics so I can test
> it.

## Why it's shaped this way

- Power Apps Copilot builds best when you hand it the **table schema + a couple of
  behaviors**, not a feature wishlist. The column list maps directly to the repo's
  `topics-data.js` structure.
- `key_points` is an array in the original — Dataverse has no list type, so it's
  collapsed to a **multiline text** column (one point per line). Mention that if
  Copilot asks.
- Asking for sample data lets you click through screens immediately, which is the
  point of the tutorial.

## Good follow-up prompts (after the app generates)

- "Add a button on the detail screen labeled **Get Random Topic** that opens a
  random record."
- "Add a gallery screen grouped by Category."
- "Make the detail screen read-only and formatted like a printable handout."

## Source project

[alivegeek/safety-topic](https://github.com/alivegeek/safety-topic) — zero-dependency
static site serving bite-sized safety briefs for meeting openers. 50 topics across
10 categories, curated from OSHA / DOE / NIOSH public-domain content.
