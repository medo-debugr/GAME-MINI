# Mini Militia style 2D shooter
Start menu with PLAY / CHANGE MAP (20 maps, each with its own theme and props), side-view arena with free jetpack flight in all directions, UZI / Shotgun / Sniper (each with its own gun shape), grenades, melee, reload, 3 bots, kill feed and a 5:00 timer.
All art and sounds are generated in code (no external assets). The player character, bullets, flash and smoke come from "Player Shooting and Movement Mechanics".

Keyboard/mouse: A/D move, W/Space fly up, S fly down, mouse = aim + shoot, R reload, Q swap, 1-3 select weapon, G grenade, F melee, Z zoom, Esc menu.
Touch: left stick = fly in any direction, right stick = aim + fire, top buttons = reload / swap / zoom / menu, side buttons = grenade / melee.

## Update
- Left stick = Mini Militia flight: any held direction keeps the jetpack on, the body leans with the stick angle, sideways speed = flying speed. Empty fuel only weakens the thrust (never cuts out).
- Bots deal less damage (35%) and your health regenerates gradually when you are far from every enemy.
- OUTFIT button: Classic + 5 military outfits (saved on the device).
- HOST GAME / JOIN GAME: 2 players over a hotspot / same Wi-Fi (WebRTC, no server). Host sends a code, guest pastes it and sends back a reply code. In the lobby the host picks the map and match time, then presses START.

## Update 2
- Standing on a weapon shows a round swap button (gun + swap arrows) at top centre, like the reference screenshot.
- All 20 maps are closed (full floor, walls, ceiling) and bigger, with barrels, crates, sandbags, flags, bushes, crystals, clouds and more scenery.
- Shadow under the player removed.
- Enemy damage raised by 30% (35% -> 45.5% of normal).
- Touch controls redrawn like the reference: blue left stick, red right stick, ring buttons with drawn icons (no emoji).

## Update 3
- Each weapon has its own synthesized sound (pistol, magnum, SMG, AK, M4, minigun, laser, flame, launcher, EMP...). Player-death and enemy-death sounds added.
- 7 bots; smarter AI: always hunts the player, probes the terrain with rays, steers round walls/platforms and escapes when stuck, picks up weapons.
- Many more weapon and grenade pickups spread over every platform and floor; every weapon now has reserve ammo (reload works); more grenades.
- Aim = three white dashes instead of the red laser.
- New battle-command main menu.

## Update 4
- Enemy damage -20% and the attack ramps up gradually (damage, fire rate, accuracy and speed grow over the first minute; bots also join one by one).
- Start loadout: 1 UZI (fastest), 2 Grenade Launcher, 3 M93BA Sniper, 500 rounds each.
- Pickups collected automatically: ammo box (+100 to the held weapon), medkit (health to 100%), smoke grenades.
- Smoke grenade (H key / smoke button): opens after landing, lasts 20 s, enemies cannot see you inside it.

## Update 3
- Bots now appear beside the player (about 260-520 px away on either side) instead of anywhere on the map, and they come back one at a time (the fewer are alive, the sooner the next one arrives) and chase you.
- Player damage against bots is 50% (`PLAYER_DMG` in script.js).
- Weapons use the 10 gun pictures (`GUN_URLS`; weapon number i uses picture i % 10; mirror one with `GUN_FLIP`). Needs internet to load the pictures; the old drawn gun is the fallback.

## Update 4
- Weapons are now the 10 gun pictures, in the order given: 1 Rifle 30, 2 Rifle 33, 3 Heavy MG 100, 4 Grenade launcher 1, 5 Pistol 1, 6 Sniper 1, 7 SMG 40, 8 Shotgun 3, 9 Cannon 1, 10 Arrow 1 (magazine = the number of rounds).
- All guns are drawn in the same size box so they match the character.
- Clear 3-part reload sound (mag out / mid / loud lock-in); an empty weapon reloads by itself.
- Start loadout: Rifle 33 / Grenade launcher / Sniper.

## Update 5
- Magazines: Pistol 5, Sniper 7, Shotgun 60 (fires 3 pellets per shot). Reloads are much faster.
- New reload sound (magazine release / slide in / lock + small bell).
- Guns are a bit bigger and sit in the character's hand; the sniper is bigger than the rifles.
- Fixed: after the time ends, PLAY AGAIN restarts properly and the bots appear again.

