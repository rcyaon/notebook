# how to teach with hands-on technical workshops

one lesson has shaped how i teach more than anything else, watching mechanical engineers learn soldering and pcb work: **lower the barrier to entry, or you lose people before they get interested.** when a task felt hard, interest dropped. when it felt approachable, people leaned in. small wins build motivation; obstacles kill it.

here's what that looks like in practice, using feedback from a real drone-building workshop.

---

## 1. ambiguity is a bigger barrier than difficulty

people don't mind that soldering is hard — they mind not knowing if they're doing it *correctly*. three participants used three different screw sizes because nobody could say for sure which one was right. "are the two screws perpendicular or parallel to the frame lines?" none of these are hard questions, but an unclear instruction forces a judgment call, and every judgment call chips away at confidence.

**fix:** add certainty, not just less difficulty. specify the exact fastener. reference something visual and unambiguous.

## 2. sequence matters as much as content

propellers were originally step 5, before soldering — sharp spinning blades sitting on a workbench mid-solder is a hazard nobody needs. continuity testing was buried mid-document instead of introduced up front, so a safety check became forgettable trivia.

**fix:** teach the check before the risk, not after. if someone needs to verify something before moving forward, that step belongs at the front of the section.

## 3. general enough to reuse beats specific to this one setup

instructions written for one 3d printer or one radio transmitter model didn't match the hardware people actually had ("edgetx buddy is for radiomaster pocket, instructions say radiomaster boxer"). someone follows the steps exactly, hits a mismatched screen, and can't tell if they messed up or the docs are wrong.

**fix:** name the exact hardware/software version up front. where a concept generalizes, state the general principle first, then give one specific example.

## 4. show the thing, don't just describe it

the single most repeated request across the entire workshop: more pictures. text is great for sequence and reasoning ("do this, then this, because...") but bad at spatial stuff — which hole, which orientation, which wire goes where. an annotated photo of the receiver pins cleared up confusion that paragraphs of text hadn't.

**fix:** anytime a step is really about spatial correctness, use a labeled photo instead of a sentence.

## 5. write down the failures, not just the happy path

"the auto-detect button does not work, had to manually match firmware." "motor direction config doesn't work with blhelisuite32, use an alternative." a guide that only shows the ideal path becomes actively harmful the moment reality doesn't match — now the person is debugging *and* wondering if they broke something.

**fix:** document known bugs and their workarounds up front. it's the difference between "oh, that's the known issue" and spiraling into "i've ruined this."

## 6. materials lists are part of the instructions

components used didn't match what was written down, again and again. none of these are conceptually hard problems, but each forces a small, unplanned decision exactly when someone is least equipped to make one.

**fix:** a complete, accurate materials list up front isn't overhead — it's part of lowering the barrier.

---

## concluding

every one of these is the same failure in different clothes: a small, avoidable moment of uncertainty someone has to resolve alone, at the worst possible time, with no feedback on whether they got it right. none of it makes the underlying task harder — it just makes it feel less safe to attempt. that feeling decides whether curiosity turns into confidence, or into "this isn't for me."

build in small, verifiable wins, as often as you can.
