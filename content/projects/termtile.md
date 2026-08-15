---
title: "Termtile"
summary: "University timetable planner built around the constraints students actually plan around."
competencies: ["Design", "Problem Analysis", "Use of Engineering Tools"]
---

A university timetable planner built around the constraints students actually
plan their lives by: who's teaching a section, how early the week starts, and how
long each day runs. It surfaces the resulting schedules as a browsable weekly
calendar.

[Source on GitHub](https://github.com/amarz45/termtile)

I find the most stressful part of starting a new academic year in university to be selecting courses and building a schedule. The schedule builders that most universities use are quite limited, only allowing you to do simple things like adding courses and including/excluding sections. Most of them do not allow you to do things like include/exclude certain professors for certain courses, set a limit for the number of courses per term, set a maximum gap between classes, and other constraints you would typically want to set to see a list of valid schedules you would actually want to choose from. This is the problem that Termtile tries to solve.

Termtile is still a work in progress. I have only written the parser (written in Python) and the constraint solver (written in TypeScript). Below is a mockup:

![Mockup](/eportfolio/img/mockup.png)

## What building it has taught me so far

The interesting problem turned out not to be generating valid timetables, which
is a solved problem, but deciding what counts as a constraint worth modelling.
Every constraint I care about – a professor I want to avoid, a day I don't want
to start at 8:30 – is one that no registration system exposes as data. So most
of the work has been in representing preferences the source data doesn't contain,
and in deciding which ones are worth the interface complexity they cost.

## What I'd do differently

I wrote the solver in Python first, got it working, and then realised I wanted
the whole thing to run in the browser with no backend – which meant rewriting it
in TypeScript. The rewrite wasn't wasted exactly, since I understood the problem
better the second time, but it was avoidable. I had decided how the solver would
work before deciding how anyone would actually run it, and the deployment
constraint was the thing that should have driven the language choice from the
start. Now I try to settle where something has to run before I write it. The
interface is also still a mockup: the solver produces correct schedules, but
nobody except me can use it yet, which is the honest limit of the project as it
stands.

## Competencies demonstrated

**Problem Analysis** — the project began by identifying that existing schedule
builders solve the wrong problem, not that they solve it badly. **Design** —
turning vague preferences into a constraint model that a solver can actually
evaluate. **Use of Engineering Tools** — a Python parser feeding a TypeScript
constraint solver.
