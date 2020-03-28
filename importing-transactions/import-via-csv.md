---
description: >-
  With almost 40% of our users based outside of US/Canada, CSV importing has
  been a popular choice for getting bulk transactions into Lunch Money.
---

# CSV Importing

## Getting Started

### What is a CSV file?

Most financial institutions will allow you to download a CSV export of your transactions. This is a plain-text file of your transactions details, such as date, amount and description, separated by a delimiter, typically a comma, hence, **c**omma-**s**eparated **v**alues. 

With this file, you can import your transactions into Lunch Money quickly and easily.

### How do I download my transactions?

For a quick guide on how to export transactions from your Apple Card, [click here](https://techcrunch.com/2020/01/21/apple-card-users-can-now-download-monthly-transactions-in-a-spreadsheet/).

If your bank allows it, there will typically be a way to download a CSV version of your statements or transactions between a certain date range within your bank's web portal. Try searching in the area where you can download statements. If you need help locating this, you may need to contact your bank.

### Where is the CSV Import Tool?

Head to the Transactions page and hit the "Add To Cash" dropdown. From there, select **Import from CSV**.

### What format should my CSV be in?

For a fast and successful CSV import, we recommend that your file includes the following columns with the associated header name:

* Date of transaction \(required\)
  * Header name: `date`
  * Format preferred: YYYY/MM/DD or YYYY-MM-DD
  * All other formats are possible, but we may have a hard time parsing them. \(It should still work, as there is an opportunity to teach our system which date format you're using. It just might take an extra step!\)
* Name of transaction \(required\)
  * Header name: `payee` or `description`
* Transaction amounts
  * See below.
* Transaction notes \(optional\)
  * Header name: `notes`

#### Formats supported for transaction amounts

We support three notations for indicating the amount for a transaction.

* **Use single column:** Using one single amount column, with positive/negative notation denoting credit or debit. Recommended headers include
  * `debit/credit`
  * `amount`
* **Use double column**: Using two columns column, with values in one representing debits and values in the other presenting credits. Recommended headers include:
  * `debit` and `credit`
  * `inflow` and `outflow`
* **Use by type column**: Using one single amount column with an associated column denoting the type. String in type column must be one of: outflow, inflow, debit, credit. Recommended headers include:
  * `debit/credit` and `amount`

The first two uses three columns in the CSV while the last two uses a single column. The double column formats interpret all numbers in absolute format which means a negative will not flip the amount.

As of now, these 4 columns are the only ones that you're able to import using CSVs. However, you can always use [Rules]() to help you assign categories or update payee names according to your preferences and habits.

### Recommended course of action

If this is your first time using the CSV import tool, we recommend that you only import one month's worth of transactions to start. Then, go to the Transactions page and categorize and organize your transactions as you please. As you do this, Rules will be created to remember your changes and apply them to future similar transactions. You can always go to the Rules page to audit these and make sure they are accurate.

When you go back to the CSV import tool and upload a second month's worth of transactions, you'll notice in [**Step 4: Review Transactions**](import-via-csv.md#step-4-review-transactions) that many of them will already be edited because you had rules set up from your first month! By uploading transactions in small batches, the less work you end up doing in the long run because your rules will get continuously refined. If you upload a year's worth in one go, you might get overwhelmed quickly.

## Step 1: Upload CSV

The first step is to select the manually-managed asset that you'll be importing your transactions into. If you haven't set up a manually-managed asset yet, you can do so by going to the Accounts page and hitting "Add Account or Asset".

After you select which asset the transactions are associated with, select which currency the transactions are in, and finally, upload the file.

{% hint style="info" %}
Configurations can be saved during Step 3, so next time you upload CSVs to the same asset, you get to choose whether or not to use the saved configuration in order to skip the next 2 steps.
{% endhint %}

There is a file size restriction of 200kb. We recommend you upload at most a few months' worth of transactions at a time.

## Step 2: Match CSV columns

We need to match the column data from your CSV file to columns used by Lunch Money. Use the drag-and-drop tool to correspond columns from your CSV file to the appropriate fields Lunch Money needs. We already try to match some columns for you based on whether or not you followed the recommended guidelines \(see **What format should my CSV be in?**\)

If your CSV file supports different notations for amounts, use the dropdown to select between single column or double column \(for more details, see **Formats supported for transaction amounts**\)

## Step 3: Review CSV settings

### Checking dates and amounts

At this stage, your CSV has been parsed by our system based on your settings. Double-check to make sure our interpretation of the dates and amounts are correct. Specifically, make sure that the amounts are correct in what they represent.

> Should a Starbucks expense be a credit? Nope! That's wrong– better flip the switch!

 This is very important to ensure that your transactions are imported correctly!

### Malformed lines

You'll also see a list of malformed lines from your CSV. These represent lines in your CSV that we determined to be missing required data, such as a date, payee name, or amount. If you believe any of these were done in error, you can always go back to Step 2 and fix your column matches. You can also check your CSV file to see if it's corrupted in any way. If you need assistance, we'd be more than happy to help troubleshoot!

### Other settings

You can choose to Apply Rules and Skip Duplicates. Both of these settings are recommended, so they are on by default.

Apply Rules will run your Rules against the transactions you import. Skip Duplicates will ensure that the same transaction will not be imported twice. We determine two transactions to be the same if the date, payee name, and amount all match exact.

Finally, you can choose to save your configuration. We will then remember your settings whenever you upload CSV files for this asset and you can skip steps 2 and 3!

## Step 4: Review Transactions

On this page, you will be presented with a list of transactions ready to be imported into your Lunch Money account exactly as they appear. This list of transactions has run through your rules and been de-duplicated per your settings. Duplicated transactions are shown at the bottom for your personal debugging.

This is your chance to review the transactions you're about to import. If the dates look funny or something else looks off, you can always go back to fix any settings. To prevent some transactions from being imported, de-select them.

## Step 5: Import Transactions

Hurrah! Your transactions have been imported. We did a best guess as to what your updated balance should be, but if we were off, you can enter the correct balance on this page.

## Troubleshooting

### How can I import categories?

We don't current support a way to import categories. This is because category names from your bank might not necessarily match your categories in Lunch Money easily. We'll be working on this feature soon, but in the meantime you can use Rules to help auto-categorize your transactions!

### I'm having issues with my CSV file.

Because there isn't a standard format for transactions in a CSV file, every bank exports transactions differently and we may sometimes encounter a CSV that we're not able to parse. However, we're working towards being able to support all variations and flavours of these CSV files. Please contact us at [support@lunchmoney.app](mailto:support@lunchmoney.app) with a snippet of your file and we'll work on getting it supported.

