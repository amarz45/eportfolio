---
title: "Termtile"
summary: "University timetable planner built around the constraints students actually plan around."
---

A university timetable planner built around the constraints students actually
plan their lives by: who's teaching a section, how early the week starts, and how
long each day runs. It surfaces the resulting schedules as a browsable weekly
calendar.

[Source on GitHub](https://github.com/amarz45/termtile)

I find the most stressful part of starting a new academic year to be selecting
courses and building a schedule. The schedule builders most universities use are
quite limited, only allowing simple things like adding courses and
including or excluding sections. Most don't let you include or exclude certain
professors for certain courses, set a limit on the number of courses per term,
set a maximum gap between classes, or apply the other constraints you'd
typically want in order to see a list of schedules you'd actually choose from.
That's the problem Termtile tries to solve.

Termtile is still a work in progress. So far I've written the parser (in Python)
and the constraint solver (in TypeScript). Below is a mockup:

![Termtile mockup](img/mockup.png)

## What I'd do differently

I wrote the solver in Python first, got it working, and then realised I wanted
the whole thing to run in the browser with no backend, which meant rewriting it
in TypeScript. The rewrite wasn't wasted exactly, since I understood the problem
better the second time, but it was avoidable. I had decided how the solver would
work before deciding how anyone would actually run it, and the deployment
constraint was the thing that should have driven the language choice from the
start. Now I try to settle where something has to run before I write it. The
interface is also still a mockup: the solver produces correct schedules, but
nobody except me can use it yet, which is the honest limit of the project as it
stands.
