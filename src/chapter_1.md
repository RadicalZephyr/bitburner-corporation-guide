# Manual Corporation Walkthrough

To get a feel for how your Corporation works it can be helpful to
interact with it through the game's user interface first. There are
tons of informative tool-tips on different UI elements explaining how
everything works.

## Creating your (First) Corporation

Head to the City Hall in Sector-12 to create your first corporation.
Since it's your first corporation you are most likely in Bitnode 3. If
you are you should choose to start with seed money from the
government.  Earning the seed money to self-fund your corporation
under the harsh restrictions of Bitnode 3 takes an excessively long
time.

Let's start by taking a look at the UI and what's available after we
create the corporation.

The initial Corporation screen gives you an overview of the status of
your corporation. Unlike most other mechanics in Bitburner, you can't
spend your personal money on Corporation unlocks or upgrades. Instead
you can only spend your corporation funds on these things. You always
start a corporation with $150 billion.

Right now our Corporation doesn't have any way to make money and it's
going to take a lot of investment to start making money. We're
probably going to need to get several rounds of investors to raise the
money to make our corporation truly profitable. In order to get as
much money as possible in each investment round we want to generate as
much profit as we possibly can with the funds we get in each
round.

```admonish note
#### How to make Money

But how do we actually make money with a corporation? The basic answer
is that you will hire employees, assign them to work in positions. You
will set up standing orders to buy the input materials your industry
needs and your employees productivity will turn those input materials
into output materials. You will then sell those output materials for a
profit.
```

In order to maximize our profit we need to produce as many output
materials as possible and we need to maximize the quality of our
inputs. But that's getting ahead of ourselves. For now, the first step
is to create...

## Your First Division

In order to start making money we need to expand into an industry to
create our first division. Our initial budget of $150 billion might
seem like a lot, but it's actually a fairly small budget for how much
most things cost in corporations. Because of this we should only
expand into one division initially and focus on upgrading it to
maximize the quantity and quality of the materials we produce with it.

It is _highly_ recommended that if you are new to the Corporation
mechanic you start by creating an Agriculture division first.

```admonish question
####  Why Should You Start with Agriculture?

Our ultimate goal is to create high quality products to sell for lots
of money, so we need to learn a little bit about how product quality
is determined. We'll get into this in more depth later but for now the
most important thing to know is that higher quality inputs produce
higher quality outputs. When we buy materials from the market they
always have the base level quality of 1. In order to get higher
quality materials we need to produce them ourselves using research
points, engineers and researchers (employees assigned to Research &
Development) to raise the quality of our output products.

Eventually, we want to create a circular supply chain where we
feedback high-quality materials into the beginning of our supply chain
to create even higher-quality products. If you spend some time in the
Industry expand screen you can see what materials each industry
produces and consumes. To create the optimal circular supply chain we
need to have an industry producing at least one input material for
each of our industries. We recommend Agriculture because it is part of
the smallest self-sufficient supply chain (Agriculture <-> Chemical)
and Agriculture is cheaper than Chemical to start and has better
scaling in some mechanics we haven't talked about yet.

Because of our low budget in the first round we can only create one
industry and we won't be able to unlock the "Export" mechanic which is
key to creating complex supply chains, but starting with Agriculture
sets us up to expand into Chemical and complete our supply chain loop.
```

To create our Agriculture division click the "Expand" button at the
top of the Corporation screen next to the name of your
corporation. Choose Agriculture and a name for your new division.

This will create a new agriculture division with one office in
Sector-12 and a starting warehouse.

There's a lot of information to take in here but let's start by
looking at the Division information in the top left corner. In
particular you can see your total "Corp Funds" (which is a pool shared
by all your divisions), the Awareness and Popularity which are
important stats relevant to how much material or product you can sell,
your production multiplier and your research points.

If we mouse over the Production Multiplier we get a helpful tool-tip
briefly describing what this important quantity is, and if you click
on the question mark icon you can get a more in-depth explanation. The
executive summary is that the Production Multiplier directly affects
how many materials or products we can produce per cycle.

The most important thing to note is that this Production Multiplier is
the sum of the Production Multiplier from each office, but it is a
per-division value and it is applied to _all_ offices in your
division. The base production multiplier for each office that has a
warehouse is 1, so when you have 1 office and it's associated
warehouse, your division Production Multiplier is 1. But since the
division Production Multiplier is the _sum_ of all office Production
Multipliers if we expand to a new city and purchase a warehouse there,
our division multiplier will jump to 2 during the next [Start] phase.

[Start]: ./glossary.md#start

This means the quickest way to increase our division Production
Multiplier when starting a new division is to expand to all six cities
and purchase a warehouse in each one. Let' do that now.

## Putting Everyone to Work

The next thing we want to do is hire some employees. Currently we have
space for 3 employees in each office so go ahead and hire 3 employees
at every office. Let's also put them to work in "Research &
Development" for now to build up some Research Points.

Each industry has their own stock of Research Points. We want to
always have a stock of Research Points because having them will
increase the quality of the materials/products we create. Eventually,
once we've built up enough Research Points we can start to purchase
some Research upgrades.

Let's also take a closer look at some of the other numbers in the
office section. You'll notice that there are three average employee
stats listed.

- Average Employee Morale (Max 100)
- Average Employee Energy (Max 100)
- Average Employee Experience (No Max)

If your employees Morale and Energy are below the maximum value of 100
there's a compounding penalty applied to the base production for that
office so it's important to keep those numbers as close to maximum as
possible. If both morale and energy are at 90, then there's about a
20% penalty, but if both morale and energy are at 50 then there's a
75% decrease in production.

There are two ways to keep our employees morale and energy at
maximum. We can buy tea to increase Energy and we can throw our
employees parties to increase their Morale. We can purchase these once
each full cycle, so every 10 seconds. Purchasing tea is a flat fee and
it increases energy by +2. When throwing a party you can choose how
much money to spend per-employee on the party. Spending $10 million
per employee will double the current morale, $1 million will increase
it by about 10%, $100k will increase it by about 1%.

The other way we can make our employees happy and motivated is by
assigning some of them to be interns to boss around. Intern employees
also earn experience at 10 times the rate of other employees! Interns
are important and they become even more useful when you have more than
nine employees and your employees morale and energy starts to decrease
every cycle. To counteract this you typically want 1 out of every 9
employees be assigned as interns.

This section is based on [this code][employee-stats].

[employee-stats]: https://github.com/bitburner-official/bitburner-src/tree/v2.8.1/src/Corporation/OfficeSpace.ts

Notice that as you assigned employees to R&D, the display changes from
a zero to `0 -> 1`. Once the next `Start` phase comes around in the
cycle, this changes to a `1` so we can't instantly change employees
from one job to the other, they only switch at the beginning of a
cycle.
