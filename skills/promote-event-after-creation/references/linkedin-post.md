# LinkedIn company-page draft

Target page: https://www.linkedin.com/company/97438051

Use this structure for the main event announcement, replacing the example's event-specific facts with the current published ocgroups event. Keep readable blank lines between paragraphs, talk entries, logistics, sponsor thanks, RSVP, organizer thanks, and hashtags. Preserve exact session titles and speaker display names; the introductory topic summary can be concise and source-grounded.

## Mentions

Tag the current venue in the opening invitation using the correct LinkedIn Page selected from the native mention picker. Use verified native mentions for speakers, sponsors, organizers, and CNCF when available. A pasted name, profile URL, or literal `@Name` is not a verified tag. Check the selected identity rather than choosing the first similarly named result. If a tag cannot be resolved, keep a plain name, report the unresolved mention, and do not claim it was tagged.

When Sessionize session information is available, inspect the Sessionize profile for every speaker associated with those sessions and look for a LinkedIn URL in their social/profile links. Use any LinkedIn URL explicitly listed there as the identity reference for that speaker’s native mention in the Featured talks “by” line. Check co-speakers individually; do not assume a session has only one speaker. Match the mention picker result to the linked profile and verify the resulting mention target, including after reopening the saved draft when supported. If supplied identity sources conflict, resolve the discrepancy before selecting a tag. If the Sessionize profile is inaccessible, has no LinkedIn link, or LinkedIn cannot resolve the verified profile, use the speaker’s plain name and report the missing or unresolved tag. Do not infer a profile URL from a name or make Sessionize access a prerequisite for an independent run.

Use the following user-supplied organizer/volunteer profile mapping for the acknowledgment. Keep Deepak V. and Goutham K. from the earlier supplied roster alongside the seven profiles supplied afterward, unless the user changes the roster. This roster is distinct from the five Meetup event hosts.

| Acknowledgment name | Required LinkedIn profile |
| --- | --- |
| Rafael Brito | https://www.linkedin.com/in/rafaelbrito/ |
| Harsha Thirimanna | https://www.linkedin.com/in/harshathirimanna/ |
| Myroslav Mishov | https://www.linkedin.com/in/myroslavmishov/ |
| Srihari Nagaram | https://www.linkedin.com/in/srihari-nagaram/ |
| Cristobal Nevares | https://www.linkedin.com/in/cris-nevares/ |
| Sammy Cheung | https://www.linkedin.com/in/sammy-cheung/ |
| Akshay Mittal, Ph.D. | https://www.linkedin.com/in/akshaymittal143/ |
| Deepak V. | https://www.linkedin.com/in/yesdeepakverma/ |
| Goutham K. | https://www.linkedin.com/in/goutham-kanags/ |

For each person, select the native LinkedIn mention whose profile matches the supplied URL. Use the profile's displayed name in the picker if it differs from the acknowledgment name (for example, Cris versus Cristobal); the profile identity is authoritative. Verify the resulting mention target using the visible profile link or supported profile preview. Do not accept a same-name match without confirming identity, and do not treat pasting these URLs as tagging.

After saving, reopen the draft when supported and confirm that all selected mentions remain native mentions targeting the correct profiles. Verify each intended profile URL and displayed mention name; report any unresolved match to the user. If LinkedIn does not offer a profile in the mention picker or the target cannot be verified, leave the name as plain text only as a clearly reported unresolved item. Tell the user exactly which person still needs tagging, and do not claim all organizers are correctly tagged or the draft is fully ready while a required mention remains unresolved. Never substitute another person or silently omit a roster member.

## Post template

```text
🚀 Join us for the next Kubernetes Austin meetup on {{MONTH_DAY}} at {{VENUE_NATIVE_MENTION_OR_NAME}}.

This month, we are bringing the community together for {{CONFIRMED_HOSPITALITY_AND_NETWORKING}} and {{SESSION_COUNT}} practical Kubernetes sessions focused on {{SOURCE_GROUNDED_TOPIC_SUMMARY}}.

🎤 Featured talks:

{{SESSION_1_EXACT_TITLE}}
by {{SESSION_1_SPEAKERS}}

{{SESSION_2_EXACT_TITLE}}
by {{SESSION_2_SPEAKERS}}

Whether you are {{RELEVANT_AUDIENCE_INTERESTS}} or just starting your cloud native journey, this is a great opportunity to learn and connect with the local community.

📍 {{VENUE_NAME}}, {{CITY}}
📅 {{FULL_EVENT_DATE}}
🕕 {{EVENT_START}} – {{EVENT_END}} {{DATE_CORRECT_TIMEZONE_LABEL}}

{{CURRENT_VENUE_AND_SPONSOR_THANKS}}

Everyone is welcome. Come join us and stay connected with the latest in Kubernetes, CNCF, and cloud native technologies.

RSVP here: {{VERIFIED_OCGROUPS_PUBLIC_EVENT_URL}}

❤️ Thanks for all the active organizers and volunteers {{ORGANIZER_MENTIONS_OR_NAMES_SEPARATED_BY_VERTICAL_BARS}}

Thanks {{CLOUD_NATIVE_COMPUTING_FOUNDATION_CNCF_MENTION_OR_NAME}}

#Kubernetes #CloudNative #CNCF #GitOps #PlatformEngineering #DevOps #OpenSource #AustinTech #KubernetesAustin
```

Repeat/remove talk blocks for the actual session count. Use the actual event start/end times, not assumed talk slots, and derive CST/CDT from the event date and America/Chicago timezone. Keep the template's community hashtags; retain topical hashtags such as GitOps or PlatformEngineering only when relevant to the current sessions. Render real `#` hashtags, not the copied export prefix `hashtag#`.

For sponsor thanks, apply the standing event sponsor rules and current overrides. Do not reuse Zynga, Clowder Space, Mara Ruvalcaba, the June date, or the example's speakers unless they are part of the current event. Thank the actual venue for hosting; credit food/drinks to a sponsor only when that role is confirmed. Include Ardan Labs and the applicable Cast AI/Station Austin acknowledgments; do not invent sponsor responsibilities.

Upload the current event's finished meetup.com banner and inspect its preview. Adapt text formatting to the LinkedIn composer; do not leave Markdown markers, template placeholders, or review notes in the actual post. Save one main announcement draft and return its verified draft URL to the user. Do not create other posts or a promotion schedule. Never click Post or Schedule.
