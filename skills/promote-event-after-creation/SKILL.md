---
name: promote-event-after-creation
description: Create one Kubernetes Austin LinkedIn company-page draft from event artwork and a published ocgroups.dev link, verify posting permission and mentions, return the saved draft URL for user review without publishing, and add an available verified Meetup event URL to the matching ocgroups.dev event.
---

# Promote event after creation

Create **one LinkedIn company-page draft** for user review, independently from supplied event artwork and a published ocgroups.dev link or using existing event handoffs. A Meetup event and upstream skill execution are not required. Return the saved draft URL to the user. Do not prepare other social posts, promotion waves, or schedules. Do not publish, announce, or send messages. The only event-listing change in this skill is adding an available verified Meetup event URL to the matching ocgroups.dev event, as described below.

## Check LinkedIn permission first

Before drafting or uploading, open [the target LinkedIn company page](https://www.linkedin.com/company/97438051) in an authorized session. Verify that the current user has permission to compose and save posts **as this Page**, using observable Page management/posting controls and the selected author identity. Being able to view or follow the public Page does not establish posting permission. Never switch to posting as the user's personal profile.

If signed out, ask the user to sign in through the normal flow so permission can be checked. Do not request passwords or cookies. If the user lacks Page posting permission, **stop this skill** and tell them: “You need posting access to this LinkedIn company page. Please ask a Page administrator to grant permission, then run this skill again.” Do not use another account or channel to bypass missing permission. If permissions cannot be determined, stop and state that verification is needed rather than claiming access was denied.

## Required event inputs

Two supported entry points:

- **Independent run:** the user supplies finished event artwork and the public ocgroups.dev event link. These are sufficient starting inputs. Read the event page for its details, inspect the supplied artwork, and proceed after the LinkedIn permission check. Do not require a Meetup event, Sessionize access, an artwork manifest, or previous skill execution. Ask only for facts missing from the page or contradictions that affect the post.
- **Workflow run:** reuse the event's `meetup-event-handoff.json`, `ocgroups-event-handoff.json`, and `artwork-manifest.json` when available, resolving file paths relative to each handoff. Missing handoffs or an unsaved Meetup form do not block promotion when the artwork and published ocgroups event are available. If Meetup status is supplied, record it accurately rather than claiming an unsaved form is a created event.

Optional producer references in this repository are [create-meetup-dot-com-event](../../skills/create-meetup-dot-com-event/SKILL.md), [create-ocgroups-event](../../skills/create-ocgroups-event/SKILL.md), and [create-arts-for-events](../../skills/create-arts-for-events/SKILL.md). Their presence is not a prerequisite for an independent run.

Use the corresponding published ocgroups event as the attendee-facing source and official RSVP destination. Verify that its URL opens the intended event and that the date, title, venue, speakers, and sponsors match. Do not use edit/draft links or reuse a prior event URL. Direct RSVPs to the verified public ocgroups event, not a nonpublic Meetup link.

Gather current event title, date, actual event start time, timezone, venue/room, session topics, speakers, official RSVP URL, and sponsor list. Use the published event's talk descriptions, or source Sessionize abstracts when available, for accurate summaries, preserving technical meaning and avoiding invented benefits or claims. Unlike event descriptions, promotional posts can use concise summaries. Never infer an event start from the first talk's start time or copy historical dates, rooms, speakers, or sponsors.

If the saved event, handoffs, or artwork disagree, identify the discrepancy and resolve it before labeling copy ready. Continue drafting unaffected portions while asking for missing information. Do not expose private organizer notes, contact information, authenticated URLs, or credentials in posts.

## Reuse artwork and sponsor details

Use the finished artwork supplied by the user; in workflow runs, select the current event's `meetup_banner` from the artwork manifest, normally 1200 × 675 px. Independent runs do not require that role, filename, or dimensions; check the supplied image's suitability and the actual LinkedIn upload preview. Check names, dates, sponsors, and readability. Do not use sanitized examples or narrow ocgroups banners as social-post images. Reuse existing suitable assets; if LinkedIn requires another format, flag that adaptation or use the artwork skill when authorized and supported. Do not silently crop out names, sponsor marks, or event details.

Apply the established sponsor rules, also recorded in the ocgroups skill: Station Austin only when hosting, Cast AI through December 31, 2027 by event date unless overridden, Ardan Labs as a standing sponsor, and others only when specified by the user. Adapt sponsor acknowledgments to the post length without inventing promotional claims. When all sponsor names cannot fit legibly, flag the proposed treatment for review; do not silently drop a sponsor requirement.

For LinkedIn organizer and volunteer tags, use the exact user-supplied profile mapping and mention-verification procedure in [references/linkedin-post.md](references/linkedin-post.md). Tag speakers and organizations only with verified platform-specific handles supplied by the user or found on their official profiles. Do not derive profile identities from names. Use plain display names when a handle is unavailable and note potential tags separately for the reviewer.

When Sessionize session information is available, check each associated speaker’s Sessionize profile, including co-speakers, for a LinkedIn profile URL. Use that speaker-supplied URL to identify and verify the native LinkedIn mention in the post’s Featured talks section, following [references/linkedin-post.md](references/linkedin-post.md). This check is conditional on available Sessionize information; independent runs still do not require Sessionize access. If the profile is inaccessible, no LinkedIn URL is specified, or the mention cannot be verified, retain the speaker’s name and report the unresolved tag rather than guessing.

## Compose the post

Follow [references/linkedin-post.md](references/linkedin-post.md), including the venue mention, Featured talks, logistics, sponsor thanks, official RSVP link, organizer/volunteer acknowledgments, CNCF thanks, and relevant hashtags. Use the supplied artwork. Match the current event's confirmed food/drink and venue arrangements. Do not invent urgency from an unverified capacity or “spots left” count. If the event has passed, flag that mismatch instead of drafting an upcoming-event invitation.

## Save the LinkedIn draft

After the permission check and event verification, inspect accessible Page drafts/history for the same event to avoid creating a duplicate. Resume an unmistakably matching draft when appropriate; clarify ambiguous matches. Compose as company page **97438051**, use the supplied post structure and verified native mentions, and attach the existing event banner. Saving this draft is authorized by invoking the skill; do not ask again merely to save it.

Inspect the text, author identity, tags, official RSVP link, and image preview. Use the live interface's actual save-draft action; do not assume that closing the composer saves it. Never click Post, Publish, or Schedule. Verify the draft exists and reopen it when possible to confirm saved text, image, and Page identity. If native saving is unavailable or fails, keep a local copy and report the limitation without claiming a saved LinkedIn draft. Do not use another service or publish as a workaround. After an uncertain save, check for the draft before retrying; make at most one evidence-based retry for the same failure.

## Add the Meetup link to ocgroups.dev when available

After preparing the LinkedIn draft, use the Meetup event URL from the user or available event context/handoff if one is available. Verify that it is a public attendee event URL for the same Kubernetes Austin event, matching its date and sessions. An unsaved form, organizer/edit URL, or historical reference event URL is not suitable. If no verified public Meetup URL is available, skip this step and report that it was skipped; do not create, save, or publish a Meetup event to obtain one.

Open the matching existing ocgroups.dev event in its organizer interface and edit it to include the verified Meetup URL. Use a dedicated Meetup/external-event link field if the live form provides one; otherwise add a clearly labeled “Meetup event: <verified URL>” link in the description, keeping ocgroups.dev as the official RSVP destination. Reuse an existing matching link instead of duplicating it. Preserve the rest of the event content and its existing publication state. Saving this specific link update is authorized as part of this skill; do not ask for separate permission merely to save it.

Save the edit, reopen the event, and verify the link persisted and targets the correct Meetup event. Do not click Publish, republish, or send an announcement to complete the update. If editing access is missing or the interface requires such an action, report the blocker and leave the update pending. Report whether the link was added, already present, skipped, or could not be saved, independently of the LinkedIn draft result.

## Verify and return the draft URL

Verify the saved draft's company-page identity, event facts, RSVP link, artwork, speaker spelling, sponsor acknowledgments, and native profile mentions. Capture the actual draft URL from the interface and confirm that it opens the intended saved draft when supported. Do not construct a URL from guessed identifiers or substitute a public-post URL for an unpublished draft.

Return the draft URL as a clickable link with a short message asking the user to review and publish when ready. After verifying the draft was saved, remind the user: “The LinkedIn post is saved as a draft, not published. You can access it when starting a new post as the Kubernetes Austin Page; open or resume the saved draft there, then review and publish when ready.” Describe the observed composer/draft controls if their labels differ, and do not claim this route was verified unless it was checked. Include the result of the ocgroups.dev Meetup-link update. Mention any unresolved tagging or content issue, and confirm that the post has not been published or scheduled. Do not generate a promotion plan, additional channel copy, or mandatory handoff files.

If LinkedIn exposes no direct draft URL, say so explicitly and provide the observed company-page draft-management URL with brief instructions for locating the draft. Label it as the drafts page, not a direct draft link. If neither is available, give the verified company page and navigation instructions without claiming a direct link. Never publish to obtain a URL.

If the draft could not be saved or verified, state the blocker and do not claim completion. A local text backup may be kept for recovery, but it is not a substitute for the requested LinkedIn draft and link. Missing Meetup information is not a blocker.
