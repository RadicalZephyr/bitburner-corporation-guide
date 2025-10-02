# Chapter 2 - Getting Started Automating

Now that you've gotten some familiarity with the basic structure and
mechanics of your corporation you may have noticed that parts of it
can be fairly click-intensive to manage by hand.

The solution to this is to start creating scripts to automate the most
tedious parts. This immediately presents an issue however, because the
Corporation interface functions cost a _lot_ of RAM to use. If you're
just starting in Bitnode 3, you can only run one or two corporation
functions in a script before your script can't be run on your home
computer without upgrading!

Because of this it is helpful to focus our scripts to use as few
Corporation APIs as possible.

### Ideas for Incremental Automation Scripts

- Employee Morale and Energy Maintainer Script
- Manual Production and Sales Optimizer

#### Employee Morale and Energy Maintainer Script

Simple script to purchase Tea and throw parties every cycle if the
morale and energy are significantly below 100%.

#### Manual Production and Sales Optimizer

Create a small React UI with sliders to control the quantity of
materials purchased and the rate above market price to sell them at.

##### Progressive Enhancements

- Record the amount sold per-cycle and adjust to automatically produce
  that amount.
- Predict the amount of outputs we will produce
