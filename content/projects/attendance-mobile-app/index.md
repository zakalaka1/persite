
+++
title = "Attendance mobile app"
description = "Mobile app to track attendance of classes by signed-up students."
date = 2025-12-21

[taxonomies]
tags = ["kotlin", "attendance app"]

# Optional: rendered as a "Languages:" row under the date. Omit for no row.
[extra]
languages = ["Kotlin", "Jetpack Compose"]

# Optional: rendered as a "Links:" row under the languages. Add or remove
# entries freely (repository, app stores, project site); order is display order.
[[extra.links]]
name = "GitHub"
url = "https://github.com/zakalaka1/attendance.git"

[[extra.links]]
name = "Google Play"
url = "https://play.google.com/store/apps/details?id=com.example.sample"

#[[extra.links]]
#name = "App Store"
#url = "https://apps.apple.com/#app/id000000000"

# Optional: rendered as the horizontal screenshots carousel under the Links row,
# one block per image, in the order written here. Delete every block for no
# carousel. `src` is required; `alt` is what a screen reader announces and
# doubles as the caption when `caption` is omitted; `caption` is the label
# printed under the image.
[[extra.screenshots]]
src = "pj_attnd_motion.gif"
alt = "Workflow in the app"
caption = "Animated workflow"

[[extra.screenshots]]
src = "pj_attnd_1.jpg"
alt = "Landing screen"
caption = "Landing (classes) screen"

[[extra.screenshots]]
src = "pj_attnd_2.jpg"
alt = "Students screen"
caption = "Students screen"

[[extra.screenshots]]
src = "pj_attnd_3.jpg"
alt = "Take attendance screen"
caption = "Take attendance screen"

[[extra.screenshots]]
src = "pj_attnd_4.jpg"
alt = "Classes screen"
caption = "Classes screen, exporting attendance report"

[[extra.screenshots]]
src = "pj_attnd_5.jpg"
alt = "CSV export file view"
caption = "CSV export file view"
+++

## Need

Taking student attendance with pen and paper—as my spouse had been doing—and then poring over multiple sheets to create a monthly report for attendance analysis and billing purposes seemed quite laborious and outdated after a couple of months of watching her do it.

## Check of what's available

CI checked what was available in app stores, but the options did not fit the simple requirements of just taking attendance and producing an on-demand CSV monthly attendance matrix.

## Distilled requirements

- An app that can be used to quickly take attendance at any time

- An app flexible enough to add/edit/remove classes or students at any time

- An app that stores all data locally, not requiring login or network access

- An app with built-in i18n

- An app with accurate attendance tracking: daily and within a given month

- A straightforward UI, not aiming to impress, but rather to be usable and uncluttered

## Highights of design decisions

- The landing page is the 'Classes' page

- Edits and deletes are in-line

- Each student in each class is unique — this avoids complex tracking of students attending multiple classes, students with the same name, exposing and reusing unique student IDs, etc.

- The data model behind the app is 'open' and flexible — there is some redundancy, as storage is vast and cheap. This allows straightforward and fast maintainability without complexity

## The Result

A fast app living completely on your mobile device, not asking for any permissions to your data. Yes, the app data can be lost when the app is uninstalled or the device is lost, but this risk is assessed as tolerable.

Monthly attendance CSV export files can, of course, be sent and used in spreadsheet software to further shape the data to one's specific reporting needs.