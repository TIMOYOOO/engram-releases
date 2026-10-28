<p align="center">
  <img src="images/icon.png" width="96" alt="Engram icon">
</p>

<h1 align="center">Engram</h1>

<p align="center">
  <b>A terminal whose sessions outlive its window.</b><br>
  Close it, reopen it: your shells, your dev servers and your coding agents are still running.
</p>

<p align="center">
  <a href="https://github.com/TIMOYOOO/engram-releases/releases/latest"><img src="https://img.shields.io/github/v/release/TIMOYOOO/engram-releases?label=download&style=for-the-badge&color=ff3c8e" alt="Download the latest version"></a>
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-1f1530?style=for-the-badge" alt="Windows 10 or 11">
</p>

<p align="center">
  <img src="images/chat-arasaka.png" alt="Engram showing an omp conversation in its Chat view, with projects and conversations on the left">
</p>

## Why Engram

Most terminals die with their window. Engram splits the two: a small background daemon keeps every shell alive in its
own pseudo-terminal, and the window (the *Deck*) is only a view on them. Close the Deck, open it again later: each tab
comes back exactly as it was, screen, colors and cursor included, with whatever kept running in the meantime.

It is built for long-running work: dev servers, test watchers, and coding agents such as omp that you want to leave
working while you do something else.

## Features

### A Chat view for omp

<img src="images/chat-capricorn.png" alt="The Chat view: the request in a bubble, the reasoning and the tool calls folded, the answer in plain text">

Start an omp conversation and Engram shows it as a chat instead of a raw terminal stream: your messages in bubbles,
the reasoning folded into one line, the tool calls grouped, the answer as clean text with code blocks. The input box
types straight into omp, and the real terminal is always one shortcut away (`Ctrl+Shift+T`) for its questions and
permissions. omp itself is untouched: Engram follows the conversation file it writes.

### Projects and conversations

The left panel groups your folders as projects, with every omp conversation under its project, newest first. One click
resumes a conversation in a new tab, or jumps to the tab that already runs it. Rename, filter and delete from there.

### Tabs and split panes

<img src="images/split.png" alt="A dev server and a test run side by side in one tab">

Tabs, panes side by side or stacked (`Alt+Shift+D`), zoom on one pane, a floating pane that stays in sight from every
tab, search in the scrollback (`Ctrl+Shift+F`), and a notice when a long job ends in a tab you are not looking at.

### A code editor beside the terminal

<img src="images/editor.png" alt="A file open in the editor between the conversation and the file tree">

The *Files* panel (`Ctrl+Shift+E`) follows the folder of the terminal you are in. Click a file and it opens next to
your terminals, in the same tab, with its own inner tabs, syntax highlighting, search and replace.

### Command palette

<img src="images/palette.png" alt="The command palette listing the actions and their shortcuts">

Every action with its shortcut, one fuzzy search away: `Ctrl+Shift+P`.

### Recurring tasks

<img src="images/tasks.png" alt="The tasks panel with two scheduled tasks, and the tab of a finished run">

Schedule a command or an omp prompt (`07:00`, `lun-ven 07:00`, every `2h`…). Each run gets a tab of its own with its
output and exit code. A run missed while the PC was off happens once when Engram comes back.

### Made for agents too

Every shell started by Engram knows the `engram` command, so an agent working in it can open a pane beside its own,
read what another pane shows, and close it, with no one at the window:

```
engram split --title api -- npm run dev
engram read <pane> --lines 40
engram list
```

### Two styles

| Capricorn | Arasaka |
|---|---|
| <img src="images/chat-capricorn.png" alt="Capricorn style"> | <img src="images/chat-arasaka.png" alt="Arasaka style"> |

Pick one from the tray icon's menu (*Style*); it applies at once, terminal colors included.

## Download

**[Get the latest version](https://github.com/TIMOYOOO/engram-releases/releases/latest)** (Windows 10 or 11, 64-bit)

Download `Engram-Setup-<version>.exe` and run it. It installs for the current user only, with no administrator rights,
and adds a Desktop and a Start menu shortcut.

The installer is not code-signed, so Windows SmartScreen may warn you the first time: choose *More info*, then
*Run anyway*.

The interface is in French. omp is optional: without it, Engram is a plain persistent terminal.

## Updates

Engram updates itself. The button at the top right of the window shows when a new version is available
(`↑ <version>`), downloads it on a click, then installs it on a second click. Installing stops the background daemon,
so any running shell is closed. The app asks first if one is open.

## Safety

- The daemon listens on `127.0.0.1` only, and refuses anything sent by a web page.
- Every connection must give a token stored in your user folder, or it is shut out.
- A client never names a program to run: it picks a shell from a fixed list (PowerShell, cmd, Git Bash).

## About

This repository only holds the installers and the release notes. The source code is private.
