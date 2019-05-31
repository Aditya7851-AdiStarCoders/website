---
title: Coding Bets
description: How Coding, Investing and Gambling are similar undertakings.
url: https://riskfirst.org/Coding-Bets
image: /images/generated/titles/Coding-Bets.png
---

# Coding Bets

The argument here is that any time you start coding a new feature, accept a new task, or go hunting for a bug on a software project, you're actually making a bet.  

Let's look at some examples...

## Refactoring: The Technical Debt Bet

##### "Making our codebase easier to reason about is worth the outlay of time."

[Complexity Risk](Complexity-Risk.md) is risk due to the weight of complexity in the codebase, and its resistance to change and comprehension.  Fred Brooks' calls this mode of failure _the tar pit_:

> " Large and small, massive or wiry, team after team has become entangled in the tar. No one thing seems to cause the difficulty - any particular paw can be pulled away. But the accumulation of simultaneous and interacting factors brings slower and slower motion. " - [Frederick P. Brooks, _The Mythical Man-Month_](https://www.amazon.com/Mythical-Man-Month-Software-Engineering-Anniversary/dp/0201835959)

Refactoring is the notion that we can escape the tar pit by making our codebase simpler: If _project agility_ is some function of [Complexity Risk](Complexity-Risk.md) and your team's talent, the bet here is that you can trade some time _now_ on to move to a place of lower [Complexity Risk](Complexity-Risk.md), making it easier for the developers to _get stuff done_ in the future.

Refactoring requires that you have some _simplifying realisation_:

> "We don't need this extra parameter to this function"

> "Class A and Class B are actually different implementations of the same functionality"

> "We can encapsulate more behaviour by introducing the command pattern".

It looks like this:

![Stake and Reward for Fixing Technical Debt](images/generated/practices/coding/refactoring.png)

**When you win:**
 - The codebase is easier to think about.  
 
**When you lose:** 
- The [Complexity Risk](Complexity-Risk.md) improvement is less than you hoped,
- Or, it takes longer than expected, 
- Or the _simplifying realisation_ doesn't pan out and you've lost a week.

## Spike Solutions: A New Technology Bet

##### "This new technology is a better fit for our problem than the one we're currently using."

> "Sometimes a user story is generated that cannot be well estimated until the development team does some actual work to resolve a technical question or a design problem. The solution is to create a “spike,” which is some work whose purpose is to provide the answer or solution. " - [Spike Solution, _Agile Dictionary_](http://agiledictionary.com/209/spike/) 

You might want to use a Spike Solution to test out a badly-fitting technology for a more appropriate one.  That is, trying to solve a [Software Dependency Risk](Software-Dependency-Risk.md) issue.  For example:

> "Let's try replacing all this configuration with some [YAML](https://en.wikipedia.org/wiki/YAML) files."

> "Let's explore using [ElasticSearch](https://en.wikipedia.org/wiki/Elasticsearch) for searching instead of SQL Statements."

Alternatively, someone will suggest using an existing technology to eradicate lots of home-grown code.  Devoting parts of your code-base to solving problems that are already solved elsewhere is a source of [Complexity Risk](Complexity-Risk.md), because that code needs maintaining.

> "Let's throw away all these scripts and start using [Kubernetes](https://en.wikipedia.org/wiki/Kubernetes) to deploy our components."

> "Let's re-write these modules using [Clojure](https://en.wikipedia.org/wiki/Clojure)."

But will the new technology fit?  The answer is to try to "prove" the bet as quickly as possible using a time-boxed "Spike Solution".

![Stake and Reward for A Spike Solution](images/generated/practices/coding/spike.png)

**When you win:**
 - The spike solution demonstrates that the technology will fit for all of the use cases needed.
 - The spike solution demonstrates that the technology is definitely not a good fit, for clear reasons that weren't apparent before starting. 
 
**When you lose:** 
 - The developer can't get the spike solution working in the given time.  Does this prove that the technology is no good, or too complex, or that the developer needed more time, or that they're not skilled enough?
 - The developer gets the spike solution working for a specific use case, which is taken as success.  Later, though, other down-sides appear, and it's apparent that the solution is more trouble than it's worth.
 
**Reduce the stakes by:**
 - Searching the Internet for stories of teams who've made the same bet.
 - Tackling the hardest use-case first.
 - Skipping writing tests: if it doesn't work out, they're waste.
 - Ruthlessly rejecting any work that isn't adding to the proof.

## New Feature Bets

##### "This new feature may be exactly what our users are looking for."

Often you get user-stories like these:

> "We need to provide an export-to-Excel function, as our competitors have one."

> "Users need to be able to customize the workflow, otherwise they'll go elsewhere."

> "We need a global search because people spend too much time menu-diving."

New features might help sell your software to new markets and please existing power users.  But too many features confuse users, obscuring the essential purpose of the software.  This is [Conceptual Integrity Risk](Feature-Risk#conceptual-integrity-risk) - trying to please everyone means you please no-one.  

![Stake and Reward for Adding New Features](images/generated/practices/coding/new-feature.png)

**When you win:**
 - Existing users welcome the change with open arms.  
 - New markets open up.
 
**When you lose:**  
 - The feature is a diversion from the main purpose of the project, and a waste of time.  
 - The feature doesn't make much impact, is used often enough to not be removed, but adds [Complexity Risk](Complexity-Risk.md) to the codebase.
 - The feature confuses the user-base, and leads to increased support costs and dissatisfaction.

**Reduce the stakes by:** 
 - Thoroughly triaging new features.
 - Building mock-ups.
 - Opening up channels of feedback.
 - Testing with trial populations.

## MVP: The New Market Bet

##### "Building a Minimum Viable Product is a bet on the market"

A product may not necessarily be a set of individual features that can be delivered one-at-a-time.   Sometimes there are multiple parts that only make sense as a whole.  You can't prove the parts individually, but you can prove a _minimal set of them_.  

> "A minimum viable product (MVP) is a product with just enough features to satisfy early customers, and to provide feedback for future product development." - [Minimum Viable Product, _Wikipedia_](https://en.wikipedia.org/wiki/Minimum_viable_product)

The idea here is to make a bet that a market exists for a certain product, _and that there's money to be made from it_. 

![New Market Bet](images/generated/practices/coding/new-market.png)

> "People will use the search engine and we can monetize it with advertising".

> "People will buy pet food online"

> "Bots are the future: let's write one for the insurance business"

**When you win:**
 - You start a new business
 
**When you lose:**  
 - Loss of credibility.
 - Funding dries up.
 

**Reduce the stakes by:** 
- Failing fast.  Implement the riskiest functionality first.
- Doing things that don't scale.  You can prove the market by doing a lot of processes manually.
- Relying on Dependencies:  for everything that isn't completely unique.

## Conclusion

We're used to the idea of entrepreneurs taking risks on new business ideas.   B

This was just a few examples, but this idea is _generally_ applicable.  Look at the next piece of code you're about to write:

 - What are the likely stakes?
 - What is the [Payoff](Glossary.md#payoff)?
 - Is the bet worth it?  Sometimes, the stakes and the payoff are _a given_, but the bet still isn't worth the time.
 
How can you maximize the stakes while minimizing pay-off?  How long will it take for the pay-off to be worthwhile?

Are you making a long bet, or lots of small short bets?  (Split work up, then do the riskiest part first)
 De-Risking
