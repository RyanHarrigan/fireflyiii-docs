# Organizing transaction

## Budgets

Once you start creating transactions you start to realise that in a month, the same kind of stuff always comes back. For example:

* Bills
* Groceries
* Going out for drinks
* Clothing

Likewise, you should start to notice that you always spend the same amount of money on these things. That amount may be too high for your tastes, and you may want to change that. Or at least, keep track of it.

These things are **budgets**. Budgets are a kind of "category" that come back every single month. Bills are recurring (rent, water, electricity). You buy groceries every day. You need to pay rent every month.

In what is called an [envelope system](http://en.wikipedia.org/wiki/Envelope_system) you stuff money in envelopes and spend your money from those envelopes.

Firefly III uses this method, which means you can create "envelopes" for any period. Example: € 200 for "groceries" or € 500 for "bills" every month. On the budgets-page you can create budgets and set envelopes each month (or each week or year). Expenses can then be assigned a budget, and you will see on the budget page how well you are doing.

There is even a special budget report.

Each budget is valid for the current time period only (look to the top right). First, set the amount that is available to you by clicking the pencil icon next to *"Available in \~\~\~"*. By default, this is zero.

Then, create some budgets with the "Create a budget" button either in the center of the screen or in the top right menu. All you need for a budget is a name.

Once you've created some budgets you can set the amount of the budget using the input below the name. If you have already spent money in a budget, this will be shown as well. You can see that the top blue bar will update. It will be blue if you have budgeted all the money available, and turn red / orange if you budget more money than you have.

Both the amount available and the amount budgeted are for a specific period: if you go back a month or forward a month, both of these amounts are reset. Firefly III will remember what you've set the amounts to of course, but every period has their own amounts.

In your preferences, you can change this range to be weekly, or even yearly.

This is a different (and better!) approach than YNAB. Yes, [I am opinionated about this](../more-information/zero-based-budgeting.md).

### Adding money to a budget

You can't add money to a budget through a deposit. A reimbursement or a returned item cannot be used to restore the budget.

Since you spent the money, the money in the budget is gone. If you "unspent" the money you can do a few things:

- Edit the original transaction and remove the amount you got back
- Make the budget larger

### Automatic budgeting

Firefly III can automatically manage your budgets. Edit or create a budget and pick from the following options:

#### Fixed amount

Firefly III will create a new budget amount every selected period. The exact behavior depends entirely on your settings:

If you set it to "monthly", € 200 Firefly III will give you an automatic budget amount of € 200, valid for one month, every month. This will happen automatically. Other options are explained further ahead.

#### Rollover ("Add an amount every period")

Rollover budget amounts can be used to "save up" money in a budget. Firefly III will take the budget left from the previous period and add the configured amount to the budget.

If you set it to "monthly" (€ 25) Firefly III will behave like so:

* January, the budget will be set to € 25.
* February, the budget will be set to € 50.
* March, € 75 etc.

If you spend money in your budget, this will be reflected in the budget. For example, with the example budget now at € 75, this is what happens when you spend € 19,95:

* April, the budget will be set to € 80,05: 75 + 25 - 19,95.
* May, € 105,05. Same logic.

If at any point you spend more than the amount in the budget, the routine will start over. So if you spend 199,95 (which is more than 105,05):

* June, the budget will be set to € 25 again.

#### Adjusted ("... and correct for overspending")

If you set an adjusted budget amount, the budget amount will be set every period to the amount you specify. If you have overspent this amount in the previous period, this will be corrected in the current period.

Example: you have a monthly budget of 50 for clothes.

* January, the budget amount will be set to 50
* February, the budget amount will be set to 100

You spend 125 in February.

* March, the budget amount will be set to 25 (150 - 125)

Just like the "fixed amount" auto-budget settings, these changes will happen on specific moments. This depends on the budget settings. If you spent way too much, twice the period's amount, the new period will be set to 1 (one).

#### Trigger dates

* Daily: Firefly III will create a budget amount of one day, every day.
* Weekly: Firefly III will create a weekly budget amount every week, every Monday.
* Monthly: Firefly III will create a monthly budget amount every month, on the first of every month.
* Quarterly: Firefly III will create a quarterly budget amount every three months, on the first of every quarter (1st of January, 1st of April, 1st of July, 1st of October).
* Half-yearly: Firefly III will create a half year long budget amount every six months, twice a year (1st of January, 1st of July).
* Yearly: Firefly III will create a year long budget amount every twelve months, once a year (1st of January).

#### Special attention

You can't change the trigger dates (like every Tuesday or the 5th of the month). After the amount has been created (on the first of each period or daily) you can freely edit or remove the limit. Firefly III won't stop you.

This feature will only work when you configure the [cron job](../advanced-installation/cron.md) correctly.

If you set the budget to "monthly", the budget limit created will also be "monthly". You can't do a daily increase on a monthly budget limit for example.

This routine is multi-currency aware, so it will also work for USD or CAD or whatever exotic currency you have configured. However, due to UI constraints, you only set one auto-budget per currency. You can't set two routines, one for USD and one for EUR.

## Categories

Categories are a bit like budgets. You might start to notice how some things don't need a budget, but do need some kind of meta-thing. A category might work. "Furniture", "interest", "shoes" and "lunch" are perfect categories.

* Daily groceries
* Money management
* Lunch
* Car
* Public transport
* House

But there is also income (deposits) that you might want to give a category:

* Taxes
* Salary

Each transaction can be given a category. This will show you what you spent your money on, or where it is coming from. Firefly III lets you dynamically create and manage categories. Fancy charts will show you how your money is divided over categories. There is a category report that can show you exactly what is happening within a category.

When you delete a category, any transactions in the category will be cleared of the category, and instead will get listed under "Transactions without a category".

## Budgets and categories

If you try to save money every month on a certain subject, it's a budget. Groceries are budget. Bills are a budget. If you travel by train occasionally, it's not a budget.

A category is "incidental". You don't buy new furniture every month, but you might want to keep track of such expenses. Or you don't care about costs for public traffic (budget-wise) but a category would be nice.

The rule of thumb is: would you make a real life envelope for it? If yes: budget. If no: category.

Categories can be used in deposits (earning money). Budgets cannot.

## Tags

Tags are an extension of categories and meant to expand on the meta-data included in a transaction. You can add multiple tags to a transaction.

Tags can be useful to group expenses together, possibly in another context than your categories. For examples, tags might include:

* `too-expensive`
* `work-expense`

Or maybe something else entirely. This is up to you.

### Special tags

When you import data into Firefly III, a special tag will be created for each transaction. It is called `Import on date X` where the date and time of the import are set.

## Groups

Some things in Firefly III can be divided into groups. At the moment this applies only to piggy banks and bills, but the list is slowly growing.

### Features

Groups are a very basic visual divider of objects. For piggy banks, you could divide them up into two groups: "large savings" and "small things".

### Managing groups

There are dedicated pages (listed under `/groups/index`) to edit and delete groups. You cannot create groups on this page; groups are created whenever you edit an object and set a group.

### Deleting groups

Groups are _automatically_ deleted when no objects exist in the group. If you remove the final object from a group (for example, a single piggy bank) the group is gone.

### Managing objects in groups

This feature is pretty new and for the time being, you can't do much with them. If you have good ideas just [let me know on GitHub](https://github.com/firefly-iii/firefly-iii/issues)!


