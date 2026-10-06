# WordPress Template Mapping

The static build is structured so sections can move into Gutenberg/template parts without changing the content model.

| Current section | Suggested WordPress target | Suggested field keys |
|---|---|---|
| Header | `parts/header.html` / Header template part | `business_name`, `whatsapp_number`, `primary_cta_label` |
| Hero | Hero block pattern | `hero_eyebrow`, `hero_heading`, `hero_copy`, `hero_image`, `primary_cta`, `secondary_cta` |
| About | About block pattern | `about_heading`, `about_body`, `principles` |
| Training | Programs block/template part | `programs[]: title, description, availability_status` |
| Evolution roadmap | Process block/template part | `roadmap[]: title, description, order` |
| Facilities | Facilities block | `facilities[]: title, description, verified` |
| Gallery | Core Gallery or custom pattern | `gallery[]: image, alt, caption, authentic` |
| Membership inquiry | CTA pattern | `membership_copy`, `whatsapp_prefill` |
| FAQ | FAQ block/template part | `faqs[]: question, answer` |
| Contact | Contact template part | `whatsapp_number`, `address`, `hours`, `map_url` |
| Footer | `parts/footer.html` | `business_name`, `social_links[]`, `contact_fields` |

## Gutenberg hierarchy

Keep each major homepage section as a top-level Group block with a stable anchor: `about`, `training`, `process`, `facilities`, `gallery`, `faq`, `contact`. Prefer core Heading, Paragraph, Buttons, Group and Image blocks inside patterns. Avoid deeply nested custom wrappers.

## Verification rule

Treat `address`, `hours`, `pricing`, `facilities`, `coaches`, `testimonials`, `certifications`, `social_links` and business-owned gallery claims as publishable only after verification. A custom field such as `verified` can gate rendering for repeatable facility/social records.
