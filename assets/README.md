# Vesper Tactics art pack v1 (art-only slice)

All PNG, transparent unless noted. `@2x` = same art at double size for HiDPI.

## Units (64x80 canvas each)
Foot anchor for every unit file: (32, 76) in the 64x80 canvas (@2x: (64, 152) in 128x160).
Draw a unit by placing that anchor on the tile's diamond center: drawX = tileCenterX - 32, drawY = tileCenterY - 76.
- `units/warrior_player.png` / `units/warrior_enemy.png`
- `units/archer_player.png` / `units/archer_enemy.png`
- `units/brute_player.png` / `units/brute_enemy.png`
- Player versions face right with a blue ring at the feet; enemy versions face left with a red ring.
- `units/<class>.png` = no ring, faces left (use if you draw team rings in code and mirror yourself).
- Priest, monk, mage, and assassin use that same canvas and foot anchor, including player and enemy variants and `@2x` copies. The battle draws the 1× sprites.

## Tiles
- `tiles/grass.png` 64x32 diamond (flat, matches current grid).
- `tiles/rock.png` 36x27 doodad. Anchor = bottom-center; draw at (tileCenterX - 18, tileCenterY + 6 - 27), after ground, before units (depth-sort with units by row).

## UI
- `ui/hp_frame.png` 40x7 (gold border, dark violet fill).
- `ui/hp_fill_player.png` / `ui/hp_fill_enemy.png` 38x5; crop width to hp% and draw at frame +1,+1.
- Suggested placement: frame top-left at (tileCenterX - 20, tileCenterY - 70), i.e. just above the head.

## Logo
- Main (boot/title): `logo/vesper_logo_main_1280x720.png` (opaque dark violet), `logo/vesper_logo_main_640x360.png`, `logo/vesper_logo_main_transparent.png`.
- HUD emblem / favicon: `logo/vesper_crest_transparent.png` and `logo/vesper_crest_{256,128,64,32}.png`.
- Secondary: `logo/vesper_logo_alt1_dusk_1280x720.png` (loading/splash), `logo/vesper_logo_alt2_parchment_1280x720.png` (menus/README).

`preview_meadow_mock.png` shows everything placed on a 6x6 grid at 2x zoom.

## Party pick UI (v1.1)
Folder `ui/party/`. Every file also has an `@2x` version. The party screen offers warrior, archer, brute, priest, monk, mage, and assassin.
- `card_<class>_normal.png` 112x152. `card_<class>_disabled.png` is the same size.
- `card_<class>_selected.png` 128x168, with an 8px glow. Draw it at (x − 8, y − 8) so the card does not shift.
- `card_empty.png` 112x152 for an open slot in the four-unit lineup.
- `panel_9slice.png` 96x96, 24px corners. `border-image: url(panel_9slice.png) 24 fill / 24px stretch;` On high-DPI screens use `panel_9slice@2x.png` with a 48px slice.
- `portrait_<class>.png` 96x96 is optional HUD art and is not drawn yet.
- Font: `fonts/Cinzel-VariableFont_wght.ttf` (SIL Open Font License 1.1; see `fonts/OFL.txt`). Headings on the party pick screen use it.

## Battle buttons
Folder `ui/battle/`. Every file also has an `@2x` version. Move, Attack, Cancel, Wait, and Skip move use the pre-labeled sprites. Pressed is the pointer-down face. Disabled is the grey face. The label is in the art, so the button text is hidden.
- `btn_move`, `btn_attack`, `btn_cancel`, `btn_wait`: 112x32, each with `_normal`, `_pressed`, and `_disabled`.
- `btn_skip_move`: 128x32, same three states. The HUD scales it into a 112x32 cell so the grid stays even.
- `btn_9slice.png` 48x48 unlabeled shell, 12px corners. `border-image: url(btn_9slice.png) 12 fill / 12px stretch;` On high-DPI screens use `btn_9slice@2x.png` with a 24px slice so the corners stay 12px. The sixth grid cell is this shell with no label. The five actions do not stretch it; their frames are already in the labeled sprites.
- Grid, every cell 112x32: Move, Attack, Cancel / Wait, Skip move, empty.
- Class skills have no labeled sprites. Their names are Cinzel text on `btn_9slice`, in a row under that grid.
