# osm

Tiny session picker for OpenCode and Kilo.

## What is it?

OpenCode and Kilo are terminal tools for AI coding sessions. They store sessions in SQLite, but the built-in experience is annoyingly easy to lose when folders move or the original workspace disappears.

That’s the problem `osm` fixes: one command, one list, arrow up/down, Enter to resume.

## Why does this exist?

Because OpenCode can lose sessions in the most infuriating way possible:

- the folder moved
- the workspace changed
- the session is still in the database
- and now you’re stuck hunting for it like a cursed detective

`osm` shows the session name, ID, folder, and last update time so you can jump back in fast.

## Works great with isolated profiles

If you use isolated OpenCode/Kilo homes, `osm` will follow the active environment and read the matching SQLite DB.

It works especially well with:

https://github.com/lirrensi/opencode-kilocli-isolated-profile

That tool sets the home/profile environment first, then launches OpenCode or Kilo. `osm` just reads the active home and finds the right database.

## Install

```bash
uv tool install git+https://github.com/lirrensi/opencode-kilocli-session-tool.git
```

## Run

```bash
osm
```

The launcher name can be anything; `osm` auto-detects the active backend from the current home.

## Keys

- ↑/↓ move
- Enter resume
- q quit

## Example

```bash
osm kilo-zero
osm oc-work
```

Those names are just labels for your launcher/profile flow. `osm` still resolves the DB from the active environment.
