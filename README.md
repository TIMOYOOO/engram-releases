# Engram

A terminal whose sessions outlive its window.

A small background daemon keeps your shells running; the Deck, an Electron window with tabs, shows them and can be closed and reopened without losing anything.

## Download

**[Get the latest version](https://github.com/TIMOYOOO/engram-releases/releases/latest)** (Windows 10 or 11, 64-bit)

Download `Engram-Setup-<version>.exe` and run it. It installs for the current user only, with no administrator rights, and adds a Desktop and a Start menu shortcut.

The installer is not code-signed, so Windows SmartScreen may warn you the first time: choose *More info*, then *Run anyway*.

## Updates

Engram updates itself. The button at the top right of the window shows when a new version is available (`↑ <version>`), downloads it on a click, then installs it on a second click. Installing stops the background daemon, so any running shell is closed. The app asks first if one is open.

## About

This repository only holds the installers. The source code is private.
