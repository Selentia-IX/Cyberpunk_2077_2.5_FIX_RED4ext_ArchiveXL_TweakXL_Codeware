# Unofficial Cyberpunk 2077 2.5 builds: RED4ext, ArchiveXL, TweakXL, Codeware

Patch 2.5 ("Edgerunners II") broke the four frameworks most Cyberpunk 2077 mods depend on. These are **unofficial,
temporary builds** that work on 2.5, so you can keep playing with your mods until the official updates come out.

> **Not made or endorsed by the original authors** (wopss and psiberx). Please report problems with these builds
> **here**, not to them. When the official 2.5 versions are released, switch to those:
> [RED4ext](https://github.com/wopss/RED4ext/releases) ·
> [ArchiveXL](https://github.com/psiberx/cp2077-archive-xl/releases) ·
> [TweakXL](https://github.com/psiberx/cp2077-tweak-xl/releases) ·
> [Codeware](https://github.com/psiberx/cp2077-codeware/releases)

## Download

Get the zips from **[Releases](../../releases)**. Each one is separate; only get what your mods need.

| File | What it does | Do I need it? |
|---|---|---|
| **RED4ext** | Loads all the other plugins | **Yes**, if you use any of the other three |
| **ArchiveXL** | Lets mods add new clothes, hair, items, places and more | If your mods need it (most clothing mods do) |
| **TweakXL** | Lets mods change game data (items, stats, vendors) | If your mods need it |
| **Codeware** | Extra scripting tools many script mods use | If your mods need it |

### What's in each build

| Build | Based on | Changes |
|---|---|---|
| RED4ext | official source, master `47ac01c` (2.5 support merged, not yet released) | none, compiled as is |
| ArchiveXL 1.27.5 | official 1.27.5 | new 2.5 port ([diff](source/ArchiveXL-2.5-port.diff)) |
| TweakXL 1.11.5 | official 1.11.5 + KelpHect's PR [#22](https://github.com/psiberx/cp2077-tweak-xl/pull/22) | build fix only ([diff](source/TweakXL-on-PR22.diff)) |
| Codeware 1.20.6 | official 1.20.6 + KelpHect's PR [#63](https://github.com/psiberx/cp2077-codeware/pull/63) | build fix only ([diff](source/Codeware-on-PR63.diff)) |

## Requirements

- Cyberpunk 2077 **patch 2.5** (exe 3.0.88.46235). Tested on Steam; GOG and Epic should work too.
- **redscript 0.5.32** or newer, if you use script mods.

## How to install

1. Close the game.
2. *(Optional)* Back up your `red4ext` folder and `bin\x64\winmm.dll`, so you can go back if you need to.
3. Extract each zip you downloaded into your game folder (the one with `bin`, `archive` and `r6` in it). Allow it
   to replace files.
4. **Important:** go to `red4ext\plugins\` and move out every folder that isn't one of these four, or that hasn't
   been updated for 2.5 by its author. Old plugins make the game close on startup without any message.
5. Start the game.

Your saved Codeware data isn't touched. When the official versions come out, install them over these the same way.

## What works

- Mods load normally on 2.5.
- Clothing, hair, accessory and item mods.
- New places and world additions (for example new clubs and interiors).
- Quest and story mods.
- Character creator mods (hair, CCXL), **except custom eyes** (see below).
- Translations and new text in mods.
- TweakXL tweaks (item, stat and vendor changes).
- Script mods that use Codeware.
- Photo mode pose packs.
- Body mods: tested with Angel by Hyst and the VTK textures.
- The character creator no longer crashes when opening or editing your character.
- Loading saves no longer freezes (fixed a 2.5 deadlock in ArchiveXL's clothing code).

## What doesn't work yet

- **Starting a new game with Cyber Engine Tweaks (CET) installed** (tested with CET 1.38.0): the screen goes black
  and the game closes after about two minutes. This is CET, not these builds. **Workaround:** create the first save
  of a new game without CET. Move `bin\x64\plugins\cyber_engine_tweaks.asi` out, start the new game, save once,
  then put the file back. Loading and saving existing games works fine with CET.
- **Custom eyes in the character creator** don't show up.
- **Some custom head mods make V look broken** (spiky, "exploded" shapes across the body). It happens when a head
  mod's face shape file doesn't match its head model, which 2.5 no longer tolerates. It's the head mod, not these
  builds: remove it for now and wait for its author's 2.5 update.
- **Mirror customization:** the menu can show only the last option with a big empty space above it. That's a game
  bug and happens in the unmodded game too. With some body mods, V's arms can also turn invisible after customizing
  at a mirror; that comes from the body mod.
- **Mods from the in-game mod menu** may not work while ArchiveXL is installed. ArchiveXL turns off the game's own
  built-in mod features, because running both breaks character models. Mods you install yourself work fine.
- **Mods that change specific spots on the map** may not apply until their authors update them, because 2.5 changed
  parts of the map. They're skipped safely.
- **Other plugins** (Audioware, RedData, RedFileSystem, RedHttpClient, CyberwareEx, Mod Settings and so on) need
  their own 2.5 updates.
- ArchiveXL's "hot reload" for mod makers is turned off.

## Troubleshooting

- **The game closes a few seconds after starting:** an old plugin is still in `red4ext\plugins\`. The last line of
  the newest file in `red4ext\logs\` shows which one.
- **"REDScript compilation has failed":** one script mod isn't compatible with 2.5, and that turns off all script
  mods. Move the mods named in the message out of `r6\scripts`.
- **"The following scripts contain invalid native definitions":** those scripts belong to a plugin you removed or
  that isn't updated. Move those folders out of `r6\scripts`.
- **Black screen, then the game closes, when starting a new game:** that's CET; see the workaround above.
- **V looks spiky or exploded:** remove your head mod.

## For mod authors

The release also has an optional **`NOTES-FOR-MODDERS-source-and-tools-2.5-unofficial.zip`**. It has technical notes
on what 2.5 changed and how it was fixed, diffs of every source change, and the research scripts used for the port
(unsupported). It isn't needed to play.


| Build | Based on | Changes |
|---|---|---|
| RED4ext | official source, master `47ac01c` (2.5 support merged, not yet released) | none, compiled as is |
| ArchiveXL 1.27.5 | official 1.27.5 | new 2.5 port |
| TweakXL 1.11.5 | official 1.11.5 + KelpHect's PR [#22](https://github.com/psiberx/cp2077-tweak-xl/pull/22) | build fix only |
| Codeware 1.20.6 | official 1.20.6 + KelpHect's PR [#63](https://github.com/psiberx/cp2077-codeware/pull/63) | build fix only |

The source changes are in the mod-author zip (see below).

## Credits and licenses

- **RED4ext** © Octavian Dima (wopss). **ArchiveXL, TweakXL and Codeware** © Pavel Siberx (psiberx). All MIT
  licensed; the original licenses are in [LICENSES/](LICENSES) and inside each zip.
- **KelpHect** for the 2.5 groundwork on TweakXL, Codeware and the RED4ext SDK layouts.
- **jac3km4** for redscript.

These builds will be retired once the official 2.5 releases are out.
