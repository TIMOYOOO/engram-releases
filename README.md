<p align="center">
  <img src="images/icon.png" width="96" alt="Engram icon">
</p>

<h1 align="center">Engram</h1>

<p align="center">
  <b>A home for your coding agents on Windows.</b><br>
  Run several omp sessions at once, read them as chats, let one of them run the others,<br>
  watch their agents at work and answer them from your phone. Close the window: the work goes on.
</p>

<p align="center">
  <a href="https://github.com/TIMOYOOO/engram-releases/releases/latest"><img src="https://img.shields.io/github/v/release/TIMOYOOO/engram-releases?label=download&style=for-the-badge&color=ff3c8e" alt="Download the latest version"></a>
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-1f1530?style=for-the-badge" alt="Windows 10 or 11">
</p>

<p align="center">
  <img src="images/hero.png" alt="The Régie's tab: a map of five omp sessions grouped by project, and its conversation listing who works, who waits and who is done. Facette, the geode, sits over the corner of the window and introduces itself">
</p>

## Why Engram

Coding agents work for minutes, sometimes hours, and the useful way to use them is several at a time: one fixes a
bug while another writes the docs and a third waits for your answer. A terminal window is a poor place for that.
Engram is built around it:

- **They keep running.** A small background daemon holds every shell and every agent; the window (the *Deck*) is
  only a view on them. Close it, come back tomorrow: each tab is where you left it. A conversation nobody looks at
  sleeps to free its memory, and wakes up when you come back to it.
- **You read them, not their terminal.** An omp conversation shows as a chat: one line per tool call, edits with
  their diff, questions as cards you answer with a click.
- **You stay on top of many.** The *Régie* is a conversation that runs the others: ask it who is waiting, what one
  of them found, or to open a new one. *Facette*, a small geode on your desktop, shows every session's state even
  when the Deck is closed. Away from the PC, your phone shows them too.
- **You see their agents.** The *Atelier* shows every agent at work on one floor, what it costs, and lets you edit,
  compare and create agents without touching a config file.
- **They remember.** A built-in *brain*, a vault of markdown notes compatible with Obsidian, feeds each new
  conversation with what matters and keeps what they learn.

Without omp, Engram is still a terminal whose sessions outlive its window: dev servers, test watchers and long jobs
keep running in the background.

## Features

### Facette, on your desktop

<img src="images/facette.png" alt="Facette: the geode with six facets in different colors, and its bubble open on a session that waits for an answer, with a line to reply">

A small geode that stays above your windows, even with the Deck closed. Each live omp session holds one of its six
facets (colors of the Dark style; each style has its own):

- **grey** is a free facet, **lavender** a session at rest;
- it beats **amber** while its session works, detaches in **cyan** and pings when it waits for you, turns **red**
  and shakes on an error;
- it turns **green** when an answer is done, and stays green until you read it, in the Deck or from Facette.

Its **heart**, where the facets meet, is the Régie. Hover a facet for *project · session · state · since when*. Click
it and the conversation opens beside the geode, shortened to its last turns, with a line to answer it; double-click
it and the Deck opens on that conversation. Click the heart, or press `Ctrl+Alt+Space` from anywhere, to talk to the
Régie.

A session that waits for you or fails says so in a line over the geode, with a soft sound: no Windows notification to
dismiss. Drop a file or some text on the geode and it lands in the brain's inbox. Facette steps aside when a game or
a video goes full screen.

### The Régie: one conversation that runs the others

The picture at the top is the Régie's tab: a map of your omp sessions grouped by project, and its conversation docked
below. Ask it in plain words. It lists the sessions, reads their last answers, writes to them (the message arrives as
`[Régie] …`, queued if the session is at work), opens new ones in a project's folder with a first instruction, waits
until they are done and sums up what they said. A line on the map ties it to each session it worked with.

Whatever it writes into another session from a question asked in Facette waits for your *Send* or *Cancel* first. It
closes a session only when asked, never one at work, and remembers its own conversation from one opening to the next.

### The Atelier: your agents at work

<img src="images/atelier.png" alt="The Atelier: agents of two projects at work on one floor, each machine in the zone of what it is doing, with the list of what each one does under it">

A full-window view of every agent at work, behind its own button in the bar (`Ctrl+Shift+A`). Each conversation and
each of its subagents is a small machine on a shared floor; it moves to the zone of what it is doing (reading,
editing, the shell, the web, delegating) and to the counter when it waits for your answer. The machine tells the
model, its paint and pennant the project, its light the state. Under the floor, a list says what each one does, for
how long and at what cost, waiting ones first with *Reply*. It only reads omp's own files: it costs no tokens.

Click an agent and its sheet opens:

- **edit it without YAML**: what it may do, its skills, model, effort and prompt; *New*, *Duplicate*, or *Derive* a
  copy specialised for one project. The Claude Code copy is written too;
- **what it really does**: its last 30 days (missions, time, tokens, cost, failures), its last missions, and a
  comparison with its parent for a derived agent;
