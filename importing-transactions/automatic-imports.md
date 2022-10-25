---
description: >-
  We support automatic imports from your bank via a third-party service, Plaid.
  Currently, this feature is only available to most US and Canadian-based banks.
---

# Automatic Imports

## Introduction

We rely on [Plaid](https://plaid.com), a third-party banking provider, to import transactions and balances for your bank accounts. Plaid is a popular, secure and established service also used by a slew of other personal finance apps on the market.&#x20;

If automatic bank syncing is not available in your region, you may instead take advantage of our [CSV import tool](import-via-csv.md) or [developer API](developer-api.md) to get bulk transactions into Lunch Money.

## Frequently Asked Questions

1. [I can't connect to my institution!](automatic-imports.md#i-cant-connect-to-my-institution)
2. [Why does my account keep requiring me to relink/re-authenticate?](automatic-imports.md#why-does-my-account-keep-requiring-me-to-relink-re-authenticate)
3. [Why am I not seeing any transactions for my brokerage/investment accounts?](automatic-imports.md#why-am-i-not-seeing-any-transactions-for-my-brokerage-investment-accounts)
4. [My institution is not listed.](automatic-imports.md#my-institution-is-not-listed)
5. [What information do you store when I sync my bank account?](automatic-imports.md#what-information-do-you-store-when-i-sync-my-bank-account)
6. [How do I stop importing transactions for a synced account and only track manually?](automatic-imports.md#how-do-i-track-transactions-manually-for-a-synced-account)
7. [How do I manually insert historic transactions to fill in the gaps for my synced account?](automatic-imports.md#how-do-i-manually-insert-historic-transactions-to-fill-in-the-gaps-for-my-synced-account)
8. [I was tracking my transactions manually, and now I'm using bank syncing. How do I reconcile my transactions?](automatic-imports.md#i-was-tracking-my-transactions-manually-and-now-im-using-bank-syncing-how-do-i-reconcile-my-transactions)

## Support for international banks

Through our partnership with [Plaid](https://plaid.com), we currently support automatic bank syncing for most financial institutions based in the following countries:

* USA
* Canada
* France
* The Netherlands
* Spain
* Ireland
* Germany (limited release)

In the meantime, we have a[ developer API](https://lunchmoney.dev) which we're hoping will bridge the gap between Lunch Money & international banks. We already have a few European banks supported via community-made open source plugins such as [bunq](https://github.com/markjongkind/bunq-to-lunchmoney) and [Monzo](https://github.com/joehoyle/monzo-to-lunch-money)!

We also highly recommend using our [CSV import tool](import-via-csv.md) which we have been putting a lot of effort towards making as seamless as possible. Almost 40% of our users are international users so this method has been proven sustainable for long-term use on Lunch Money!

## Fetching the latest data

Balance and transactions are fetched automatically when we receive a notice via webhook from your bank & Plaid (our third-party banking provider) that there are new transactions. On rare occasions, this webhook doesn't arrive or somewhere along the line, something hiccups and we don't fetch the latest. In this case, you can manually trigger a fetch from the Transactions page by clicking on the refresh icon:

![](../.gitbook/assets/screen-shot-2020-04-09-at-4.26.48-pm.png)

This operation is also automatically triggered if you go to the Transactions page and we determine that it's been over 12 hours since we last fetch transactions for your accounts.

You can get more information on when we last fetched transactions & balances for your accounts from the [Accounts](https://my.lunchmoney.app/accounts) page.

## Recovering revoked accounts

Connections get revoked if you don't enter your billing information within 5 days of your trial ending.

When a connection gets revoked, that means that we have voluntarily given up our access to your bank data. To continue with bank syncing, you'll need to link a brand new connection to your bank. Your revoked/error'ed connections are not recoverable.

To merge the data from your revoked connections with the new ones, follow these steps:

1. Check each of your revoked/error accounts and note down the date of the last successfully imported transaction.
2. Go through the removal flow for each of your revoked/error accounts and when prompted, elect to keep account data and move to a new manually-managed account.
3. Connect to your bank(s). When prompted, set the "earliest import date" to be the last import date as noted in step 1 and enable "Block importing before this date" to prevent duplicates. This will make sure that the newly synced account will only import transactions after this date!
4. Once that's done, click on your newly created manually-managed assets from step 2. For each one, click on "Merge with synced accounts" and choose the associated synced account. This will merge together transactions, recurring items, rules and balance histories.

## FAQ

### I can't connect to my institution!

Do you have an **ad-blocker or other browser extensions** that disable Javascript or otherwise intended to modify behaviour of websites? If so, we've heard reports that these can affect the ability to connect to an institution. We suggest turning these off temporarily when attempting to connect.

Do you have **2FA set up** on your account? If so, institutions requiring a new one-time password on every login are not currently supported due to the nature of the connection.

Do you have multiple **secret questions & answers** set up? If so, it may require you to connect a few more times in order to collect all the answers to all the questions you have set up.

For any other issues, feel free to reach out to support@lunchmoney.app or use the in-app "Submit a bug or feedback" button at the bottom right of every page.

### Why does my account keep requiring me to relink/re-authenticate?

This is most likely related to a multi-factor authentication setting that you have enabled with your bank. In general, Plaid can handle 2FA. However, if a bank requires a unique one-time password on every login or otherwise very frequently, then Plaid will have difficulty maintaining connection. We always suggest checking to see if your bank provides you with app passwords or a setting to enable trusted devices– those would help Plaid maintain the connection!

### Why am I not seeing any transactions for my brokerage/investment accounts?

Automatically importing transactions for some investment accounts is supported but not enabled by default.

If you have automatically synced investment accounts that are supported for this feature, you'll see an option to "Sync transactions (beta)" under "Advanced Settings" in the Accounts page. Note that you'll need to enable this option for each investment account you want transactions for.

### My institution is not listed.

Unfortunately, we don't have control over which institutions are supported by Plaid.&#x20;

According to Plaid, they are not currently prioritizing new institution builds. Their recommendation is to reach out to your financial institution on their behalf and ask them to submit a contact request via [https://plaid.com/plaid-exchange/](https://plaid.com/plaid-exchange/) if they are interested in collaborating directly with Plaid on an API integration.

### What information do you store when I sync my bank account?

If you use the automatic bank syncing feature, we store the following information about your account:&#x20;

1. The account name
2. The account mask (last four digits)
3. The account type and subtype (for example, loan and mortgage)

And then we periodically receive transactions and balance updates.

We do not store, nor do we have access to the account holder's name or other personal information, or account routing numbers.

### How do I stop importing transactions for a synced account and only track manually?

If your transactions were automatically syncing with your bank, and something happened such as a service disruption, you can temporarily track transactions manually for a synced account.

It's important to note that synced accounts inherently do not support manual transactions. So, you'll need to convert the synced account to a manual account. To do this, you'll need to go through the account removal flow and opt to keep all existing data.

Click on the account in question and scroll down in the side pop-up to where it says "Remove  account". Decide if you only want to manual track for this account, or all other associated accounts within the same institution.

Once you've made your selection, make sure you have the following selected to keep all your existing data and to assign it to a new manually-managed asset. If you have an existing one that you want to use, you may also choose that one. We also recommend that you elect to keep your balance history (this is asked in the next screen).

### ![](<../.gitbook/assets/Screen Shot 2022-04-25 at 2.39.57 PM.png>)

Once you've gone through this flow, you are able to treat this account as a manually-managed account and add transactions to it. The balance will automatically update, and you may also reconcile your balance at any point from the Accounts page.

{% hint style="info" %}
Note: this option makes it so that you stop attempting to sync this account automatically. If you'd like to continue automatic syncing of transactions, see the next FAQ.
{% endhint %}

### How do I manually insert historic transactions to fill in the gaps for my synced account?

Are you automatically syncing new transactions for an account but you're missing historical transactions that you'd like to manually import, either via our CSV tool or developer API?

First, create a new, temporary manually-managed account and import your transactions to this manual account.

Next, click on the manually-managed account within the Accounts page, and locate the "Merge with synced account" option under Actions:

![](../.gitbook/assets/screen-shot-2021-05-24-at-3.09.46-pm.png)

This will merge your temporary manually-managed account and its transactions with the selected synced account. It's important to do this only for historical transactions because our system will not automatically detect or de-duplicate manual transactions with newly imported transactions.&#x20;

### I was tracking my transactions manually, and now I'm using bank syncing. How do I reconcile my transactions?

If you were tracking your transactions manually while your bank was either not supported for syncing or undergoing downtime, you may want to reconcile your transactions with the new bank connection.

The first step is to identify the date of the latest transaction you added for this account. **Do this before you link to your bank**. When prompted, set the "Earliest import date" to the date of the latest transaction and select "Block importing before this date".

{% hint style="info" %}
#### What if I already linked my new bank?

Never fear! You can set these fields by clicking into your account. This will prevent future transaction updates from importing older transactions. You'll then need to manually remove your duplicates. You can do this easily by identifying duplicate transactions using the filtering feature in the Transactions page.

For example, set a filter to only show transactions from your new synced account and your old manually-managed account. Sort by date and use the bulk-selection method to bulk-delete transactions.
{% endhint %}

![After you connect to your bank, you'll see this pop up. Make sure you enter the earliest date to import and block importing before this date.](../.gitbook/assets/screen-shot-2020-11-27-at-1.00.52-am.png)

This makes it so that our system will not automatically import transactions before a certain date. Since this date is set to the date of your most recent manual transaction, there should be no duplicates imported.

Once your new bank connection is active, click into your old manually-managed asset and choose the option "Merge with synced account".

![](../.gitbook/assets/screen-shot-2021-05-24-at-3.09.46-pm.png)

Follow the instructions and make sure to merge over all transactions and balance history for a seamless experience!