## Update 6
- Enemy damage is now 10% of normal (flat). 
- Player damage: sniper 1 shot kills, pistol 2 shots, spray weapons 5 shots = half health (heavy MG 5 per bullet because it fires twice as fast), shotgun 1 hit kills, grenades / launcher / cannon kill when close and do less damage far away.
- The 10 weapons are placed randomly on every map (all 10 always appear), re-shuffled each match.
- Player start ammo (`START_RES`): sprays 300, sniper 50, pistol 60, launcher/cannon/arrow 50, hand grenades 30.

## Update 7
- Bow is drawn at the same size as the rifles (in hand and on the ground).
- Bots return at varied, slower times (3 to 10 seconds apart).
- Bullets fly exactly along the aim line (the dashed guide is drawn on the same line); a hit anywhere on the body counts.
- Hit zones: head x1.7, upper half x1.5, lower half x1 (spray weapons: 6 / 7 / 10 bullets to kill).
- Menu: EDIT BUTTONS (drag every touch button / stick, saved on the device, RESET puts them back), SOUND on/off, MUSIC on/off (music also plays softly in-game).

## Update 8
- Enemy damage back to 30% (`BOT_DMG`).
- Only 3 outfits now: the body block (head + torso) is the picture (`OUT_URLS`); arms and legs keep their shape and take a colour taken from the picture. The 7 enemies wear these outfits too. Needs internet to load the pictures (old drawn body is the fallback).


## Update 9
- The character is back to the original player exactly (red cap, red shirt, white arms and legs, blue pants), for you, your friend and the bots.
- All outfits / skin pictures and the OUTFIT menu button are removed.
- No shadow under the character. Everything else is unchanged.

## Update 10
- FIT button is back in the main menu: Classic + 5 body outfits (pictures in `SKIN_URLS`), saved on the device.
- The outfit replaces the BODY (torso) only. Head, cap, arms and legs stay the original. Needs internet to load the pictures (Classic is the fallback).
- `SKIN_TORSO` in script.js = how much of the bottom of each picture's character is used as the torso.

## Update 11
- The whole outfit picture is stretched to the exact body size (the top part is no longer cut off).
- Cap, sleeves, arms, legs and pants take the main colour of the chosen outfit picture.

## Update 12
- FIT menu now has 4 tabs: BODY (outfits), HAIR (10 hairstyles + 8 hair colours), CAP (10 caps), FACE (10 faces: happy, angry, laugh, cool, sad, shocked, wink, cute, pirate). Saved on the device, applied to your player.
- Caps take the body colour of the chosen outfit. Hair shows under/outside the cap (pick CAP > None to see the hair fully).
- LANGUAGE button in the main menu: English / العربية / Español / Français (menus, HUD texts, kill feed, connection messages). Saved on the device.

## Update 5
- EDIT BUTTONS: tap a button to select it, then resize it with the - / + buttons or the SIZE slider (50% - 220%); drag it to move it. Size and position are saved on the device. RESET restores everything.
- New muzzle effect: star-shaped flash along the aim, soft smoke puffs, sparks, ejected brass shells, and glowing tracer bullets (replaces the yellow block).
- Character redrawn closer to the reference pictures: rounder oval head, slightly sloping shoulders, flat belly line, thin dark outline, bigger always-white fists, ankle + bigger shoes.
- FIT > SHOES: 10 shoe designs (army, black combat, white / red / blue / neon sneakers, brown, desert, gold, camo boots).
- Small head motion: the head follows the aim (up / down / forward) and lags behind movement (left / right / up / down).

## Update 5
- New OUTFIT tab in the FIT screen: Classic / Mask Tunic. The Panda outfit replaces the cap, torso, both arms (weapon-holding pose + free glove pose), both pant legs and both boots with the 10 pictures (loaded from the internet). Right arm holds the gun; left arm joins in while shooting and swings free otherwise; melee uses the free glove arms.
- New MASKS tab in FIT: 8 face masks (Ninja, Domino, Surgical, Gas Mask, Skull, Bandit, Gold Mask, Hockey) drawn on the face; outfit torso enlarged.
- Second outfit 'Kung Fu' (straw hat, sash torso, arms/legs/boots) added to OUTFIT tab; torso narrowed.
- Third outfit 'Diver' (diving helmet, suit + tank torso, fins) added.
- Fourth outfit 'Pirate' added; torso narrowed again (40 wide).

