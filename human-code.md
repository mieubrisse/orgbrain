Human Code
==========
What's human code?
------------------
Imagine you're an airline and you have a sequence of things that need to be done to make a plane ready before takeoff. Would you rely on the pilot to remember these things? Of course not - the human memory is prone to lapses and affected by even things as small as what you ate that day; missing even one thing could spell disaster in flight. Even if one pilot remembered the steps perfectly, the next pilot might not. No, your airline would make a checklist.

Any safety-critical organization from airlines to NASA to the military knows that humans are poor executors of routines. It takes a long time to encode the steps in muscle memory, and a long time to change that muscle memory when the steps need to be updated. By writing down checklists, we create a centralized source of information that can be referenced by anyone, doesn't rely on human memory, and can be updated with new learnings. In short, checklists are code functions executed on human processors.

And yet... we have all these amazing advancements for machine code - cloud storage and version control and powerful editors and CI/CD tools. Where are these tools for human code? Maneuver warfare and the Toyota Production System show that whoever can cycle and learn fastest wins. So why are organizations leaving their institutional lessons scattered in the heads of their employees where they can be forgotten or lost when an employee moves on?

Rules for writing human code
----------------------------
### Every item must be actionable (must start with a verb or conditional-verb)
Machine code is a sequence of unambiguous, actionable instructions to the machine. Make human code likewise by starting every item start with a verb (e.g. "Press the 'Upgrade' button in the bottom-right corner of the UI") or conditional followed by a verb (e.g. "If the return code is 12, press the 'Send logs to IT' button").

By this rule, any supplemental information must be in-line (e.g. "Restart the server (NOTE: be careful; the power button's logo has faded!)"). Do NOT put supplemental info as a subtask.

### Every item must be specific, with a clear "done" point
Much like [SMART goals](https://www.mindtools.com/pages/article/smart-goals.htm), each item should clearly be either "not done" or "done". "Order parts" has an unclear endpoint (which parts?); "Order 4 more 16GB RAM sticks". "Tell Jeff" is ambiguous; "Inform Jeff that the production system was just upgraded" is not. 

### Complex or broad items should be broken into sub-steps
Steps can always be decomposed into smaller steps, with sub-tasks answering "how?". Break down complex or broad tasks by using sub-tasks, e.g.:

```
* [ ] Stop Oracle
    * [ ] Run `ps aux | grep oracle` to find the Oracle PID
    * [ ] Run `kill $THE_ORACLE_PID` (NOTE: do NOT use `kill -9`!!!)
    * [ ] Rerun `ps aux | grep oracle` until the Oracle process disappears
```

When deciding whether to break a task down into subtasks, a good rule of thumb is, "Would a junior engineer be able to follow this?" Remember that humans always think they're communicating more clearly than the reader receives it.

### Use variables when necessary
Just like with machine code, variables are sometimes necessary. These can be declared at the top of the checklist for easier readability, e.g.:

```
NOTE: $ENVIRONMENT will indicate the deployment environment

* [ ] SSH into the jumphost (the-jump-host.our-domain.com)
* [ ] If $ENVIRONMENT is development, run `bash ~/setup-dev-environment.sh`
* [ ] If $ENVIRONMENT is production, run `bash ~/setup-prod-environment.sh`
```

If your checklist uses a lot of machine code, it might be worth having the user declare an actual machine code variable so you can make it easier to copy-paste instructions later:

```
* [ ] If $ENVIRONMENT is development, run `ENVIRONMENT=dev` in your terminal
* [ ] If $ENVIRONMENT is produdction, run `ENVIRONMENT=prod` in your terminal
* [ ] Run `if [ ${ENVIRONMENT} -eq "dev" ]; then do-dev-thing; else do-prod-thing; fi`
```

### Use TODOs to clearly indicate work-in-progress areas
As with machine code, it's okay to build human code iteratively. Don't fall into the trap of feeling like codifying a checklist means you have to write down every last detail in excruciating detail. If you know an area needs more work, log a TODO and check it into version control so future executors can get in touch with you in the future.

### Don't repeat yourself (single-source rule)
We have the maxim "Don't Repeat Yourself" (DRY) when writing machine code because code duplication leads to divergent logic and bugs. This holds true at many levels:

1. At the sub-task level: if my checklist and your checklist both require "Stop the Oracle database", we should write a "Stop the Oracle database" checklist and have both our checklists link to it in the right spot. We should NOT both inline our own separate sub-tasks for stopping it!
2. At the whole-checklist level: people would rather write a new checklist than update an existing one because it's easier. This must not be allowed, or learning will fragment again and the org will slow down.
3. At the supplementary information level: if I have multiple steps that reference the Oracle database hostname, I should create a new page called Oracle Database Hostnames and link to that. I should NOT inline the hostname in each step, where it can grow stale.

A good rule to remember: "if you find it, fix it" - if you find a problem with the human code, fix it there and then.

### Human code repositories must be version-controlled
Just like with machine code, history is important, rollbacks are sometimes necessary, and a branching model allows for contributors. Likewise, pull requests should be required before changes are made to the checklist. Git is perfect for this.

### Human code repositories must be easily accessible by everyone
If the human code repository isn't easily-accessed, teams won't go through the trouble of using or updating them and human code will revert to being stored in human brains. If the checklists aren't available to the entire team, learning will fragment again as each team writes their own checklist thinking it's the first of its kind. If permissioning is needed, allow users to see the checklist title but not the contents.

### The checklists in the human code repository should be templatest for future executions
To run a checklist, a human should be able to simply make a copy of the master from the human code repo. The master should contain all the empty boxes and such necessary for an executor to start storing their results in seconds.

### Be wary of the cost-benefit tradeoff for checklists
For human code that runs very frequently (approx daily or more), the work of consulting and filling a checklist tends to be seen as prohibitively expensive and humans tend to go by memory regardless of whether a checklist exists. If errors won't cause serious issues, it's probably easier to skip writing a checklist for these very frequent routines and transfer updates to the routine the old-fashioned way (by repeatedly reminding people until they remember it). You can increase the speed of this method of learning by tightening the loop between incorrect behaviour (e.g. executing an old version of the routine instead of a new version) and feedback (e.g. a reminder to use the new steps).

Rules for executing human code
------------------------------
### Don't check an item off until it's done
It's sometimes tempting to check an item off and then turn to do it. If you were to get pulled away by an emergency in that second and come back to the checklist later, you'd skip a step. Only check items off after you've completed them.

### Check items off as soon as they're done
Likewise, it's tempting to batch checklist actions - read a couple items, do them all at once, and then tick off several items. The same issue with emergencies applies: if you were interrupted by an emergency in the middle of your batch, some items would get done twice. Worse still, batching means relying once again on the failure-prone human memory. The easiest solution to this is to keep the checklist open side-by-side with your workspace and check items off as you go.
