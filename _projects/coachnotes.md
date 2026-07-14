---
layout: project
permalink: /projects/coachnotes/
image: /assets/images/coachnotes.png
title: CoachNotes
description: Self-built lesson-planning dashboard with AI-assisted prep, in active production use.
tech: [Google Apps Script, Claude API, Pike13 API]
type: personal
educational: true
featured: true
priority: 2
link: https://github.com/isaiahcat
date: 2026-05-01
date_range: "Apr 2026 - May 2026"
---
A lesson-planning dashboard built for coding coaches at theCoderSchool. CoachNotes centralized session prep, post-session notes, and parent-facing write-ups in one place — replacing a fragmented workflow of spreadsheets and manual copy-paste.

What I built:
- Full-stack web app on Google Apps Script with a Google Sheets backend, served as a container-bound web app with zero external dependencies
- Student roster with session history, scheduled day/time, and language tracking across 100+ cumulative sessions per student
- Lesson prep system with per-session "Option 1 / Option 2" cards (label, overview, concepts, sample notes, sample code) generated manually or via Claude AI integration
- AI-assisted prep workflow: one-click export of session history as a structured prompt → paste into Claude → import JSON response back as formatted prep options
- Pike13 integration: full session history import via copy-paste parsing, and a post-session note sync that matches note blocks to students by name and writes back language, project, concepts, and status
- Day view showing all sessions for a selected date, collapsible per-student cards, and bulk session management

What I learned:
Shipped a functional internal tool used in active coaching sessions. The project was ultimately not adopted beyond my own use — theCoderSchool franchises follow a centralized tooling recommendation (Notes+), and individual coaches don't have purchasing authority. That constraint surfaced a real product lesson: for B2B tools in franchise environments, the decision-maker and the end user are rarely the same person. The technical and UX work was validated; the go-to-market assumption wasn't.