## Update 13
- Head shape: round (circle) on top, oval at the bottom, and smaller (`HEAD_SX` / `HEAD_SY` = 0.66, `headPath()` in script.js).
- Pharaoh outfit (Mask Tunic) removed completely.
- New outfit added as the first OUTFIT (`New Outfit`) from the 10 gallery pictures (head, 2 arms, torso, 2 hands, 2 legs, 2 feet). `capBox` = [width, bottom y, max height] of the head picture if it needs adjusting.

## Update 14
- 'New Outfit' now uses the original Mini Militia body sizes (flag `mm: true` in `OUTFITS[0]`): torso = original shirt box (36.75 x 22.5), original shoulder points, arms 20.5 long and at most 8.75 thick, head picture fitted to the original head box (`capBox` [34, 26.5, 32]). Legs and boots already used the original boxes.

## Update: Tex proportions
- Character body re-proportioned to match the Tex reference: big head (wider than the body, rounded block with flat chin), short wide torso, short thick arms, short legs, flat boots. Hitbox, gameplay and weapon aim unchanged (muzzle position follows the new hand position).

- Body (torso, arms, legs, boots) enlarged 30% (BK in script.js); head size unchanged.

- Weapon is now held exactly in the hand: the grip sits on the centre of the fist (fist drawn over it), muzzle position updated to match.

- Added outfits "Helmet" (gallery MpJMHcy) and "Mask" (gallery 8vtff27). Gallery L4bq3th is not added yet (6 direct image links still missing).

- Mask equipped: the head (skin, face, hair, cap) is hidden, only the mask shows; head appears only without a mask.
- Weapon-holding pose: the left arm picture is auto-mirrored when it is the mirrored copy of the right one, so the fist is always at the hand end (all outfits).

- Firing pose: gun arm unchanged; the second (left) arm that is raised now uses the free-arm picture in all outfits.

- Added outfit "Outfit 3" (gallery L4bq3th). Outfits "Mask" and "Outfit 3": the head picture is fitted exactly to the head box, covers it (no base head / face under it) and moves with it.

- "New Outfit" and "Helmet": the bare head and face are no longer drawn under/around the head picture (only the picture shows, same size as before).

- MASKS tab removed from the FIT menu (the 8 drawn face masks and their code are gone; a saved mask choice is cleared). The outfit named "Mask" is still in the OUTFIT tab.
- Outfit "Outfit 4" now uses gallery t45LhWG (replaces gPMJpGM): head, 2 upper arms, torso, 2 forearms, 2 legs, 2 boots. Same settings as the "Mask" / "Outfit 3" outfits (head picture fitted to the head box).

- Outfit 4: the head picture is now anchored by its bottom edge to the top of the torso (`headBottom` in `OUTFITS`, no gap). Raise/lower the number to move the head down/up.
- Outfit 4 only: head lowered a bit (`headBottom: HEAD_TOUCH + 1.8`). Future outfits: use `headBottom: HEAD_TOUCH` so the head starts exactly at the top of the torso.

- Added 5 outfits "Outfit 5" to "Outfit 8" (galleries QcD0n18, VXRvjPL, TPbRNfj, c8FxJsK). Same settings as the standard outfits: head picture fitted to the head box, `headBottom: HEAD_TOUCH` (head starts at the top of the torso).
- "Outfit 9" removed. All outfits that use `headBottom` (Outfit 4 to 8) now have `HEAD_TOUCH + 4.5`.

