# F.E.A.R.-Better-AI-Mod-ALPHA-
# Video: [Gameplay V.7](https://www.youtube.com/watch?v=AuuXsP5BSTQ&t=497s)

**(Compatibility: Main game only, not the expansions. EchoPatch is supported.)**
This is pretty much the final product; remaining bugs are most likely engine limitations. Feedback is still welcome if you think something could improve the experience.
I am usually more active on ModDB and NexusMods. Do not expect me to reply to you extremely fast if you try contacting me on GitHub.

---
## What is this mod supposed to do?
It's meant to make the AI smarter, more tactical, and better able to adapt to your playstyle; an experiment to see how far I could push the AI beyond what the developers originally designed it for.

F.E.A.R.'s AI is already advanced, and a lot of that comes down to the map layout. But it has real limits, so I removed some of those and added new behaviors, which meant reworking the AI logic and difficulty settings.

This is a clean, standalone AI mod; it only touches enemy logic, cost tables, difficulty, and a few item values to keep things balanced. Nobody else has made a mod quite like this; most go for complexity, but there's room for something closer to vanilla, just sharper.

With this installed, Replica Soldiers and ATC Security become genuinely experienced, brutal fighters. Casual players can still enjoy it; just be careful with High or Extreme.

---
## Are the difficulties still the same?
Not even close. I drastically increased the values across all tiers, so they actually mean something different now.

For reference: "High" (2.0 AI factor, 1.5 damage) sits closer to vanilla's old "High" difficulty; "Extreme" (2.5 factor, 2.5 damage) is the genuinely new tier beyond anything vanilla offered. If you found vanilla's hardest setting fair, "High" here should feel familiar; "Extreme" is where the real escalation begins.

Go "Extreme" for a real challenge; "Moderate" if you'd rather not have a bad time. I wouldn't recommend this for a first playthrough; play vanilla first, then come back.

---
## How different is it from vanilla?
Pretty different. Enemies are more dynamic and tactical, roughly balanced 50/50 between offence and defence, and adapt to how you play. It doesn't always land perfectly, but it does its job well based on testing and feedback so far.

---
## Installation
1. Download the mod.
2. Put `Arch.00` in the root of your game folder.
3. Add `"BetterAI.Arch00"` to the end of `Default.archcfg`.
4. Enjoy! Let me know about any bugs.

---
## Features
* **Agile Movement:** Fast upright side-steps to dodge bullets while still aiming and firing at you, plus more frequent precise dodge rolls.
* **Less pain reaction:** Enemies flinch less from gunfire or melee.
* **More coordination:** They stick closer to their heavy units to set up ambushes.
* **Charge Mechanic:** Enemies occasionally charge while shooting, then go for melee when you least expect it. (Watch out for shotguns; you will die a lot.)
* **Explosives:** More frequent use of explosive barrels.
* **Cover Discipline:** Enemies prioritize diving behind cover, staying low up to 10 seconds to reload safely and lay down suppressive fire.
* **Window/Door/Jump Usage:** More frequent use of windows, doors, and drop-downs to move through the environment.
* **Chatter:** Less frequent, so they can catch you off guard more easily.
* **Smart Flanking:** They avoid dead-end doorways and use side corridors/windows to flank you.
* **Grenades:** Used more cleverly; one precision throw to flush you from cover, then a switch to aggressive rifle combat for about 45 seconds. (FlushOut and GrenadeAttacks have separate timers, which can vary between enemies.)
* **Limping States:** Regular enemies start limping at 30% health (more likely to trigger now); heavy Powered Armor units limp at 20%, giving you an opening to flank.
* **Improved Awareness:** They react to disturbances immediately instead of ignoring low-cost stimuli.
* **Increased Update Rate:** Sensor and decision-making systems run in real time with no delay, so they should be able to apply their own strategies (hiding, charging, ambushing, flanking, waiting, etc.), shooting and getting in cover much faster.
* **Improved Alert System:** Soldiers get alerted more easily.
* **Limited Medkits:** Capped at 5, each healing only 50 HP; vanilla was too forgiving.
* **No Assassins:** Removed; balancing the rest of the AI meant their logic no longer fit. More in Known Bugs below. (or it is an engine limitation)
* **Improved Stealth:** Soldiers can be knocked out easily with melee, and others won't get alerted unless they're close or see you directly. (Technically a bug, but it changes gameplay in an interesting way.)
* **Real Difficulty Scaling:** "Low" through "Extreme" now genuinely change the experience; don't waste medkits, you'll need them.
* **Efficient:** One player reported hitting 4K/120fps at only 50W power draw; worth checking on your own setup too.

---
## Fixed from earlier versions
* Removed repetitive dialogue spam.
* Fixed suicidal enemy pathing (GoToTarget), now used intentionally for charging and flanking.
* Fixed grenade spam.
* Assorted minor bugs.

---
## Under the hood
This isn't just difficulty scaling. Sensors have been drastically changed across the entire system, not just individual enemy vision, so reactions and coordination happen in true real time. Goal priorities were also reweighted relative to each other (aggressive goals like Charge value meaningfully higher than defensive ones like Cover), so the AI's aggressive bias is built into the actual decision math, not just surface-level number bumps.

---
## Known Bugs
These mostly come from pushing the AI past its original limits, which makes things a little unstable. I've fixed what I could, but some of these might not be fixable without reverting parts back to vanilla. None of them are serious; the AI improvements are worth it.

* Bodyfall sound occasionally missing.
* WaterSplash sound occasionally not triggering (likely same root cause as above).
* Because of the Bodyfall bug, an NPC may not react when a nearby comrade is taken down by melee from behind. (Some players might actually like this; makes stealth more viable)
* Assassins are bugged; they run into the player and their attacks get delayed. Their AI logic isn't compatible with the rest of the changes, so they've been removed for now. Every other enemy type works correctly.
* Very rarely, enemies may walk over obstacles they shouldn't.
* Walking over some objects (like boxes) may play the wrong surface sound.
* Melee attacks while crouching are occasionally delayed by about half a second.
* Some animations/cutscenes may not always play correctly.
* Very rarely, enemies may take extra hits to go down.
* The known "First Encounter" window-transition bug (present in vanilla too) can still occur; not caused by this mod. Try switching weapons or toggling VSync if it happens.

---
## For modders
Happy to share the underlying database for anyone who wants to build on this or fix what I couldn't. Grab "FEAR Public Tools v2" to get started. Folders I worked in while building this:

```
AI\Actions
AI\ActionSets
AI\Attributes
AI\Brains
AI\Constants
AI\Goals
AI\GoalSets
AI\Limits
AI\Sensors
AI\Stimuli
Server\Difficulty
```

---
## Final notes
This mod has a few known bugs; I'm self-taught in this area, and I tried to keep it as stable as possible.
I welcome criticism and don't mind it at all, especially from other modders who might solve what I couldn't.
Realistically I might not have time to make this fully polished.
If you use the shared database and build something better, I'd love to see it; keep the proposals coming.
I've tested across 5 full playthroughs, including 3 complete runs on "Extreme" difficulty, to confirm the mod is stable and beatable at its hardest setting, not just balanced on paper. Hopefully this brings some inspiration to other modders who can take it further than I did.
<p align="center">
<img width="422" height="330" alt="9034f15596ef20c29926e3b5d50e612c" src="https://github.com/user-attachments/assets/3333aa01-45e3-4d2d-999e-6257f0314a08" />
</p>
