# easiware Backend Challenge

Looking for a job? Check out our [open positions](https://www.welcometothejungle.com/en/companies/easiware/jobs).

## Why?

We believe our tech team should have a strong culture and build common conventions and coding style. We should be able to work together as a team. Ideally it should be impossible to know (except when _git blaming_) who wrote a given piece of code; we call this **Shared ownership**.

This culture and shared coding practices are meant to be evolutive and represent the current team in place. They must be opinionated, yet shared and represent the industry coding standards and best practices. This:

- allows junior developers or newcomers to quickly onboard on the project
- improves overall code quality and decreases regressions
- eases performance tuning

> this exercice is a kind of [_kata_](http://codekata.com/), a simple problem that allows someone to explore deep engineering concepts; we'll hope you'll enjoy working on it and sharing it with us

## Guidelines

You are a new developer in the _easiware_ team, and your first job is to add a feature to an old existing piece of code.

Hi and welcome to the team. We are in the future, and easiware has extended its activities by opening a pharmacy. Your task is to add a new feature to our system so that we can begin distributing a new drug. First an introduction to our system:

- All drugs have an `expiresIn` value which denotes the number of days we have until the item expires.
- All drugs have a `benefit` value which denotes how powerful the drug is.
- At the end of each day our system lowers both values for every drug

But there is more:

- Once the expiration date has passed, Benefit degrades twice as fast.
- The Benefit of an item is never negative.
- "Herbal Tea" actually increases in Benefit the older it gets. Benefit increases twice as fast after the expiration date.
- The Benefit of an item is never more than 50.
- "Magic Pill" never expires nor decreases in Benefit.
- "Fervex", like Herbal Tea, increases in Benefit as its expiration date approaches. Benefit increases by 2 when there are 10 days or less and by 3 when there are 5 days or less but Benefit drops to 0 after the expiration date.

We have recently signed a supplier of "Dafalgan". This requires an update to our system:

- "Dafalgan" degrades in Benefit twice as fast as normal drugs.

**For each level, write code that creates a new `data/output.json` file from the data in `data/input.json`.
An `expected_output.json` file is available to give you a reference on what result is expected.**

## Instructions

- Clone this repository (or fork it as a **private** repository)
- Implement the required feature
- Invite us on the private repository

You are encouraged to refactor the existing code before adding your own, as you would do if this was a real task in real life. We strongly recommend that you write tests to help you during this process.
A good way to solve this is by adding new layers of abstraction when they become necessary. You can use OOP, functional programming, or whichever approach you find useful; you should be able to explain your choice, and don't forget the mindset is to write code that could be run in production.
Don't hesitate to write [shameless code](http://red-badger.com/blog/2014/08/20/i-spent-3-days-with-sandi-metz-heres-what-i-learned/) at first, and then refactor it

Feel free to make any changes to the `updateBenefitValue` method implementation and add any new code as long as everything still works correctly. However, do not break the public API of the `Drug` and `Pharmacy` classes, as those are used by other pieces of the software (you can add new methods though).

Please commit as frequently as possible to make the review easier.

## Test

To make sure that you will not break anything in the existing code, we added a log of the simulation in the _output.txt_ file. Make sure that your code is able to generate the same file. You can generate a new file by running the following commands:

```sh
yarn start
```
