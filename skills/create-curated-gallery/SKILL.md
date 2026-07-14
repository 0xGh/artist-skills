---
name: create-curated-gallery
description: Creates, updates or configures a curated NFT gallery page using Manifold listings.
---

# Create Curated Gallery

Use this when the user wants a simple one-page curated NFT gallery from Manifold listings.
Write in plain language and avoid developer jargon.

## Steps

Run steps in order.

### 1. Target File Selection

Pick the gallery file in this order:

1. If the user points to an existing gallery file use that file and help them edit it.
2. Else if `curated.html` exists use it.
3. Else if `curated/index.html` exists use it.
4. Else create a new gallery file by copying `./template.html` from this skill folder to `./curated.html` in the current working folder.

Read the gallery file.

### 2. Ask for Gallery Configuration First

If a new file was created from the template ask only for basic gallery details first.
Do not ask for artwork listing links or IDs yet.

Ask for:

- gallery `title`
- gallery `description` (optional)
- `curator.name`
- optional `curator.links` entries with:
  - `type`: `twitter` or `instagram` or `web`
  - `url`
  - display `text` (optional)
- whether to keep Manifold embeds enabled with `embed: true` or use external links with `embed: false`
- optional `theme`: `dark` or `museum`

Apply those values to the target file.

### 3. Explain How to Add Gallery Entries

After basic details are set or when editing an existing gallery explain how to add artworks in the `listings` area. Use simple examples.
Before asking for any works provide the full add-works guidance in one message then ask the user to send their full list.

Explain that each artwork entry can be:

- a share link like `https://share.manifold.xyz/listing/<id>`
- a listing ID like `12345` (generally 5-6 digits, to not confuse with longer ids which Manifold uses for other things)
- a direct Manifold link like:
  - `https://manifold.xyz/@.../id/<id>`
  - `https://gallery.manifold.xyz/<contract>/<tokenId>` (this might not work)

Also accept user-friendly shorthand input when the user is not technical:

- `value custom text...`
- Parse the first token as the listing value (URL or ID)
- Parse the rest of the line as custom text
- If custom text is present store it in the internal override format in the file

Tell them they can send:

- a list of listing URLs or IDs
- optional custom text after each URL or ID on the same line
- clarify that only auction listings are supported at the moment

Also explain:

- By default each artwork shows its actual description from Manifold
- If they provide custom text that custom text replaces the default description for that artwork

After the user has provided all required values ask one follow-up:

- optional `recommendedGallery` URL:
  - explain this adds a "See More Artworks" link at the bottom of the page
  - explain this is optional

### 4. Gallery Behavior

Explain this clearly in non-technical words:

- The page loads Manifold listing data from the configured listing IDs or URLs
- If `embed` is true the page shows Manifold listing widgets for live auctions
- If `embed` is false the page shows simple external listing links
- If `recommendedGallery` is set the page shows a "See More Artworks" link at the end

### 5. Ongoing Edits

For future edits change only what the user asks for:

- config fields
- listing entries
- optional per-entry custom descriptions

Keep the gallery single-page and the code (excluded configuration) unchanged unless the user asks to change layout.