- Weapons are smaller in the hand and on the ground: `GUN_K = 0.85` (1 = old size). The muzzle position follows. The HUD weapon icon is unchanged.
- Added outfits "Outfit 9" (gallery jnCsqd0) and "Outfit 10" (gallery zgN30bq), `headBottom: HEAD_TOUCH + 4.5`.
- Outfit 9 and 10: legs moved closer together (`legIn: 1.5` px each, so the boots sit on the legs). Bigger number = closer. Other outfits unchanged.
- Outfit 9 and 10: `bootFit: true` - each boot is placed so its shaft (top part) sits exactly under the end of its leg, measured from the pictures themselves, for the left and the right boot. Other outfits unchanged.
- `bootFit: true` is now on every outfit that has leg + boot pictures (not only Outfit 9 and 10).
- Added outfits "Outfit 11" to "Outfit 14" (galleries sRRRLDc, XFdrrWw, WjgJ21S, b8VNfXm): `headBottom: HEAD_TOUCH + 4.5`, `bootFit: true`.
- Added outfits "Outfit 15" to "Outfit 22" (galleries 92wwjh5, 1NPS8Ty, d7rGcHS, 4K2yMzf, vVRkD2v, bkyb6h5, Pw759jy, c3sGFkh). Outfit 16, 17 and 20 (galleries 1NPS8Ty, d7rGcHS, bkyb6h5) have unlabeled files (part-01..10), assumed order: arm-left, head, arm-right, hand-arm-left, torso, hand-arm-right, leg-left, leg-right, shoe-left, shoe-right.
- Enemy outfit: `ENEMY_OUTFIT` (index in `OUTFITS`, -1 = original enemy look) is worn by every bot / other player.
- Removed "Outfit 17" and "Outfit 20" (the other names keep their numbers). Added the "Enemy" outfit (gallery kKJ8jCS, head `HEAD_TOUCH + 6`) and set `ENEMY_OUTFIT` to it, so all bots / other players wear it (it also shows in the OUTFIT tab).

- New game menu: coins + kills counters top-left, SETTINGS gear top-right (music, sound, edit buttons, language), big buttons PLAY / JOIN / HOST / VAULT (= the outfit locker, old FIT) / MAPS, map preview on the right. Esc or tapping outside closes the settings.
- Every kill you make (solo, host or guest) adds 1 kill and 20 coins (`COIN_PER_KILL`), counted over the whole life of the game and saved on the device. With the server (folder `server`, set `STATS_SERVER` in script.js) the kill count is also saved permanently on the server; kills made offline are sent when the connection is back.
- Menu redesigned like the reference picture: cartoon scenery, wooden title, Settings / Inventory (= outfit locker) / Maps tiles, Join / Host, big Play button with map arrows (previous / next map) and the map name under it; BACK TO BATTLE (yellow, top-left) appears while a match is running. The coins and kills counters are no longer shown (kills are still counted in the background and saved, see the server folder).

## Update 5
- New main menu: your character (current outfit, hair, cap, face, shoes) stands in the middle holding a rifle; Settings / Inventory / Maps on the left, Join / Host on the right, PLAY with map arrows under the hero.
- New animated battle background: dusk sky, burning city, smoke, searchlights, helicopter + jet, tracer fire, sandbags, barbed wire, embers.

## Update 6
- Every outfit: legs are narrowed / moved inward so they never stick out past the torso (hips), and each boot is scaled so its shaft matches the end of the leg and sits exactly on it.

## Update 7b
- Boots: in every outfit the boots are always behind the foot (front of the boot shaft under the front of the leg end, extra size goes to the back).
- Enemy outfit only: legs a bit wider.
- Hand/arm pose is back to the original (no shoulder-level limit).

## Update 8b
- All outfits are worn on the classic body: every outfit uses the classic part sizes (torso box, leg box, shoe box). The boot picture is drawn BEHIND the leg (leg end covers the top of the boot), heel/toe/sole positions = classic shoe.

## Update 8c
- Boots: each boot is exactly as wide as the end of the leg, the leg picture ends on the first (top) part of the boot, the sole stays on the classic ground line, nothing sticks out.

## Update 8d
- Boots: the neck of each boot is exactly in the middle of its leg and as wide as the leg end; the leg picture covers the top bit of the boot so a bit of it is behind the leg.

## Update 8e
- Leg width (enemy outfit widening) now grows inward: the outer edge of each leg stays inside the torso, the extra width goes towards the middle.

## Update 9b
- Removed outfits: Mask, Outfit 3, Outfit 9, Outfit 10, Outfit 15 (the chosen outfit is now saved by name).
- Auto-fit: every outfit picture is measured when it loads and fitted to the classic body (legs inside the torso, boot neck centred on the leg, arm thickness kept in the classic range).

## Multiplayer server (updated)

The old manual WebRTC QR exchange has been replaced by a Socket.IO room relay. Deploy `server/` with `npm install && npm start`, then set `window.MP_SERVER_URL` before the Socket.IO/game script tags in both `src/index.html` and `dist/index.html` when the server is on a separate domain. See `server/README.md`.

The current game logic remains host-authoritative in the host browser; the server validates room membership and routes guest inputs/host snapshots. Full server-authoritative hit validation requires a separate migration of the combat simulation and is not part of this compatibility-preserving transport update.
