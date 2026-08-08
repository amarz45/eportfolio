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
