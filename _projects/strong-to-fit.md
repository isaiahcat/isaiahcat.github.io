---
layout: project
permalink: /projects/strong-to-fit/
image: /assets/images/strong-to-fit.png
title: Strong → Strava Workout Converter
description: Browser tool converting Strong app workouts into Garmin .fit files with full strength detail for Strava.
tech: [JavaScript, Python, FIT SDK]
type: personal
educational: false
featured: false
priority: 9
link: /assets/tools/strong-to-fit.html
date: 2026-07-01
date_range: "Jul 2026"
---
Built a self-contained browser tool that converts Strong app workout exports into Garmin .fit files, preserving full strength training detail — exercises, sets, reps, and weights — for accurate Strava uploads. Solved import bugs around UTC timestamp anchoring, exercise grouping by category/subtype pairing, and FIT's 1/16-kg weight resolution to avoid undercounted lifts. Also includes a Python-based bulk converter for full CSV exports.

<div style="margin: 2rem 0; border-radius: 12px; overflow: hidden; border: 0.5px solid #e8e5df;">
  <iframe
    src="{{ '/assets/tools/strong-to-fit.html' | relative_url }}"
    style="width: 100%; height: 900px; border: none; display: block;"
    loading="lazy"
    title="Strong to Strava Converter Tool">
  </iframe>
</div>