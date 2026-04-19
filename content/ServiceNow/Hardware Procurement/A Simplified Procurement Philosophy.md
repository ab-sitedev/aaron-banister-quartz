---
publish: true
created: 2026-04-18T22:52:32.204-05:00
modified: 2026-04-19T15:53:28.292-05:00
published: 2026-04-19T15:53:28.292-05:00
---

> [!Attention] A Grain of Salt
> Every company uses ServiceNow differently.
> Because of that, you might disagree with the below assessment and therefore also the solution.
>
> The described solution resonated with the stakeholders in my business, which means it might resonate with yours too!
> Let me know what you think in the comments. ✌🏻

## The Out-of-Box Intention (The Problem)

ServiceNow's vision for employee-driven procurement is very _"Amazon-esque"_. Users search the catalog for the hardware they want, click into each item, and add to cart.

### Why That's Great

This setup gives users a ton of autonomy - And who doesn't love shopping on Amazon? It's a pretty familiar user experience and seeing it implemented in the Employee Center looks very nice.

### But Here's Where It Gets Clunky

- Each piece of hardware requires its own catalog item (Catalog starts to feel bloated)
- Each catalog item can look slightly different (Users want consistency)
- Order approvers might get multiple approval tasks for the same cart
- Each catalog item requires dev effort (Creation, security, approval flows, etc...)

Each of those problems can be addressed in different ways without any customization. But for my business, none of the out-of-box solutions perfectly satisfied our requirements.

---

## The Thinking Shift That Changed Procurement

So, what _were_ those requirements?

After toiling over less-than-sufficient OOB solutions, I began working with our stakeholders on a new approach to procurement: One that's unified under a singular intake interface.

**We settled on these tenets:**

1. **Don't make users "shop" a catalog for their hardware.**
   Give users a single catalog item that supports multiple hardware items.

2. **Empower procurement admins.**
   Let them manage hardware availability and metadata directly in production.
   ==\*(Eliminate dev effort)\*==

3. **Simplify approvals.**
   They can still be procedural, but have them apply to the whole request instead of each individual item.

4. **Integrate seamlessly...**
   ...with ServiceNow's Asset Management and Purchase Order modules.

**Next:** An overview of our procurement implementation's tech stack _(Coming soon...)_
