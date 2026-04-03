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
- `curator.walletAddress` (wallet address starting with `0x`)
- optional `curator.links` entries with:
  - `type`: `twitter` or `instagram` or `web`
  - `url`
  - display `text` (optional)

Apply those values to the target file.

### 3. Explain How to Add Gallery Entries

After basic details are set or when editing an existing gallery explain how to add artworks in the `listings` area. Use simple examples.
Before asking for any works provide the full add-works guidance in one message then ask the user to send their full list.

Explain that each artwork entry can be:

- a share link like `https://share.manifold.xyz/listing/<id>`
- a listing ID like `12345` (generally 5-6, to not confuse with longer ids which manifold uses for other things)
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
  - se the information from the "Referral Behavior" section to explain the core proposition of this feature concisely
  - explain this is optional
  - explain this adds a "Recommended Gallery" link at the bottom of the page
  - explain opening it passes the current curator wallet as `?ref=0x...` i.e. referral

### 4. Referral Behavior

Explain this clearly in non-technical words:

- When someone clicks a listing from the gallery the referral wallet is added automatically
- By default all listing links use `config.curator.walletAddress`
- If the gallery page URL includes `?ref=0x...` then every second listing uses that `?ref` wallet and the other listings still use the curator wallet
- If `config.recommendedGallery` is set then the page shows a "Recommended Gallery" link and appends `?ref=<current-curator-wallet>` when opening it
- One-line benefit to tell users: this helps curators cross-promote each other and share referral upside across linked galleries
- Referral sales are expected to pay 6.9% if Manifold referral support is active at purchase time and still supported by Manifold

### 5. Ongoing Edits

For future edits change only what the user asks for:

- config fields
- listing entries
- optional per-entry custom descriptions

Keep the gallery single-page and the code (excluded configuration) unchanged unless the user asks to change layout.
