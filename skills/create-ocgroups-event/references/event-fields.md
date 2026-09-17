# Event fields and source mapping

## Sources and precedence

Use current user instructions, confirmed logistics, and the current Sessionize sources. Use `artwork-manifest.json` to match artwork to the same event and to reuse verified speaker/title information. Use the user-established venue boilerplate and schedule defaults in [description-template.md](description-template.md). Other prior-event facts must not carry forward without confirmation.

The repository's `creating-an-event.md` links the full event workflow to the four canonical skills. This skill handles only the ocgroups draft stage; its invocation does not authorize executing the Sessionize, Meetup, or LinkedIn stages.

The public ocgroups.dev homepage and [group explorer](https://ocgroups.dev/explore?community%5B0%5D=cncf&entity=groups) were inspected on 2026-09-17. Organizer fields, upload controls, and draft-saving behavior must be checked in the authenticated interface at execution time. No platform API or form selectors are assumed by this skill.

## Field mapping

| Field | Source and handling |
| --- | --- |
| Group | Verified Kubernetes Austin group on the live site; do not infer group IDs from the old Bevy guide |
| Event title | User-supplied title, or a short combination of the main Sessionize topics joined with ` & `; retain full exact titles in Featured Talks and Agenda |
| Date and time | Use the current date and `America/Chicago` for these Austin events unless overridden. Default session starts are 6:30 PM and 7:15 PM for two sessions. Keep event start, arrival, and session times distinct; do not hard-code CST/CDT |
| End time | Confirmed end time or duration; ask if required and missing |
| Format and location | User-selected Station Austin or another Central Austin venue. For Station Austin use 701 Brazos St, Austin, TX 78701 and confirm the default Apollo Room, 1st Floor. Use venue-specific instructions for other locations; follow explicit virtual/hybrid overrides |
| Description | Event introduction, distinct session sections with titles/abstracts and corresponding speakers, confirmed schedule, logistics, and sponsor acknowledgments |
| Speakers | Search the platform selector for the Sessionize speaker and select only an identity match. If not found, leave the association blank and continue; do not create a profile or select a substitute. Retain exact speaker names in descriptive text and the handoff, and note unmatched speakers for review. Use source-backed bios and verified public links when available |
| Hosts | Current group organizers if supported; confirm current membership rather than copying a stale host list |
| Sponsors | Follow the sponsor rules in SKILL.md: Station Austin only when hosting, Cast AI through 2027-12-31 inclusive by event date, and Ardan Labs with no supplied end date. Others only when the user specifies them. Apply explicit user overrides; cross-check artwork and do not infer sponsorship from a logo, another venue, or a speaker employer |
| Missing sponsor entries | Search existing sponsors first. If an authorized sponsor is absent, add it under Settings → Sponsors as Silver unless the user specifies another tier; reuse the original logo from the artwork workflow, fitting it proportionally with padding into a verified 360 × 360 PNG. Upload that square logo, verify the entry, associate it with the draft, and tell the user what was added. Preserve tiers on existing sponsor entries |
| Registration | Explicit current settings. The repository historically used RSVP and a capacity of 50; treat this as a proposal to confirm, not an automatic limit |
| Images | `ocgroups_long` and `ocgroups_short_mobile`, using actual file metadata and observed live upload controls |
| Visibility | Draft/unpublished, verified after saving |

For Station Austin, use the supplied venue-sponsorship acknowledgment and formerly-Capital-Factory wording in the description template. Use current Station Austin branding from the artwork handoff; do not substitute an old Capital Factory logo. The room reminder/confirmation is required for the current event unless the user already confirmed it.

## Description composition

Write a short invitation suitable for the confirmed event. Give each session its own heading, followed by the same abstract from Sessionize and its speaker name(s). Copy abstracts unchanged in both description and platform sessions, preserving paragraphs, lists, and technical wording; adjust only formatting required by the editor. Do not summarize or rewrite abstracts; do not add promised demos, prerequisites, expertise, food, accessibility services, or recording availability that sources do not establish. The supplied Station Austin boilerplate explicitly supports its food/drink invitation and venue logistics; use it for that venue unless the user changes the arrangements.

Include an agenda using the usual two-session start times, 6:30 PM and 7:15 PM, unless the user overrides them. For other session counts obtain missing start times. Include the confirmed venue/room, arrival instructions, sponsors, and relevant attendee links when available. Use current group policy links only when supplied or verified on the group's official page.

Preserve separate session records in the handoff. A displayed `&` between titles is a presentation separator, not part of either source session title.

## Review before save

Check that the event and artwork refer to the same date, people, and sponsors; confirm both time boundaries and timezone; check venue/room and registration settings; inspect banner crops and text legibility; remove copied previous-event references. Review the initial event form and click Save to create the draft, then fill and save the platform Agenda to unlock the next tab. Do not block the initial save on agenda fields that become available afterward. Continue the remaining draft tabs and repeat these checks on the completed draft. An AGENDA heading in description text does not substitute for platform agenda entries. Never publish to progress through tabs. Missing optional fields can remain blank when supported, but must be called out in the review summary; required fields must never be fabricated to make the form submit.
