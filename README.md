# Designers in Code

**A designer working inside the dev environment.**

This repo holds a talk and the checklist that goes with it. The talk is about a designer pulling a repo from GitHub, fixing a UI bug with Claude Code, and opening a pull request, instead of writing a ticket and waiting. The checklist is how to start doing the same thing with your own design team, this month, without touching production code.

Fork it. Present it to your team. If you improve it, send me a pull request. That would be a nice first one.

---

## What is in here

| File | What it is |
|---|---|
| `designer-in-dev-env.html` | The talk. One self-contained HTML file. Open it in a browser, press F for full screen, use the arrow keys. No internet needed. |
| `README.md` | This file. The checklist starts below. |

The deck is built as a web page, not a PowerPoint. It runs offline, it scales to any screen, and it has two visual modes: a Figma-style design canvas for the opening, and a code-editor canvas for the rest. The moment one turns into the other is the point of the talk.

### Presenting the deck

| Key | What it does |
|---|---|
| Arrow keys, space | Next and previous slide. On slides that reveal in steps, space reveals the next step first. |
| Click | Same as space on reveal slides. |
| 1 to 5 | On the flow slide, jump to a move: repo, branch, commit, pull request, merge. |
| 1 to 6 | On the demo slide, tick a step. |
| L | Switch every editor slide between light and dark. Use this at the tech check. Whatever you choose is remembered. |
| Shift + \ or Cmd/Ctrl + \ | Hide all the interface chrome. Same shortcut as hiding the UI in Figma. |
| F | Show the fun fact on the current slide, if it has one. |
| Q | Hidden slide: the cheat sheet, for Q&A. |
| B | Hidden slide: an offline walkthrough of the demo, for when the wifi dies. Esc goes back to the demo slide. |

Two things to do before you present:

1. Replace the QR codes. The two QR codes at the end point at my repo and my LinkedIn. Search the HTML for `Designers-In-Code` and `linkedin.com/in/ridin` and swap in your own links, then regenerate the codes with any QR tool and paste the SVG in.
2. Replace the byline. Search for `Ridin Dinesh` and put your name in.

If you enable GitHub Pages on your fork and rename the deck to `index.html`, the talk is live at a URL you can share.

---

## The checklist

Everything the talk says, in the order you would actually do it.

### 0. Git is not GitHub

You will hear both words in the same sentence and nobody will tell you they are different.

- **Git** is a free tool that lives on your laptop. It watches a folder and saves versions of it. It works offline, with no account and no website. Think of it as the camera.
- **GitHub** is a website. It hosts the project so everyone works from one copy, and adds the people: access, comments, reviews, approvals. Think of it as the shared album everyone can comment on.

You will use Git constantly and almost never notice, because VS Code turns it into buttons.

### 1. You already know this workflow

| In Figma | In GitHub |
|---|---|
| The Figma file | the repository |
| Duplicating a page to try something | a branch |
| A named version in history | a commit |
| Marking it ready for review, with comments | a pull request |
| Publishing to the team library | merging to main |

Same instinct: work on a copy, show it to someone, get a second pair of eyes, then publish. Only the canvas changed.

### 2. Week one, in the browser. Read only.

- Ask for read access to one repo. Any repo. Read access cannot break anything.
- Sign in at github.com and just read for a few days: the files, the open pull requests, and especially the comments on them. That is where you learn how the team talks.
- Install VS Code. It is the editor, and the only app you will install.
- Install Claude Code inside VS Code, or whichever coding assistant your company allows. The rest of this guide assumes Claude Code.

### 3. Week two. A repo for your design team.

Do not start on product code. Start with each other.

- Put your next prototype, internal tool or design-system experiment on GitHub as a repo your design team owns.
- Invite two other designers as collaborators.
- Agree three rules before anyone touches it:
  1. **One branch, one fix.** Two bugs means two branches. A branch that does one thing gets reviewed in minutes. A branch that does five things sits for a week.
  2. **Name it for a stranger.** What kind of change, a slash, what it touches. `fix/card-padding`, `update/button-hover`. Never `final-final-v2`.
  3. **Open the pull request the same day.** A branch left alone for a week slowly stops matching main.
- And one rule under all of those: **never edit main directly.** Main is where everyone lives.

This is real GitHub. You will branch, commit, review each other and merge. Nothing you do can break anything that matters, and after two weeks the flow feels normal.

### 4. Your first pull request, move by move

1. **Repo.** The one file everyone works from. On github.com.
2. **Branch.** Your own copy, safe to break. In VS Code, bottom-left corner, click the branch name, create a new one.
3. **Commit.** A named version you can return to. In VS Code, the Source Control panel. Write the message like a changelog line: `Fix card padding to 16px`.
4. **Pull request.** A design review, with a diff. Push, then open the pull request on github.com. The green button.
5. **Merge.** Your copy becomes the real thing. After someone approves, on github.com.

### 5. What keeps Claude Code honest

Claude Code drafts the code. You still have to keep it on a short lead.

- **One fix per ask.** Ask for two things and you will be reviewing five changes.
- **Say it like a Figma comment.** Values and a file. `Card padding is 12px, should be 16px, in card.css.` Not `make it look better`.
- **Keep the room small.** Open the one file that matters. Less context, fewer inventions.
- **Read the diff, not the code.** Right file, right values, nothing extra. You do not read the codebase. You read the change, the way you would check a redline.

The design system is your review checklist. Without tokens you have no way to know when the AI is wrong.

### 6. Where to stop

**Yours**
- Spacing, colour, type
- Button states: hover, focus, disabled
- The words and labels on screen
- If you can point at it in a screenshot, it is yours

**Not yours**
- Anything that calculates or decides
- Anything that loads or saves data
- Anything that changes more than one screen
- Anything you cannot explain to the reviewer

A pull request is a request for someone's time. If your branch does not make main better, delete it. Nobody has to know.

### 7. Step two, when it feels normal

- Ask to read one real product repo.
- Pick one visible UI bug. Small. Something you can point at.
- Branch, fix it with Claude Code, check the diff, open a small pull request.
- A developer reviews it like any other. Your review checks it matches the design. Theirs checks it belongs in the codebase. Two different jobs.

### 8. What to ask your company for

One repo, read access, one friendly reviewer. That is the whole budget.

The sentence that works on a lead: *"There are a hundred small UI bugs nobody has time for. Give me read access to one repo and one reviewer, and I will start fixing them without adding a ticket to anyone's sprint."*

---

## Cheat sheet

| Word | Meaning |
|---|---|
| repo | the shared file, with full history |
| branch | your own copy, safe to break |
| commit | a named version you can return to |
| PR, pull request | please review my copy before it goes live |
| merge | approved, now part of the real thing |
| main | the live version everyone builds on |
| clone | download the repo to your laptop |
| push | send your commits up to GitHub |
| pull | fetch other people's commits down to you |
| diff | exactly what changed, line by line |

---

## About

Talk and deck by Ridin Dinesh, product designer working in design systems and design engineering. Given at a public design and development event in Bangkok, September 2026.

The two characters in the deck, Pip the designer and Bracket the developer, are original. Use them.

Questions, corrections, war stories: open an issue, or find me at [linkedin.com/in/ridin](https://linkedin.com/in/ridin).

## License

MIT. Take it, change it, present it. Keep the copyright line.
