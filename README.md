# radiantruin
## Project RADIANT RUIN - Etrian Odyssey IV Randomizer
### Theory and Design Document v0.00

#### some preliminary feasibility speculation based on my understanding of the internal data structures
- maps: probably static due to storage of the 3D data. it may be possible to shuffle the location of individual overworld chunks, but this would lead to a mess
- exits, maze shuffling on overworld: most likely modifiable pending further investigation
- internal zone data and enemy placement: most likely modifiable and at least semi-known for the ds games (yggdrasil zone viewer)
- items: injection of new item data is feasible so alteration of existing records should be
- enemy stats: should be possible, but scaling would need investigation - some kind of automatic multiplier based on existing stats elsewhere along the difficulty curve?
- class unlocks/talent trees: unknown, but alteration is definitely possible to some extent. skill info is, across EO games, probably one of the best-understood individual data structures in shape if not in totality (due to shuffling behavior flags, etc.)
- **flags/region unlocking**: now this is the doozy and most likely to involve core logic rewriting and asm diving
- ~~is there any other human being on the planet who'd actually play this~~ discarded (reason: depressing)

So, the goal needs to be set, for one.  Heavenbringer fight on locating tablets, maybe? I feel like the best way to plan on going about this in general is to treat it like a Free Enterprise or open-world SMRPG randomizer, with key items used to create gates for chunks of the overworld and probably specific dungeons (in addition to the 'native' locks that exist such as airship upgrades). Going off the SMRPG example, it may also be good to scale enemy or at least boss stats based on percentage of key items obtained/checks made. Any speculation on logic programming requires a full study of what's even possible to alter easily in the first place.
Ideally all of these individual aspects will be customizable and function with *any version of the game*, both important to keep in mind in case of variant addresses, character sets, and so on. Cosmetic alterations like music variation/randomization may also be possible based on existing projects such as EOX music hack.

#### (fragmentary) to-do and initial investigation
- [x] Basic citra gdb setup, environmental stuff, set up repo and write v0 of this document, etc.
- [ ] Teach myself gdb at all again and become even marginally competent at reading assembly.
- [ ] Inspect existing repos to begin understanding data table shapes and comparison with their 4 versions. 3 and 1/2U have an array of resources for these, and some classes recur; it may be possible to use this to gain more insight into subheadings than looking at the data of any game individually.
- [ ] Start experimentation with shoving a screwdriver into the data files and see what happens? I have a lot of unanswered questions regarding what it actually is feasible to directly edit, though from existing hacks a lot of it does seem editable in place.
- [ ] More optimistically, also ought to investigate seeking the permission of the speedhack maker to include that, as a significant QoL tweak which already exists.
- [ ] Begin inspecting game logic, flags, and unlock data for feasibility studies of the 'open world' concept. This may not be ultimately plausible itself, but it's sort of the ideal final form, I think.