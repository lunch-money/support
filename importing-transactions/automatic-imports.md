---
description: >-
  We support automatic imports from your bank via a third-party service, Plaid.
  Currently, this feature is only available to most US and Canadian-based banks.
---

# Automatic Imports

## Support for international banks

We'd love to integrate with international banks for automatic imports, but unfortunately we're running into blockers due to data privacy laws as we're a Canadian-based company. 

Our highest priority right now is connecting to European and Australian banks for automatic imports. We're actively working with a number of data providers and waiting patiently for them to work with local regulators and hopefully pave the way for us one day to support our international users with automatic imports.

## FAQ

### Why does my account keep requiring me to relink/re-authenticate?

This is most likely related to a multi-factor authentication setting that you have enabled with your bank. In general, Plaid can handle 2FA. However, if a bank requires a unique one-time password on every login or otherwise very frequently, then Plaid will have difficulty maintaining connection. We always suggest checking to see if your bank provides you with app passwords or a setting to enable trusted devices– those would help Plaid maintain the connection!

### Why am I not seeing any transactions for my brokerage/investment accounts?

We're currently not able to get transactions for brokerage/investment accounts. We may be able to get the latest balance if the institution your account is associated with is not deemed an "investment-only bank". If it is, then we suggest creating a manually-managed asset to track the balance yourself.

The reason for this is simply because fetching transactions for brokerage/investment accounts costs  us much more money. At this point, we are choosing to focus mainly on tracking expenses and we are not pursuing to become an investment or portfolio tracking app.

