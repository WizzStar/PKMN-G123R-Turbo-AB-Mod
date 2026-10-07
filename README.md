# G123R Turbo_AB Mod

Hold **A** or **B** on dialogue and battle text to keep advancing after a short delay — no more mashing. Supports **Gen1Recomp** (Red, Blue, Yellow), **Gen2Recomp** (Gold, Silver, Crystal) and **Gen 3** (FireRed, LeafGreen, Ruby, Sapphire, Emerald).

## Persona

Small accessibility / QoL input helper for Gen 1, Gen 2 & Gen 3 Recompilation project text.

## Try it

1. Enable **G123R Turbo_AB Mod** in the mod manager.
2. Talk to an NPC or start a battle.
3. Hold **A** or **B** — after a brief pause the text keeps advancing page after page.
4. When a YES/NO box, a menu or the battle command box appears, turbo stops — you choose.
5. Tweak **HOLD DELAY** and **REPEAT SPEED** under the mod’s options.

## Defaults

| Option | Default | Meaning |
|---|---|---|
| TURBO A/B | ON | Master enable |
| TURBO A | ON | Holding A repeats |
| TURBO B | ON | Holding B repeats |
| HOLD DELAY | 16 | Frames before the first repeat (~267 ms) |
| REPEAT SPEED | **3** | Middle of a 1–5 ladder (see below) |

### REPEAT SPEED ladder

| Setting | Feel | Frames between repeats |
|---|---|---|
| 1 | Slower | 14 |
| 2 | Slightly slower | 12 |
| **3** | **Default** | **10** |
| 4 | Slightly faster | 8 |
| 5 | Fastest | 6 |

## Where turbo fires

| Generation | Covers |
|---|---|
| Gen 1 / Gen 2 | `TextBox` on top of the stack (field dialogue, signs, item text…) and the battle state's text phases (`intro`, `messages`, `resolving`) |
| Gen 3 | Field messages with no menu layer open, and battle text while no command / move / target / bag / party UI is up |

### Always suppressed

* Overworld (nothing on screen), so holding A never re-talks to an NPC in a loop
* Every menu: Start menu, bag, party, PC, shops, options
* Battle command box (FIGHT / BAG / POKéMON / RUN), move select and target select
* YES / NO prompts, text boxes that end in YES / NO, and multichoice lists
* Naming screens, Slot Machine, Roulette, Berry Blender, Contests, Surfing Minigame, Unown Puzzle, Card Flip
* A+B+SELECT+START (soft reset) — turbo pauses while START or SELECT is held

### Opt out (for UI authors)

On your screen object (Gen 1/2) or the module you `Stack.push` (Gen 3), set either:

```lua
state.noTurboAB = true
-- or
state.turboAB = false
```

Or from another mod: `exports.denyScreen("my_screen_id")` / `exports.allowScreen(id)`.

## Pairs with

**G123R Turbo_Scroll Mod** — hold the D-pad in menus. Same HOLD DELAY / REPEAT SPEED options, no overlap: Turbo_Scroll handles the D-pad in menus, Turbo_AB handles A/B on text.
