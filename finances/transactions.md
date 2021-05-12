# Transactions

Transactions are the building blocks for your Lunch Money experience! A transaction represents the movement of money, whether that's between existing accounts or from your credit card to a merchant. 

## Frequently Asked Questions

1. How do I handle the case where others pay me back for a large bill that I paid for?
2. Is there a limit on how many transactions I can add?
3. How do I handle credit card payments?
4. What are some ways I can stay on top of manually adding transactions?

## Creating transactions

For details on automatic bank syncing, check [here](../importing-transactions/automatic-imports.md).

For details on CSV importing, check [here](../importing-transactions/import-via-csv.md).

For details on our Developer API, check [here](../importing-transactions/developer-api.md).

You can manually create transactions by clicking the "Add to Cash" button. "Cash" in this case refers to the default account of your transactions. If a transaction is not linked to any account, it is by default linked to Cash. Alternatively, if you have manually-managed assets set up, you should see options to add transactions to these accounts from the "Add to Cash" dropdown. You can also change the account of any transaction from the transactions details pane.

![&quot;Capital One Quicksilver&quot; is a manually-managed asset.](../.gitbook/assets/screen-shot-2020-06-20-at-1.15.53-pm%20%281%29.png)

There are also options to create transactions with specific properties:

1. **Create Transfer** can be used to represent the transfer of money from one manually-managed asset to another. Under the hood, this creates an expense for the originating account and a credit for the destination account, and groups them together so they show up as a net $0. This operation will also update the balance for associated accounts.
2. **Create from Recurring** can be used to automatically create a transaction linked to an existing recurring expense. \(For more details on recurring transactions, check [here](recurring-items.md#recurring-transactions)\)

## How do I handle the case where others pay me back for a large bill that I paid for?

We generally recommend using our grouped transactions feature for this use case. Assuming you footed the bill and your roommates end up paying you back their portion, group together all of these transactions and you should be left with a transaction that represents how much you paid. You can then treat this as a high-level transaction and assign a category to it.

![](../.gitbook/assets/group-gif-2.gif)

If you don't want to bother recording your friends' payment, you can **split** the transaction and simply categorize the portion paid by your friends to a new category called "Reimbursed" which is excluded from totals and excluded from budgets. This ensures that amount is not counted towards your own expenses.

## Is there a limit on how many transactions I can add?

There are limits to how many transactions you can upload on a single request but there isn't a limit on total transactions you add. This limit differs depending on the upload method \(CSV or API\).

For analytics and whatnot there's currently a hardcoded limit of 20,000 when fetching transactions, so if you have transactions over 10+ years, you may not be able to see the full picture if you do an "all-time" analysis.

## How do I handle credit card payments?

For credit card payments, usually made up of one debit to your cash account and one credit to your credit card, we recommend using the default [category](../setup/categories.md) **Payment and Transfers**. This category is set to be [excluded from totals](../setup/categories.md#exclude-from-totals) and [excluded from budgets](../setup/categories.md#exclude-from-budget), so these transactions should not affect your overall numbers or budget. Transactions in this category should also total up to $0 at the end of the month.

## What are some ways I can stay on top of manually adding transactions?

Here are some suggestions from our users on how to stay on top of manually adding transactions!

1. A recurring task in Things \(my task manager of choice\) that forces me to spend 5-10 minutes at the end of each week rounding things up.
2. My partner and I live in a primarily cash-based society. We keep a little pile of receipts in the office and every few days when it stacks too high, one of us will take it and input transactions manually. Takes about 10 minutes each time!
3. A Lunch Money user, Derek Reiff created [Milk Money](https://milkmoney.club/), a mobile-friendly solution for quick add on-the-go. \([Github source](https://github.com/dareiff/quick-add)\)
4. Create a Google form for inputting transactions, and every week or so, export the data as CSV and import it into Lunch Money

Finally, there is a secret, undocumented feature which we should really take time to improve upon– the [Lunch Money Quick Add screen](https://my.lunchmoney.app/transactions/new).



