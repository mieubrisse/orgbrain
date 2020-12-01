Fractal Outcomes
================

Uncertainty
-----------
* Human code works well when the path is already trodden
    * Put in X work, get Y output
* When doing something never done before, it's harder to use
    * Don't know what's going to happen - Black Swans could throw everything off
* Introduce notions of input/output uncertainty
    * Checklist is high input/output certainty
* What does low input/output certainty look like?
* Forest analogy:
    * Our top-level outcome is clear - get to the town on the other side of the forest
    * How we get there is not - we have several trail options in front of us
    * The very next step (what GTD calls the "Next Action") IS clear - it's to take a step
    * But in which direction do we go?
    * Form several hypotheses
    * Take your best guess given current knowledge, and take a step in that direction
    * If this way looks promising, keep going
    * If the way seems to take you away from the direction of the town, you backtrack and choose another hypothesis
* This is how humans naturally navigate!
* Contact with reality _will_ yield unexpected results - a way that's looked promising for the best 15 minutes could suddenly dead-end, meaning your top hypothesis is now your bottom hypothesis and you need to switch
    * These are Taleb's Black Swans

Past approaches at handling uncertainty
---------------------------------------
* Both Agile and GTD recognize the folly of rigidly defining the future
    * GTD has Next Actions, Agile works in short sprints
* Both Agile and GTD don't have a good way for handling the steps beyond the immediate
    * How do you plan for the steps beyond the immediate?
    * Both use the notion of "projects", and both suffer from the same flaws
        * What does a project for "Mom's birthday" mean? When is it done?
        * When is "Prod database upgrade" done?
* Common, bad e.g. as the result of a quarterly planning document:
```
### P1 - Prod Database Upgrade
* New servers
    * 12 x R420s
    * Maybe 6 x R620s??
    * Kevin
    * Galen
    * Need to get in touch with Marco
* Software
    * James
    * Alex
    * Get in touch with vendor
        * Ask for discount
            * $500 last year
            * $2000 next year
        * Blocked on budget increase approval

### P2 - Audit logging
* Steve
* Code changes
* Deploy
* QA
```
* Main problem: "project" becomes this broad, reified concept, exempt from the human code rules about specificity and actionability and supplemental information
* People do this because:
    1. They know uncertainty exist, so they make a broad bucket to attempt to handle changes
    2. They don't want to change the plan
    3. They think "projects" are separate from "tasks"

A better way
------------
* As we've seen, this isn't how humans actually navigate
    * Instead, you form hypotheses, test those hypotheses by exploring the highest-conviction one, and keep hitting unexpected events and backtracking and iterating until you eventually arrive at your destination
* All the points along the way - both one step in front of you, and ten steps, and ten miles - are just hypothesized outcomes reach serving a larger outcome
    * Each journey is just a bunch of smaller journeys
    * It's _fractal_
* We've used human code for reaching highly certain outcomes
* We can extend it for navigating highly UNCERTAIN situations with Fractal Outcomes

```
* [ ] Implement Prod database upgrade to vX.Y.Z
    1. [ ] Order new servers @Kevin @Galen
        * [ ] (H) Purchase 12 x 420s
        * [ ] (H) Purchase 6 x 620s
    1. [ ] Upgrade database software @James @Alex
        1. [ ] Secure budget increase approval
            1. [ ] Contact Emily from finance and verify that she's okay with us going over our budget from last year
            1. TODO
        1. [ ] Secure discounted rate of 1k (NOTE: we paid $500 last year, and it's going to bump up to $2000 this year)
            1. [ ] Get in touch with vendor to ask for a discount
            1. TODO
    1. [ ] 
* [ ] Implement audit-logging 

### P2 - Audit logging
* Steve
* Code changes
* Deploy
* QA
```

* Immediate benefits:
    * Everything has an owner
    * Clarified what "Prod Database Upgrade" actually means
        * It's to go up to vX.Y.Z, so we've completed our mission and can move on to other things if we get to X.Y.Z
    * Represented that we have two competing hypotheses for ordering servers
    * Clarified that there's no work to do on the vendor discussion until we get the approval from finance by ordering the events appropriately
    * Surfaced that the Next Action for the budget approval is talking to Emily
    * Explicitly called out that there will likely be work after talking to both Emily and the vendor
    * Clarified what exactly "audit logging" means
    * Any outcome and all its subtasks can be owned by a given person
* Principles:
    * Everything is an outcome, and is NOT exempt from the rules of human coding
        * No distinction between tasks and projects
    * Every outcome is a hypothesis, that may be changed as contact with reality hits
        * "Everybody has a plan until they get punched in the mouth"
    * Because every outcome is a hypothesis, the plan must always be fluid (just like human brains)
    * Just like in checklists, sub-outcomes answer "how"
* Federalized outcomes:
    * Preserves the federalized command structure that works so well in maneuever warfare - you can break off an outcome and say "you figure out how to do it"
    * Parent outcomes answer "why"
        * This allows for communicating the "commander's intent", and gives teams the latitude to renavigate as needed
* Contract:
    * The FO is a document that says, "with our given knowledge, this is what we're promising to get done"
    * Allows us to measure:
        * Our output: how much work is being completed?
        * Our scoping ability: how much did we book vs how much did we actually do?
* Renavigations:
    * But, reality hits and things MUST change
    * All contracts are forever open to renavigation BUT the renavigation has to be made explicit!
    * This happens both ways:
        * Manager asks for more stuff, and the engineer goes "this is what's on the plate - what gets dropped?"
        * When an engineering task explodes, the engineer has to renavigate to say "this is taking longer than expected" (can't wait until the deadline)
    * Totally fine to renavigate - that's how humans naturally navigate!
    * Sometimes the uncertainty is so high that you have a 'planning event horizon' where you can't see beyond it
        * E.g. "talk to vendor" could change everything
    * In this case, explicitly budget & schedule a renavigation: "I'll take the one step I definitely know, and then we'll plan the next steps"

Rules for writing Fractal Outcomes
----------------------------------
### All rules for writing checklists still apply, no exceptions
Writing checklists are actually a special, high-certainty sub-case of Fractal Outcomes - basically Fractal Outcomes for a path that's already been walked before.

### 
