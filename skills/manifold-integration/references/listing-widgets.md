# Listing Widgets

Individual widgets, prepended by `m-listing-`, are standalone widgets that pull specific data from a listing. They are exported to give creators more freedom as to how they want to organise their listing page.

## m-listing-attributes

Displays the attributes and their values for the token.

```html
<div
  data-widget="m-listing-attributes"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-bid-form

Shows an input field for the bid and a CTA. It displays nothing when the listing has ended (replaces the parent div with a comment, `<!---->`).

**IMPORTANT:** If the user selects this widget, you must ask them to provide the CONTRACT_ADDRESS. This is the smart contract address for the NFT listing and is required for this widget to function properly.

```html
<div
  data-widget="m-listing-bid-form"
  data-address="CONTRACT_ADDRESS"
  data-id="LISTING_ID"
  data-network="NETWORK"
  data-version="2"
></div>
```

## m-listing-bid-form-rich

Contains text for the minimum bid or offer/bid or offer status, the current bid currency, and the balance of the connected wallet. Displays nothing (`<!---->`) if the listing has ended.

```html
<div
  data-widget="m-listing-bid-form-rich"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-countdown

Displays a countdown ticker for the auction or the appropriate if the listing has not yet started/has ended.

```html
<div
  data-widget="m-listing-countdown"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-description

Loads the token's on-chain description.

The equivalent HTML code looks something like this:

```html
<div class="m-description">
  ::before
  <p>test</p>
</div>
```

The `::before` pseudo-component contains the “DESCRIPTION” header.

```html
<div
  data-widget="m-listing-description"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-interactions

**\[Updated name] In versions < 3.2.0:** `m-listing-bids`.

Shows the listing's bid/offer history as a table.

```html
<div
  data-widget="m-listing-interactions"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-image-expandable

Displays the listing media and a floating action button on the bottom-right to allow for expanding the media into a full-screen view.

<img src="https://268636785-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F8n4plerMUJrsrAiaKpc2%2Fuploads%2FkAyXTjHtcAl15KqbvS2a%2FMExpandableImage-3.2.0.png?alt=media&#x26;token=0ad365e2-b33c-4647-82d8-e7cdf9b81c9b" alt="" data-size="original">

```html
<div
  data-widget="m-listing-image-expandable"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

To customize the widget background, provide a [`data-media-background`](https://docs.manifold.xyz/manifold-for-developers/resources/widgets/marketplace-widgets/data-attributes#data-media-background) prop.

## m-listing-inventory

For ERC-1155 listings only. Displays the following text

```jsx
${ tokenRemaining } of ${ tokenMax } left
```

when `tokenRemaining > 0` with a progress bar above it.

When `tokenRemaining = 0`, we display

`tokenRemaining` and `tokenMax` come from the `listing` details (`listing.totalSold` and `listing.totalAvailable` respectively).

```html
<div
  data-widget="m-listing-inventory"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-links

Shows a list of links related to the listing.

```html
<div
  data-widget="m-listing-links"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-minted-counter

For ERC-1155s listings only. Displays the following text

```jsx
`${amount_of_tokens_minted} out of ${max_mintable_token_amount} minted so far`;
```

```html
<div
  data-widget="m-listing-minted-counter"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-name

Displays the name of the listed token in a span. Pulls the data from on-chain.

```html
<div
  data-widget="m-listing-name"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```

## m-listing-price

Displays the listing price’s label and the listing’s price, along with a bid status if the listing is an auction and the user has participated in the bid.

The listing label is one of the following:

- “Bidding Starts At” — if the listing is of type auction, is still ongoing, and does not have any bids.
- “Price” — if listing is not of type auction or if the listing has ended and there is a current bid amount.
- “Current Bid” — if the listing is of type auction, is still ongoing, and has at least one bid.
- “Winning Bid” — if the listing is of type auction, has ended, and has a current bid amount.

If the listing is a ranked auction, the price widget also displays the highest offer and the floor value.

```html
<div
  data-widget="m-listing-price"
  data-id="LISTING_ID"
  data-network="NETWORK"
></div>
```
