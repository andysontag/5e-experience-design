# 5E Design Map — Output Guide

Read this before building the map, whether it is the mid-session draft or the final one.

## Where to start

Copy `assets/map-template.html` and fill its slots. It is a complete, self-contained page — inline CSS, no external dependencies, dark mode and print styles already handled. Every slot is marked `{{LIKE_THIS}}` with a comment above the block explaining what belongs there.

Do not restyle it. The visual system is deliberate — 8pt spacing, a single type scale, phase accents that all pass WCAG AA on both light and dark surfaces — and improvised changes tend to break one of those quietly. If the user asks for something different, that is a different instruction and you should follow it.

Deliver the finished file to the user. Describing the map in chat is not the deliverable.

## What goes in each slot

**Header.** `{{EXPERIENCE_NAME}}` is whatever the user calls the thing, not a title you compose for them. If no title came, use a plain description of the thing in their words rather than inventing one. The three meta chips are experience type, audience and duration; delete any the user never specified rather than guessing.

**The Meaningful Outcomes block.** `{{AMBITION}}` is what they said when asked what would happen if it went really well, before any constraint was applied. `{{MEANINGFUL_OUTCOMES}}` is what the experience is for, in prose, in their words. `{{EXISTING_STATE}}` and `{{PREFERRED_STATE}}` are the "from" and the "to" of the core shift. `{{MEANING_1..3}}` are the three they picked from Shedroff's list, exactly as named. `{{BEHAVIOUR}}` is what you would see afterwards. Quote all of these as closely as their words allow; paraphrasing weakens the map.

**The state line.** The template header carries a `<p class="state-line">` paragraph. **Delete it in almost every map.** It appears only when one threshold is met: the map records moves, and there are no Meaningful Outcomes and not one phase with a stated feeling. That is an agenda rendered as a map, and the line lets anyone it is forwarded to read it correctly. Use the string exactly as it ships:

```html
<p class="state-line">Moves only: the Meaningful Outcomes and the emotional journey for this experience have not been designed yet.</p>
```

One consistent string, the same reasoning as the unset markers below. If any part of that layer exists, even one feeling in one phase, delete the paragraph and let the unset slots carry it on their own.

**A dropped meaning is not on the map.** If you asked which one they would drop and they dropped one, the map carries the three they finished with. Do not add a fourth chip or annotate the one that went; the map records where they landed, not how they got there.

**The two maps.** The mid-session draft and the final map use the same template. The only difference is that the draft has no moves in it yet, because none have been discussed. In the draft, use the normal card body for every phase, not the `open` pattern — the phases are not unreached, they are unfilled, and they should look like slots waiting rather than questions abandoned. Write each empty move slot as:

```html
<li class="unset">Not designed yet</li>
```

Use the `open` card pattern only in the final map, and only for a phase the conversation genuinely never reached.

**See / Do / Feel.** One line each, concrete. *See* is what is in front of the participant, *Do* is the action they take, *Feel* is the intended emotional state.

Users describe phases in activities, so *Feel* is the slot most often left empty. During the conversation that is worth one question — asking what someone should be feeling by the end of a phase is a facilitation question, not a design suggestion, and the answer is usually the most useful thing in the card.

If it is still unstated when you build the map, write exactly:

```html
<dd class="unset">Not named yet</dd>
```

Not a guess, not a blank row, and not a phrasing you invent on the spot. Guessing puts your intention in the user's map under their name. A blank row reads as an oversight rather than a live question. And an improvised label — "not yet defined", "TBC", "open" — means two maps from the same skill disagree about what an empty slot looks like, which makes the marker useless as a signal. One consistent string is what lets a user scan a map and see instantly what they never decided.

**Moves.** The specific choices the user made, in their words. Add or remove `<li>` elements to match what they actually chose; do not pad a thin phase out to a matching length. A phase with one real move and one empty line reads as more honest than a phase with two invented ones.

**Pitfall badges.** The template carries a single exemplar, on the Excitement card. It is optional and starts populated only so you can see the markup — delete it unless you actually flagged something for Excitement, and copy it into another card only where you flagged something there. Do not treat a slot's presence in the template as a phase that expects a badge; a badge on a phase you never challenged, or one the user subsequently fixed, misrepresents the session back to them.

**Pitfall summary.** Include the whole `<section class="summary">` only if something was flagged. Each entry is the pitfall in a few words plus one line on why it matters. Delete the section entirely if the conversation surfaced nothing.

## Edge cases

**A phase the user deliberately kept light.** Fill it normally and say so in the moves list — "intentionally minimal, single-session format". A thin phase by choice is a design decision and should read as one.

**A phase never reached.** Use the `open` card pattern — the Extension card in the template shows it. Dashed rule, muted heading, and the open questions in place of moves. Leave it visibly unanswered rather than inventing content or dropping the card. The empty card is the next conversation, and presenting it that way is more useful to the user than a map that looks finished and isn't.

**Fewer than five phases discussed.** Still render all five cards. The gaps are the point of the framework.

**After a spar.** Only update the map if the user asks, and only with changes they stated themselves. Never write in a revision you argued them into — see `spar-mode.md`.

## If the template is unavailable

Build the page from scratch to the same spec: single self-contained HTML file, outcome statement anchored at the top, five phase cards in order with See/Do/Feel and moves, pitfall summary at the bottom if any were flagged, readable on a phone, sensible in print, no external dependencies.