- **recruit from a conversation**: a model reads a conversation and drafts an agent from the rules you kept
  repeating;
- **training arena**: two agents do the same brief side by side, each in a throwaway copy of the project, with their
  diffs, time and cost, and a spending cap.

Once a week, if you accept it, the Atelier reads your recent requests and proposes an agent for a task that keeps
coming back and that none of yours covers, saying why it would help and why it might not. The *Projects* column shows
what each project's conversations cost today and over 7 days.

### Engram on your phone

Turn it on in *Settings → Phone*, scan the QR code and type the PIN shown on the PC: your phone's browser becomes a
chat app, nothing to install. It lists the Régie and each project's conversations, with what works, what waits for
you and what sleeps, and opens one in big text, with omp's questions as big buttons and pictures from the camera. A
new conversation asks which project it is for.

Everything goes through a relay that only sees encrypted traffic: no port is opened on the PC. The phone reads and
answers; configuration, terminals and files stay on the PC, which refuses them whatever the page asks.

### A Chat view for omp

<img src="images/chat.png" alt="An omp conversation in the Chat view: tool calls on one line each, an edit with its diff, a table and a code block, the context gauge under it. Facette, over the corner, explains that a finished answer stays green until it is read">

Start omp in a tab and the conversation comes to the front as a chat, with a *Terminal* tab beside it for the real
thing:

- your messages in bubbles, the reasoning folded into one line;
- **each tool call on one line**: what was done and on what, then what it came to (`9 lines`, `code 1`,
  `2 results · 1 file`); a click unfolds the output;
- **edits with their diff**, removed lines in red, added in green, with line numbers;
- tables, links, quotes, code blocks colored by language with a copy button, and **pictures**: an SVG block drawn in
  the colors of your style, a picture whose path an answer names shown under its paragraph;
- **paths in answers are links**: `src/app.js:12` opens the file in the editor at that line;
- **quote what you answer**: select a sentence in an answer, or lines in the editor, and *↩ Quote* drops it into your
  message as a chip that brings you back to its source;
- **diagrams and live pages**: a `mermaid` block is drawn as a diagram; an `html` block omp writes is a card that
  runs, on a click, as a page beside the conversation (a demo, a small tool, a chart), sandboxed with no network;
- **pictures in your messages**: paste one (`Ctrl+V`) or drop it on the view; a click on any picture shows it big,
  with zoom. Drop a **video** and the agent watches it; drop a file or folder and its path lands in the message;
- a message sent while omp works waits above the input box, with **Send now** to cut in;
- a **context gauge** under the conversation: its size against the model's context window (`186.4k / 1M`), green,
  then amber, then red as it fills.

omp itself is untouched: Engram follows the conversation file it writes, and installs omp for you the first time if
it is missing.

### Answer omp's questions with a click

<img src="images/ask.png" alt="A question from omp shown as a card, with three options, the recommended one marked">

When omp asks you something, the question and its options appear as a card in the conversation, with a picture
when an option comes with one (a render, a screenshot). One click answers;
several questions, multiple choices or a typed answer are gathered, then sent together. The answer goes into omp's own
dialog, so the terminal stays in sync.

### See the work while it happens

<img src="images/agents.png" alt="A running conversation: the status line with its timer, the pinned task list, the subagents card, Git marks in the file tree and the Agents panel">

- A **status line** says what omp is doing and for how long, with an *Interrupt* button.
- omp's **task list stays pinned** above the input box while tasks remain.
- The **subagents** it starts show as a card in the conversation, and in the **Agents panel** under the file tree:
  running ones first, with their kind, model, context, cost, time and what they are doing right now. A click opens an
  agent's log.

### Talk instead of typing

The microphone (`Ctrl+Shift+M`, from any application) types what you say into the message, live. It runs on your PC
(whisper.cpp, on the graphics card when there is one): nothing is sent anywhere. While you speak, press `F9` and draw
on your screens to circle what you mean: the picture lands in your sentence, right after the words you had said.
`Ctrl+Enter` sends. Say "Facette" and the geode wakes up and writes what you say next in its bubble (off by default).

### A brain for your agents

<img src="images/brain.png" alt="The Brain tab: the notes of a vault in a folder tree, and their links drawn as a circuit board, one zone per domain. Facette, over the corner, says that a file dropped on it goes to the brain's inbox">

The *Brain* tab holds a vault of markdown notes, compatible with Obsidian: a folder tree, search, the links of the
note you read, and a graph drawn as a circuit board (domains as zones, notes as chips, links as traces). Notes open
in the editor with a live preview.

Point it at your own Obsidian vault, or let Engram make one. A guided start asks where it lives, writes your profile
in a few questions, and lets you choose what it may do, each with its cost:

- new omp conversations start with your profile and the top of its index;
- at each message, omp gets a few pointers to the notes that match it;
- finished omp and Claude Code conversations are captured into its inbox;
- a daily upkeep, given to omp, files the inbox into pages. A strip shows what it changed, and one click puts every
  page back as it was. Each note keeps its earlier texts for 30 days.

### Your Claude subscription and MCP servers at a glance

