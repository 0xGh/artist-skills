---
name: manifold-integration
description: Integrates a NFT artwork auction or sale widget in the current project.
---

# Manifold Integration

Follow the instructions below when the user wants to integrate a Manifold auction or NFT drop in their website or page.

## Steps

It is very important to execute all the steps below in order.

### 1. Integration Page

If not provided, ask the user where they want to integrate: an existing page or a new one.

### 2. Integration Type

Ask the user whether they want to do:

1. A default integration - this renders a card with artwork and controls right below to bid or buy the artwork.

2. Custom integration - renders a custom layout with widgets placed where the user wants. The following widgets are available, show all of them to the user and ask which ones they want to add to the page:

- m-listing-name
- m-listing-image-expandable
- m-listing-description
- m-listing-attributes
- m-listing-price
- m-listing-bid-form
- m-listing-bid-form-rich
- m-listing-countdown
- m-listing-interactions
- m-listing-inventory
- m-listing-links
- m-listing-minted-counter

If the user chooses custom, show the entire list and offer to select which one (use checkboxes if available). Then ask them about the style of the integration or if they want you to make one up.

### 3. LISTING_ID and NETWORK_ID

Ask the user to provide the Manifold LISTING_ID and the NETWORK_ID.

Explain that in order to get a listing ID, the user must create a listing for their work in Manifold studio https://studio.manifold.xyz if they haven't done so yet - collecting the LISTING_ID at this stage is mandatory so you must ask to provide it.

Once they have a listing they should find the listing ID there.

The NETWORK_ID is the block chain id, eg Ethereum=1 etc. You may ask them to provide the name and convert it to chain id yourself to provide a smoother UX.

### 4. Widgets Integration

Note the examples before are in HTML but if the user is using another language (eg. JSX) you must adapt it to that language.

First, insert this code:

```html
<link
  href="https://connect.manifoldxyz.dev/3.3.0/connect.css"
  rel="stylesheet"
/>
<link
  href="https://marketplace.manifoldxyz.dev/3.5.18/marketplace.css"
  rel="stylesheet"
/>

<!-- optional customization styles and theming
<style>...</style>
-->

<script src="https://connect.manifoldxyz.dev/3.3.0/connect.umd.min.js"></script>
<script src="https://marketplace.manifoldxyz.dev/3.5.18/marketplace.umd.min.js"></script>
```

You will use LISTING_ID and NETWORK_ID collected earlier and set them in the templates.

Add the following to the body of the page:

```html
<div
  id="connect"
  data-widget="m-connect"
  data-delay-auth="true"
  data-network="NETWORK_ID"
></div>
```

If asked to hide the above, wrap it in a div with the following styles:

```css
position: absolute;
opacity: 1;
height: 0;
overflow: hidden;
pointer-events: none;
```

Depending of what the user choose (default or custom integration) you'll pick one of these two and add it to the body:

#### Default (card) Integration

```html
<div
  data-widget="m-card-catalog"
  data-id="LISTING_ID"
  data-network="NETWORK_ID"
></div>
```

#### Custom Integration

Refer to ./references/listing-widgets.md for the full reference and available code snippets integration docs.

### 5. Final touches

Tell the user to open the page in a browser and verify the widget renders correctly.

If something is not quite right, help them resolve potential issues. Suggest checking the browser console for errors (press F12 to open developer tools). You can find additional troubleshooting information in the widgets docs at https://docs.manifold.xyz/manifold-for-developers/resources/widgets

#### Customization & Styling

If everything looks good you must ask the user whether they want to customize the widget. If they want to customize the integration styles first you should check whether this can be done via custom properties.

Manifold expose a custom-CSS-properties based API that allows to customize widgets.
Refer to ./references/theming.md for details.

Otherwise you may generate additional CSS to fulfill the user request, making sure you use the same styling solution and pattern their page is already using, if any.
