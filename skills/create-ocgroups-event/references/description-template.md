# Event description template

Use this structure for the event description, adapting the venue branch and replacing every placeholder with current event information. Keep the exact Sessionize titles and abstracts in Featured Talks and Agenda; only the event's overall title is shortened. Speaker count can differ from session count.

## Title and schedule

Create a short event title combining the main topics of the Sessionize titles, usually joined with ` & `. Preserve both topics without copying two long titles in full or inventing claims. For the supplied example, a suitable short title is **Kubernetes Pod Density & Production Guardrails for AI**. A user-supplied event title takes precedence.

For the usual two-session event, schedule the first session at **6:30 PM** and the second at **7:15 PM**, in `America/Chicago`, in the supplied session order unless the user specifies another order or times. These are user-established defaults, not facts inferred from a previous event. Do not infer a session duration or the event end time from the gap between session starts. Arrival time, event start time, and first-talk time are distinct fields. For a different number of sessions, get any missing start times rather than inventing slots.

## Venue selection

The user chooses Station Austin or another location in Central Austin. Ask for the venue when not supplied; do not choose Station Austin merely because it was used last time.

**Station Austin:** use the address **701 Brazos St, Austin, TX 78701**. Propose **Apollo Room, 1st Floor** and explicitly remind/confirm with the user before saving, for example: “Station Austin usually means Apollo Room on the 1st floor. Is that the room for this event?” An explicit room confirmation already given for the current event satisfies this requirement; do not ask twice. Continue preparing the description and artwork while waiting, but do not save an assumed room as confirmed. If the user supplies a different room, use it consistently in all arrival text.

The Station Austin wording below is user-provided venue boilerplate, including the formerly-Capital-Factory wording, arrival after 5:45 PM, garage parking at $8 with validation tickets distributed, parking link, and membership link. Include these instructions for Station Austin unless the user supplies updated arrangements. Surface these practical details in the review summary so the user can correct them. Do not silently replace them based on an unrelated venue or old event. If a source checked during execution contradicts them, report the specific discrepancy and resolve it before saving conflicting instructions.

**Other Central Austin venue:** obtain the venue name, address, room (if relevant), arrival/access instructions, parking information, and any venue sponsorship acknowledgment explicitly authorized by the user. Another venue is not automatically a sponsor. Retain the overall description structure, replacing all Station Austin-specific content. Do not carry over its address, Apollo room, Capital Factory signs, arrival time, parking price/validation, or membership links. Include food/drinks and sponsor promises only when supported by the current event arrangements.

## Cast AI sponsorship

Cast AI is a standing sponsor through December 31, 2027 inclusive, based on the event date, unless the user specifies an exception. For 2028 or later, include it only if the user explicitly specifies renewed sponsorship. Reconcile this sponsor with the artwork handoff before saving; do not silently deliver inconsistent sponsor lists.

When Cast AI sponsors the event, insert the following exact acknowledgment immediately after the complete Station Austin venue-sponsorship paragraph and before “Looking forward to seeing you there!”. For another venue, place it after that venue's acknowledgment, or in the sponsor section before the closing invitation if there is no venue acknowledgment. Do not add Station Austin content to an event at another venue.

```markdown
🤖 **Sponsored by Cast AI**
Thank you to Cast AI for sponsoring Kubernetes Austin! Cast AI is the Kubernetes automation platform that keeps application performance and cloud costs on autopilot. It continuously analyzes how workloads actually behave and automatically tunes CPU, memory, and infrastructure provisioning — cutting cloud spend without hand-tuning your clusters. Learn more at [https://cast.ai/](https://cast.ai/)
```

Replace `{{CAST_AI_SPONSOR_ACKNOWLEDGMENT_IF_APPLICABLE}}` in the template with this block when applicable; otherwise remove the placeholder and leave no empty heading or conditional text in the saved description.

## Ardan Labs and other sponsors

Ardan Labs is a standing event sponsor with no supplied end date. Include it unless the user explicitly changes the sponsor list. Place this simple acknowledgment after Cast AI, or after the venue acknowledgment when Cast AI is not applicable:

```markdown
**Sponsored by Ardan Labs**
Thank you to Ardan Labs for sponsoring Kubernetes Austin!
```

Do not invent company descriptions, links, sponsorship benefits, or promotional copy for Ardan Labs. Use user-supplied copy if provided later. Add any other sponsor only when the user explicitly specifies it. Do not retain sponsors from previous events or assume another venue is a sponsor. Keep the selected sponsors consistent with the platform fields and artwork handoff.

## Station Austin description

Render Markdown or the site's supported rich-text equivalent. After saving the initial event form, also enter and save the sessions in the platform Agenda tab/section to unlock the next tab; the description below does not replace that step. `ABOUT THIS EVENT` and `AGENDA` should appear once each; avoid repeating them if the editor already supplies those section labels.

```markdown
ABOUT THIS EVENT

🚀 Join us at Station Austin for Food, Drinks, and Kubernetes on {{EVENT_DATE_LONG}}!

Station Austin (formerly Capital Factory) is generously hosting the Kubernetes Austin meetup!

Everyone is welcome whether you are new to Kubernetes or already experienced, come connect with the Austin cloud native community. We'll share the latest updates, practical insights, and real world learnings from Kubernetes, CNCF projects, and modern platform engineering.

**Featured Talks**

🎤 **{{SESSION_1_SPEAKERS}}**
{{SESSION_1_EXACT_TITLE}}

🎤 **{{SESSION_2_SPEAKERS}}**
{{SESSION_2_EXACT_TITLE}}

Expect good conversations, practical takeaways, food, drinks, and a strong community vibe.

📍 **Venue**
Station Austin
701 Brazos St, Austin, TX 78701

**Arrival Instructions**
Upon arrival at the building, please proceed to {{CONFIRMED_FLOOR}}, {{CONFIRMED_ROOM}}.
We'll be in {{CONFIRMED_ROOM}}, {{CONFIRMED_FLOOR}} (look for Capital Factory signs) after 5:45 pm.

**Parking**
We know parking in Downtown is tricky! So, you can park in the building garage for just $8.00 (validation parking tickets will be distributed)!
Street parking will still be an option. More information on parking here: https://www.capitalfactory.com/parking/

🏢 **Venue Sponsored by Station Austin**
Thank you to Station Austin for sponsoring Kubernetes Austin! Station Austin is the center of gravity for entrepreneurs in Texas. They meet the best entrepreneurs in Texas and introduce them to their first investors, employees, mentors, and customers. To sign up for a Station Austin membership, click here: https://stationaustin.org/commons/

{{CAST_AI_SPONSOR_ACKNOWLEDGMENT_IF_APPLICABLE}}

**Sponsored by Ardan Labs**
Thank you to Ardan Labs for sponsoring Kubernetes Austin!

Looking forward to seeing you there!

---

### AGENDA

**6:30 PM — {{SESSION_1_EXACT_TITLE}}**
*In-Person · {{SESSION_1_SPEAKERS}}*

{{SESSION_1_ABSTRACT}}

**7:15 PM — {{SESSION_2_EXACT_TITLE}}**
*In-Person · {{SESSION_2_SPEAKERS}}*

{{SESSION_2_ABSTRACT}}
```

Repeat or remove session blocks for the actual session count and apply explicit timing overrides throughout. Copy Sessionize abstracts unchanged, preserving paragraphs, lists, and technical punctuation; adapt only editor formatting, not the wording. When creating platform sessions after the initial Save, leave the speaker association blank if no matching speaker is found. Keep the source speaker names in Featured Talks and Agenda description text regardless of selector availability. Include all speakers of each session in both Featured Talks and Agenda. Include Ardan Labs and add other sponsor acknowledgments only when explicitly specified by the user. Keep the Station Austin acknowledgment only when Station Austin is the venue. Apply any explicit event-specific sponsor overrides to the template as well as the platform sponsor selections. Do not reuse the example's September date, speaker identities, or session content for a new event.