The bar shows the **5-hour and 7-day windows** of your Claude subscription, each with its gauge; hover one to see when
it resets. With several Claude accounts signed in to omp, **⇄** switches every conversation to another one in a
click. The **MCP** button lists every MCP server omp can use, whether it is connected, its tools and its last error;
turn one off, reconnect it, or add one.

### Projects and conversations

The left panel groups your folders as projects, with every omp conversation under its project, newest first. One click
resumes a conversation in a new tab, or jumps to the tab that already runs it. Rename, filter and delete from there.

### Tabs and split panes

<img src="images/split.png" alt="A dev server and a test watcher side by side in one tab">

Tabs, panes side by side or stacked (`Alt+Shift+D`), zoom on one pane, a floating pane that stays in sight from every
tab (or in a window of its own, on any screen), search in the scrollback (`Ctrl+Shift+F`), and a notice when a long job ends in a tab you are not looking at.

### Files, Git and a code editor

<img src="images/editor.png" alt="A file open in the editor between the conversation and the file tree, with Git marks on the files and the branch under the bar">

The *Files* panel (`Ctrl+Shift+E`) follows the folder of the terminal you are in, and the disk: a file omp writes or
deletes shows at once, and lights up for a moment. Each changed file wears its **Git mark** (`U` untracked, `A` added,
`M` modified, `D` deleted, `R` renamed), folders holding changes wear a dot, and the branch with its counts stands
under the bar. Click a file and it opens next to your terminals, with its own inner tabs, syntax highlighting, search
and replace.

<img src="images/compare.png" alt="A changed file compared with its last commit, side by side">

The **Changes** view (`±`) lists the changed files alone. Click one to **compare it with the last commit**, side by
side or in one column, unchanged stretches folded, `F7` to jump from one change to the next. It follows the file live.

### Command palette

<img src="images/palette.png" alt="The command palette listing the actions and their shortcuts">

Every action with its shortcut, one fuzzy search away: `Ctrl+Shift+P`.

### Recurring tasks

<img src="images/tasks.png" alt="The tasks panel with two scheduled tasks, and the tab of a finished run">

Schedule a command or an omp prompt (`07:00`, every `2h`…). Each run gets a tab of its own with its output and exit
code. A run missed while the PC was off happens once when Engram comes back.

### Made for agents too

Every shell started by Engram knows the `engram` command, so an agent working in it can open a pane beside its own,
read what another pane shows, and close it, with no one at the window:

```
engram split --title api -- npm run dev
engram read <pane> --lines 40
engram list
```

### Settings, in English or French

<img src="images/settings.png" alt="The settings panel: language, notification area, start with Windows, style, terminal text size, start animation, live preview, shell of new tabs, Chat view, notices, Facette">

Everything in one panel (`Ctrl+,` or ⚙ in the bar), sorted by subject: General, Appearance, Terminals, omp and Chat,
Voice, Facette, Phone, Shortcuts, Brain. **Every shortcut can be changed**: click it and press the new keys. The
interface speaks English or French and follows Windows' language by default.

### Four styles

Dark, shown everywhere above, and Light are the sober ones; Capricorn and Arasaka are the showier ones.

| Dark | Light |
|---|---|
| <img src="images/chat-dark.png" alt="Dark style"> | <img src="images/chat-light.png" alt="Light style"> |
| **Capricorn** | **Arasaka** |
| <img src="images/chat-capricorn.png" alt="Capricorn style"> | <img src="images/chat-arasaka.png" alt="Arasaka style"> |

Pick one in the settings or the command palette; it applies at once, terminal colors and notification-area icon
included.

## Download

**[Get the latest version](https://github.com/TIMOYOOO/engram-releases/releases/latest)** (Windows 10 or 11, 64-bit)

Download `Engram-Setup-<version>.exe` and run it. It installs for the current user only, with no administrator rights,
and adds a Desktop and a Start menu shortcut.

The installer is not code-signed, so Windows SmartScreen may warn you the first time: choose *More info*, then
*Run anyway*.

omp is optional: without it, Engram is a plain persistent terminal.

## Updates

Engram updates itself. The button at the top right of the window shows when a new version is available
(`↑ <version>`), downloads it on a click, then installs it on a second click. Installing stops the background daemon,
so any running shell is closed. The app asks first if one is open.

## Safety

- The daemon listens on `127.0.0.1` only, and refuses anything sent by a web page.
- Every connection must give a token stored in your user folder, or it is shut out.
- A client never names a program to run: it picks a shell from a fixed list (PowerShell, cmd, Git Bash).
- The phone is off until you pair it, goes through a relay that only sees encrypted traffic, and can only read and
  answer conversations.
- Live pages from an answer run sandboxed, with no network and no access to Engram or your files.

## License

Engram is free to use, at home or at work, but it is not open source: see [LICENSE.md](LICENSE.md). In short, you may
use it on as many computers as you like; you may not resell or redistribute it, nor take it apart; it comes as is,
with no warranty.

## About

This repository only holds the installers and the release notes. The source code is private.
