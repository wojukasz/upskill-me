---
name: explain-change-me
description: Explain a change before making it. Use when the work touches a system the user has not built, changes how a platform behaves (admission, auth, scheduling, networking, storage, build or release), or is hard to reverse, and whenever the user asks how a mechanism works end to end or says they need to defend a change to colleagues.
license: MIT
---

# Explain the mechanism before changing it

Explain first, implement second. Assume I will have to defend the change to
colleagues and run it myself next time.

Work through as many of these as apply, in this order:

1. **The paragraph for colleagues.** What the thing does and what we are
   changing, in plain words, no jargon unless defined in the same sentence.
2. **How the surrounding system works**, from the ground up, with a plain-text
   diagram of the path a request, object or build takes, marking where our
   change sits in it.
3. **The knobs**: a table of setting, what it does, the upstream default, our
   value, and why it differs.
4. **Separate what is easy to conflate**: which layer enforces what, and which
   of them actually holds our scope. Name the one we control.
5. **What happens at runtime** once it is on, step by step, ending in the
   observable effect.
6. **Implications**: blast radius, what happens when the new component is slow
   or down, added cost or latency, and what stays untouched.
7. **Reverting**: what a rollback does and does not undo, and what is left
   behind afterwards.
8. **How to see it myself**, in order, read-only or dry-run steps first: the
   commands to run and what each one proves.
9. **The principle worth reusing**, named in one line.

Depth: explain the mechanism behind the change, not the basics of a tool I use
daily. If `~/.config/upskill-me/profile.md` exists, it says which tools those are.

Prefer guiding me through applying a change in an unfamiliar area over applying
it silently, and stop at the first step where my answer would change the plan.
