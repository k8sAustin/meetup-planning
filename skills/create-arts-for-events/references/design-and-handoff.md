# Design reference and artwork handoff

## Visual system

The supplied examples establish teal backgrounds, white text, red portrait rings, an orange sponsor label, dark navy headline text, and the rainbow Kubernetes Austin ATX logo. The meetup.com example also has a pale teal upper band, white lower section, teal name ribbons, a small calendar block, and a multicolor footer. Use the examples for visual relationships; exact typography and spacing may adapt to the current content.

The canonical examples are:

- `../assets/examples/ocgroups.dev-short-banner-mobile-sanitized.png`: ocgroups.dev short banner for mobile composition.
- `../assets/examples/ocgroups.dev-long-banner-sanitized.png`: ocgroups.dev long banner composition.
- `../assets/examples/meetup.com-banner-sanitized.png`: meetup.com banner composition.

These are sanitized raster layout references, not editable production templates or authoritative logo masters. They were edited using built-in image generation to replace sponsor marks and personal data with neutral placeholders. Generated references may include white margins and extra placeholder sponsor slots; neither is a production requirement. Reference image dimensions differ from the required output sizes; always export new event graphics at the sizes in `SKILL.md`. Prefer a supplied official Kubernetes Austin logo asset for production, using the retained reference branding only as visual guidance.

### ocgroups.dev banners

Maintain three clearly separated zones: community identity, sponsors, and speakers. Place `k8saustin.com` beside the community logo. Use the current ocgroups.dev templates as the baseline for community branding. Keep both elements vertically centered, preserve logo proportions, and maintain clear gaps between the logo, website, and sponsor group. Group sponsor logos under or beside `Sponsored By`, with balanced apparent sizes and clear space. Use circular authentic headshots with red outlines and names underneath, matching each name to its portrait. Preserve this arrangement in both widths without distorting any asset. The narrow references do not include session titles or dates; do not add them by default.

### meetup.com banner

Place the speaker row in the upper area, with large portraits and readable name ribbons. Put exact session titles in the white central area using navy text, with a clearly visible `&` between every adjacent pair of titles. Prefer a separate centered line for each `&`, keeping each title visually grouped even when it wraps. For example: title one, then `&`, then title two. With three talks, add another `&` before title three; with one talk, omit the separator. The separators are presentation elements and must not be appended to session titles in the manifest. Reserve the lower area for the current event date, confirmed start time if supplied, and sponsor group. Retain community branding and the multicolor footer. Adjust row heights, title line breaks, and portrait sizes to the real speaker count and title lengths. If the content cannot fit legibly, surface the specific conflict and offer a layout adjustment or seek approval for shortened display titles.

Dates and times must be based on current event input. If the requested calendar motif displays only month/day, still record the full year in the handoff. Never inherit the example's month, day, or time. The retained community website is branding, not an event-specific registration URL.

## Delivery contract

Use the user's requested output location; otherwise create a distinct event output folder such as `event-artwork/YYYY-MM-DD/`, outside the skill package. Preserve existing outputs by using a new revision folder when necessary.

Deliver:

- `ocgroups.dev-short-banner-mobile.png` — 1220 × 192, unless explicitly overridden.
- `ocgroups.dev-long-banner.png` — 2428 × 192, unless explicitly overridden.
- `meetup.com-banner.png` — 1200 × 675, unless explicitly overridden.
- `artwork-manifest.json` — machine-readable handoff, with relative file paths.

The manifest is a local contract for the future event-creation skill, not a CNCF or Meetup API schema. Include:

| Field | Content |
| --- | --- |
| `schema_version` | `1` |
| `status` | `ready` only after all graphics are verified and required inputs are resolved; otherwise `draft` |
| `event` | `community`, ISO `date`, `start_time` and IANA `timezone` or null when unknown, and `title` only if supplied |
| `sessions` | Array of exact `title`, `speaker_ids`, and a public `source_url` when available |
| `speakers` | Array of stable local `id`, exact `display_name`, and public `photo_source_url` when available |
| `sponsors` | Array of `name` and public `logo_source_url` when available |
| `artworks` | Array of `role` (`ocgroups_short_mobile`, `ocgroups_long`, `meetup_banner`), relative `file`, actual `width`, `height`, `mime_type`, and concise factual `alt_text` |
| `missing_inputs` | Array of unresolved facts/assets; empty for a ready handoff |
| `notes` | Material layout decisions, explicit size overrides, and source limitations |

Use null for unavailable source URLs rather than inventing them. For authenticated Sessionize pages or locally supplied assets, record a brief source note without cookies, tokens, private URLs, or absolute personal filesystem paths. Speaker IDs are internal handoff identifiers, not guessed Sessionize IDs. Session-to-speaker mappings must reflect the source.

The future publishing skill should read this manifest, resolve relative paths from its directory, and use the matching artwork roles for event listings. This skill ends with the artwork handoff.
