# Meetup description layout

Use the user's requested section order below. The published ocgroups event supplies the current event facts. Keep the Sessionize abstracts unchanged; the example's shortened abstracts are not a general instruction to summarize future talks. Use confirmed session end times only; if unavailable, show the known start times rather than copying the example's 7:00 PM and 7:45 PM end times.

The official RSVP link belongs immediately after the bold opening invitation, before the host introduction or talks. Repeat the same verified URL after sponsor acknowledgments, just before the closing invitation. The user explicitly directs attendees to RSVP only on the CNCF official site. Use these exact labels:

- Opening: `RSVP only here (CNCF official site):`
- Closing: `Full event details and RSVP only here (CNCF official site):`

Put each link on its own paragraph, with the actual current public event URL as both visible text and destination. Never retain the example event's URL for a new event.

## Spacing and formatting

- Keep a visible blank line between every major section, between each talk block, and around the opening and closing RSVP paragraphs.
- In Markdown, use two newline characters to separate paragraphs/blocks. In the Meetup rich-text editor, use paragraph breaks or blank paragraphs as needed to preserve visible spacing; a soft line break alone does not separate sections.
- Use bold section headings and bold speaker names. Retain a readable paragraph break between the host introduction and the community welcome.
- Inspect the rendered editor or an unsaved preview to confirm the blank lines survived pasting and links remain clickable. Do not save to check formatting.
- Meetup supplies the page heading “Details”; do not add a second “Details” heading to the description body when the platform already shows it.

## Body template

Replace every placeholder. Repeat/remove talk and agenda blocks for the actual session count. The blank lines below are intentional.

```markdown
🚀 **Join us at {{VENUE_NAME}} for Food, Drinks, and Kubernetes on {{EVENT_DATE_LONG}}!**

RSVP only here (CNCF official site): [{{OCGROUPS_PUBLIC_EVENT_URL}}]({{OCGROUPS_PUBLIC_EVENT_URL}})

{{VENUE_HOST_INTRODUCTION}}

Everyone is welcome whether you are new to Kubernetes or already experienced, come connect with the Austin cloud native community. We'll share the latest updates, practical insights, and real world learnings from Kubernetes, CNCF projects, and modern platform engineering.

**FEATURED TALKS**

🎤 **{{SESSION_1_SPEAKERS}}** — {{SESSION_1_EXACT_TITLE}}

{{SESSION_1_EXACT_ABSTRACT}}

🎤 **{{SESSION_2_SPEAKERS}}** — {{SESSION_2_EXACT_TITLE}}

{{SESSION_2_EXACT_ABSTRACT}}

**AGENDA**

{{SESSION_1_CONFIRMED_TIME_LABEL}} — {{SESSION_1_TITLE}} ({{SESSION_1_SPEAKERS}})
{{SESSION_2_CONFIRMED_TIME_LABEL}} — {{SESSION_2_TITLE}} ({{SESSION_2_SPEAKERS}})

📍 **VENUE**

{{VENUE_NAME_AND_CONFIRMED_ROOM}}
{{VENUE_ADDRESS}}
{{CURRENT_ARRIVAL_INSTRUCTIONS}}

**PARKING**

{{CURRENT_PARKING_INSTRUCTIONS_AND_LINK}}

{{VENUE_SPONSOR_ACKNOWLEDGMENT_IF_APPLICABLE}}

{{CAST_AI_ACKNOWLEDGMENT_IF_APPLICABLE}}

{{ARDAN_LABS_ACKNOWLEDGMENT}}

{{OTHER_USER_SPECIFIED_SPONSOR_ACKNOWLEDGMENTS_IF_ANY}}

Full event details and RSVP only here (CNCF official site): [{{OCGROUPS_PUBLIC_EVENT_URL}}]({{OCGROUPS_PUBLIC_EVENT_URL}})

Looking forward to seeing you there!
```

Use the upstream [venue and sponsor wording](../../create-ocgroups-event/references/description-template.md) and [sponsor rules](../../create-ocgroups-event/SKILL.md). For Station Austin, the introduction is “Station Austin (formerly Capital Factory) is generously hosting the Kubernetes Austin meetup!” and its acknowledgment heading is `🏢 **VENUE SPONSORED BY STATION AUSTIN**`. Follow it with `🤖 **SPONSORED BY CAST AI**` when applicable, then `**SPONSORED BY ARDAN LABS**`. Keep a blank line between acknowledgment blocks. Preserve the authorized acknowledgment wording; use another venue's current details when applicable. Do not carry Station Austin-specific logistics to another location or promise food/drinks without supported arrangements.

Remove unused conditional placeholders and empty sections, not the required opening and closing links. Keep Ardan Labs under the standing sponsor rule even though it was absent from the pasted example; explicit event-specific user overrides still take precedence.
