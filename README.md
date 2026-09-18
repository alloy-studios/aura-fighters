# aura-fighters

Aura Fighters — Rework Summary
New: Title Scene

Opens on a designed title mark with a live attract shot — a Super-form fighter burning below the logo, its flame rising through the type. Controls grid, a starting tip, and click-or-any-key to begin. The HUD hides behind it and the camera reframes on start.

Combat: every form plays differently

Previously all 11 forms shared one melee behaviour, and the specials collapsed into 6 types — beam alone covered 4 forms. Now every form owns a unique melee signature, ki blast, and special.

Melee signatures: 3-hit launcher (Super) · 5-hit chain lightning (Ascended) · blink strike with a delayed echo (Divine) · i-frame slips (Ultra) · no combo, one shockwave slam (Ego) · Rend-stacking claws that detonate (Beast) · Heat that accelerates then overheats (Overdrive) · Seal marks every 3rd hit (Godslayer) · strikes that drag enemies in (Singularity) · 360° omni-strike (Infinity)

New systems: Rend (bleed stacks), Heat (Overdrive's redline), Seals (amplify Execution), i-frames

Specials now include: Piledriver command grab, Event Horizon gravity well, the arena-ending Finale, delayed Execution with a judgment pillar

Beams

Three distinct beams rather than four copies of one: Super's sustained channel, Divine's twin beams that cross from each hand (stand at the crossing, take both), Beast's brief torn-edged Feral Cannon that loads Rend. Rebuilt renderer with hot core, stepped falloff, muzzle charge sphere, and impact blooms that terminate on the target.

Enemies — the big one

Rivals used to run one behaviour with scaled stats. Four archetypes now:

Rusher — telegraphed lunges, long recovery, punish the whiff
Zoner — holds range, fires volleys, bursts you off when you close
Duelist — circles and counters when you're mid-attack
Warlord — blinks in, area slams, enrages below 40% HP

Every attack is telegraphed with a closing ring and threat cone. Interrupting one requires landing your combo finisher early in the tell — a read, not a mash.

Progression

Enemy lap scaling 1.55× → 1.32×, and the Zenkai floor raised. The old curve punished skill: clean clears grew you ~1.17×/lap against enemies growing 1.55×. Clean play now keeps pace indefinitely; risky play still pulls ahead.

Visuals

Particle-driven auras unique to each form · per-transformation outfits (gi / battle-torn / armour plate / energy seams) · ink holdlines and rim light on both fighters · enemy tier crests · nebula depth, arena floor, persistent scorch decals · real typography (Archivo Black + Rajdhani) · angular HUD with segmented gauges and Rend/Seal/Heat readouts

Performance

223ms → ~3.4ms per frame (~65×). Soft particles now blit from a sprite cache instead of rebuilding radial gradients every frame; off-screen culling added; AURA_DENSITY exposed as a tuning knob.

Notable bugs fixed
Permanent soft-lock — a trimmed beam projectile could lock you out of every action forever
Stun-lock — fast forms froze enemies so completely they never acted; added a poise/armour system
Ultra was invulnerable — 11 i-frames on a 5-frame cooldown meant 100% uptime
Safe zone — enemies ignored you past 600 units, so you could always retreat and charge ki for free
Rend scaling with the 100× damage multiplier; Overdrive's drill never multi-hitting; the full-screen tint washing every frame olive; the aura vanishing while charging
