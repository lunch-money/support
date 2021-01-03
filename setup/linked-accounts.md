# Accounts

## How are manually-managed account balances updated?

Manually-managed account balances are updated automatically when you add, remove or update a transaction assigned to that account.

For instance, if you import transactions via CSV, manually add a new transaction or use the developer API to bulk-insert transactions, the associated account balance will update accordingly.

Admittedly, sometimes we miss a few things and your account balance may not update perfectly. In this case, you can always go to the Accounts page and manually update the balance.

Note: making a manual update to your account balance will not create any new transactions.

## How do I merge a manually-managed account with a synced account?

### Why would I ever need to do this?

It may be that at some point, your bank integration ran into some issues and you had to switch to a manually-managed account to continue getting your transactions into Lunch Money.

Once the bank integration was fixed, you're now left with two accounts representing the same bank account– one which is synced, and one which is manually-managed. At this point, there is no longer a need for the manually-managed account.

At this point, you can use the **Merge Accounts** feature to combine both accounts into one. Note, this is an irreversible process so do ensure you pick the right accounts.

### How do I merge accounts?

To get to the **Merge Accounts** feature, go to the Accounts tab and click on the manually-managed asset you want to merge.  At the bottom, under "Actions", click the button that says "Merge with synced account".

This will take you to the next step. Here, you will choose the synced account to merge with. 

{% hint style="info" %}
You may only choose from a list of currently active accounts \(that is, healthy connections\) to merge with.
{% endhint %}

When we merge your accounts, we will migrate your transactions, recurring expenses and rules over to the new synced account. Import configurations will be deleted as they will no longer be needed. 

You'll likely have two sets of balance histories. On our end, we'll do our best to merge them but when there is a month for which both the manually-managed account and the synced account have a balance history, you'll need to let us know which one to choose. To help you decide this, you can head over to the Net Worth tab to see what balance histories we have for each of your accounts.

And that's it! It might take a few seconds to see changes, but your accounts should now be merged.

## My partner and I have joint accounts and they are showing up twice with duplicate transactions. How do I handle this?

Our account removal flow can help with this!

Get started with this button in the details pane of the duplicate account you'd like to remove:

![](../.gitbook/assets/screen-shot-2020-04-07-at-11.35.53-am.png)

You'll be asked if you want to remove all accounts associated with the bank or just one account.

![](../.gitbook/assets/unnamed.png)

After that you'll have the option to keep and transfer all existing transactions or remove them all.

