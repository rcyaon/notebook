# how to teach with hands-on technical workshops

there's one lesson that's shaped how i think about teaching more than anything else, and it came from watching mechanical engineers try to learn soldering and pcb work at the motion studio: **lower the barrier to entry, or you lose people before they even get interested.**

sounds almost too simple to be a real insight, but watching it happen in real time taught me more than any teaching guide could have. someone genuinely curious about electronics hits a confusing step, and you can just see them deflate. when the task felt hard, interest dropped. when it felt approachable, people leaned in. **small wins build motivation.** big, ambiguous obstacles kill it.

so here's what that lesson looks like in practice, using feedback from a real workshop (a drone-building session) as the case study.

---

## 1. ambiguity is the biggest barrier, bigger than difficulty itself

people don't mind that soldering is hard, they mind not knowing whether they're doing it *correctly*. the single most common category of feedback from the drone workshop wasn't "this is too hard," it was "i don't know if i'm doing this right":

- *"step 3 - specify which screw to use... m3 x 10 (might be 12, the screws were mixed)"* — three different participants reported using three different screw sizes (m3x10, m3x12, m3x16), because nobody could say for sure which one was correct.
- *"confusion on whether we are screwing in 2 or 4 of the holes, if two screws, which 2?"*
- *"are the two screws perpendicular or parallel to the straight lines on the sides of the frame?"*

none of these are hard questions, but when the instructions aren't specific, every participant has to make their own judgment call, and every judgment call is a tiny moment of self-doubt that chips away at confidence. multiply that by twenty steps and you've built a workshop that *feels* hard even though no individual step actually was.

**the fix isn't removing difficulty, it's adding certainty.** specify the exact fastener. say which two holes, and reference something visual and unambiguous, like the straight lines on the frame instead of "the ones on the left."

---

## 2. sequence matters just as much as content

some of the best feedback wasn't about *what* was taught, it was about the *order* it was taught in:

- propellers were originally step 5 of assembly, before the electrical soldering steps. multiple participants pushed back: *"i think it would be better if this order was reversed (solder first, then propellers)."* sharp spinning propellers sitting on a workbench during a soldering step is a hazard nobody needs, and honestly it's also just easier to solder a frame that isn't already bristling with blades.
- continuity testing was buried mid-document instead of being introduced up front: *"put dial on the 'sound' icon... remind this at the start of the soldering section."* a safety and verification step that gets mentioned once and then forgotten isn't really part of the workflow, it's just trivia.
- on the 3d printing page, people needed the "watch the first few layers" step made explicit and *added* to the docs, because otherwise a failing print wouldn't get caught until it was too late to fix cheaply.

the pattern here: **teach the check before the risk, not after.** if someone needs to verify something—a solder joint, a print bed, a wire connection—before moving forward, that verification step belongs at the front of the section, not as a footnote three steps later.

---

## 3. "general enough to reuse" beats "specific to this one setup"

one instinct in technical documentation is to be maximally specific: exact printer model, exact tool, exact part number. that instinct is usually right, but it can go too far. the workshop notes called this out directly:

- *"the printer in the motion studio says 'textured powder-coated sheet'... maybe add a more general guide applying to any 3d printer (general wording instead of specific to this printer)."*
- software instructions written for one radio transmitter model didn't match the hardware people actually had in front of them: *"edgetx buddy is for radiomaster pocket, instructions say radiomaster boxer... specify from the beginning."*

both of these fail the same way. someone follows the instructions exactly as written, gets to a screen or menu that doesn't match what's described, and has no idea whether they messed up or the documentation is just wrong.

**practical takeaway:** name the specific hardware or software version right at the top, before a single instruction. and where a concept generalizes, like "select the correct build plate material," write the general principle first, then give the specific example as one illustration, not the only case covered.

---

## 4. show the thing, don't just describe the thing

by far the most repeated request across every section of the workshop was simply: **more pictures.**

- *"step 5: some visuals for soldering would be helpful."*
- *"step 6: again, more visuals would be nice."*
- *"screw holes only match the inner four screws"* followed by an actual annotated photo, which cleared up a confusion that paragraphs of text hadn't.
- *"use physical picture diagram of the receiver, label which pins are rx, tx, gnd, power since it's not labeled on the pcb itself."*
- propeller orientation: *"make propeller orientations and directions more clear, possibly annotate the image... how do i know where the leading edge is?"*

there's a reason this came up more than anything else. text is great for sequence and reasoning: "do this, then this, because..." it's genuinely bad at spatial stuff: which hole, which orientation, which wire goes where. anytime a workshop step is really about *spatial* correctness (orientation, wiring, pin mapping), a labeled photo does in one glance what several sentences struggle to do at all.

and a photo also removes the extra step of making someone translate text into a mental image before they can even check their own work. it just collapses that whole bit of effort.

---

## 5. write down the failures, not just the happy path

some of the most valuable lines in the workshop notes were the ones that admitted something didn't go according to plan:

- *"the auto-detect button does not work, had to manually match firmware based on the fc model."*
- *"had to toggle model match off and on again to actually connect, might be a bug."*
- *"motor direction configuration does not work with blhelisuite32, have to use an alternative instead because of the esc we are using."*
- *"esc seems to be missing telemetry (t3) line, unconnected for now."*

a guide that only describes the ideal path becomes actively harmful the moment reality doesn't match it, and in hands-on hardware work, it often doesn't. the person hits the exact bug the instructions never warned about, and now they're debugging *and* wondering if they broke something at the same time.

a huge part of electrical engineering is debugging—embrace it. writing down the known failure modes and their workarounds up front doesn't make a workshop look less polished. it's the difference between someone thinking "oh, this is the known issue, here's the fix" and someone spiraling into "i've ruined this and i don't know how."

---

## 6. materials lists are part of the instructions, not a footnote

there was a recurring, almost mundane thread throughout the feedback: components that were used didn't match what was written down.

none of these are conceptually hard problems. but each one forces a small, unplanned decision right when someone is deep in a task and least equipped to make a judgment call.

**a complete, accurate materials list at the very start isn't administrative overhead, it's part of lowering the barrier.** it means nobody has to stop mid-task and wonder whether the slightly different-looking part in their hand is a mistake or just an update the docs haven't caught up to yet.

---

## concluding

every one of these—ambiguous fastener sizes, propellers before soldering, printer-specific wording, missing photos, undocumented bugs, incomplete parts lists—is really just a different flavor of the same failure: **a small, avoidable moment of uncertainty that a participant has to resolve on their own, at the worst possible time, with no feedback on whether they got it right.**

none of them actually make the underlying task—soldering, 3d printing, flight controller configuration—harder. they just make it feel less certain, less safe to attempt, less likely that a wrong guess gets caught before it costs time. and that feeling is basically what decides whether someone's curiosity turns into confidence, or turns into "this isn't for me."

if there's one operating principle underneath all of this, it's the same one that started this whole line of thinking back at the motion studio: **build in small, verifiable wins, as often as you can.**

whether it's a continuity test that confirms a solder joint is good or a labeled photo that confirms a wire really does go there. none of these lower the ceiling on what people can learn. what matters more is how people apply the knowledge they gain from workshops to future projects they'll be motivated to pursue because they now have that basic foundation.
