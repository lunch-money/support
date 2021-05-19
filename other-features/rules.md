# Rules

## What is a rule?

Rules are created to automatically update certain fields of a transaction based on some criteria. The purpose of a rule is to keep your transactions organized and categorized in the way that you choose.

A rule is made up of two parts: the criteria and the effect.

### Rule criteria

The rule criteria determines which transactions a rule should apply to. For instance, if we want to automatically set the category to `Ridesharing` for transactions where the payment name contains the word `Uber` because every Uber transactions is named differently, the rule criteria would be `payee name contains 'Uber'`.

We support the following for building your rule criteria:

* Payee name
* Amount range \(between, &gt;, &gt;=, &lt;, &lt;=, =\) and type \(expense or income\)
* Day range \(supports date wrapping as well\)
* Imported from which account
* Notes

Category rules can match **payee** and **notes** in one of three ways: contain, start with, or match exactly.

| Criteria | Name | Will match |
| :--- | :--- | :--- |
| contains 'Market' | Farmer's Market | Yes |
| contains 'Market' | FRESH MARKET CO. | Yes |
| contains 'Market' | Marketing Class 101 | Yes |
| starts with 'Uber' | UBER BV | Yes |
| starts with 'Uber' | Uber Eats | Yes |
| starts with 'Uber' | SQ\* UBER | No |
| exactly 'Walgreens' | Walgreens | Yes |
| exactly 'Walgreens' | WALGREENS | No |

### Rule effect

The rule effect determines how a transaction which means the rule criteria will change. Currently, you can automatically update the following fields:

* Payee name
* Note
* Category
* Tag\(s\)
* Link to a recurring expense
* Mark as reviewed

You may also use a rule to split a transaction. Note that splitting and updating the original transaction properties are mutually exclusive!

## Rule creation

A rule can be created in various ways:

1. A category rule is automatically created with a “match exactly” rule whenever you change the category of a transaction. This can be turned off in the Settings.
2. A suggested rule is automatically created when you rename a payee.
3. When you edit a transaction, you'll also be presented with an option to create a new rule based on the changes you just made. You can always edit these later in Rules.
4. When a new recurring expense is created, a system rule is automatically created to match transactions to recurring expenses. We do not recommend editing or deleting these, but the option is there if you need to make some adjustments to ensure they match your recurring transactions.
5. Lastly, you can create a new rule manually by clicking “Add a new rule” in the Rules page.

## Applying rules

A rule in Lunch Money is applied to all automatically imported transactions. For manually-imported transactions, you can toggle the option to apply rules in the CSV import tool.

When editing a transaction whose payee name matches many others, you have the option to apply the same changes to those transactions. This will appear as part of a notification system and will show you exactly which transactions will be affected with the option of de-selecting some.

You also have the option to apply rules retroactively via the “Apply” button next to each rule in the Rule page. Before applying, Lunch Money will let you know which transactions will be updated with the option of de-selecting some.

### Rule Priority
Rules are additive and will be applied in priority order with 10 being the least important and 1 being the most important. For example, suppose there are 2 rules that both update a transaction's "Payee Name". The rule with priority 10 will be overridden by the rule with priority 1, since it is less important.
