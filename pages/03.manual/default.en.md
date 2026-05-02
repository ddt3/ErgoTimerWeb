---
title: Manual
---

## ErgoTimer — Manual

## Table of Contents

1. [Overview](#1-overview)
2. [Main Screen](#2-main-screen)
3. [Settings](#3-settings)
   - 3.0 [My Day](#30-my-day)
   - 3.1 [Core Schedule](#31-core-schedule)
   - 3.2 [Breaks & Recovery](#32-breaks--recovery)
   - 3.3 [Interface](#33-interface)
4. [Schedule View](#4-schedule-view)
5. [Active Task Controls](#5-active-task-controls)
6. [Adjusting the Schedule](#6-adjusting-the-schedule)
7. [Mental Battery](#7-mental-battery)
8. [Notifications](#8-notifications)
9. [Scheduling Logic](#9-scheduling-logic)
10. [Task Types](#10-task-types)
11. [Languages](#11-languages)

---

## 1. Overview

ErgoTimer is a daily schedule manager designed for people with Acquired Brain Injury (ABI) and anyone who needs to carefully balance mental work, physical activity, and rest. The app generates a personalised daily schedule and guides you through each task with timers, alarms, and notifications.

All data is stored locally on your device. ErgoTimer does not use the internet, cloud services, or any external connections.

---

## 2. Main Screen

When you open ErgoTimer, the main screen shows:

- **Top area** — the currently active task (shown only when the day has started)
- **Schedule list** — all tasks for the day in chronological order
- **Toolbar** — settings icon (⚙️) in the top right corner

### Before starting

When no schedule has been generated yet, the screen shows:
- A prompt to configure and generate a schedule
- A **Configure & Generate Schedule** button that opens the settings

### After generating a schedule

Once a schedule is generated, the screen shows the full day as a scrollable calendar timeline. Action buttons appear at the bottom:
- **Add Task** — opens the same anchor dialog used in settings, so you add a fixed anchor directly from the schedule
- **Catch Up** — jumps into the current point in the existing schedule based on the current time
- **Start Now** — regenerates the full schedule using the current time as the work window start, then immediately starts the first task. Only available within 60 minutes of the configured work window start time.

---

## 3. Settings

Open settings by tapping the **⚙️** icon in the top-right corner of the main screen. Settings are organised into collapsible sections. Tap a section header to expand or collapse it. Tap **Generate Schedule** at the bottom to apply your settings and create a new schedule.

### 3.0 My Day

This section defines the boundaries of your full day. The scheduler uses these times to decide where it may place generated tasks.

#### Wake-up Time
The time you wake up. Tasks will never be placed before this time.

#### Bedtime
The time your day ends. Tasks will never extend beyond this time.

#### Work Window Start
The earliest time the scheduler may place mental work. This is the start of your active working period.

#### Work Window End
The latest time at which work may end. No generated mental task will extend beyond this boundary.

---

### 3.1 Core Schedule

#### Total Work Hours
**Range:** 1 hour to 9 hours, in 0.5-hour increments  
**Default:** 4 hours

The total number of hours of mental work to schedule in the day. Physical breaks and rest periods are never included. Fixed anchors only count when their **Counts toward work target** switch is enabled for that anchor.

#### Max Mental Task Duration
**Range:** 30 minutes to 180 minutes (3 hours), in 30-minute increments  
**Default:** 120 minutes (2 hours)

The maximum continuous duration of a single mental task. When a mental task reaches this limit, the scheduler will always insert a break before allowing further mental work. This setting is a hard limit — no mental task in the generated schedule will exceed this value.

For draining fixed anchors inside the work window, this same limit also applies. If a draining anchor is longer than your configured maximum mental task duration, schedule generation is blocked with an actionable validation message so you can shorten that anchor or increase the max mental setting.

#### Min Physical Task Duration
**Range:** 5 minutes to 60 minutes, in 5-minute increments  
**Default:** 15 minutes

The minimum length of a physical or rest break inserted between mental tasks. This is used as a baseline — actual break lengths are calculated using the ratio described in [Section 9](#9-scheduling-logic).

#### Start Time
The time your working day begins. Set the hour and minute using the time picker. The scheduler uses this as the start of the first gap it can fill with generated work.

---

### 3.2 Breaks & Recovery

Between automatically generated items, ErgoTimer keeps transition space on both sides of a generated break. In practice, the pattern is: generated mental task, breathing space, generated break, breathing space, next generated mental task.

#### Breathing Space
Breathing space is the transition gap ErgoTimer keeps between generated tasks. If the day is tight, ErgoTimer may shorten this gap in specific spots to keep fixed anchors and required work feasible, while still preserving your configured schedule constraints.

#### Fixed Anchors

Fixed anchors are non-movable schedule blocks that reserve time for lunch, meetings, appointments, therapy, travel, or planned recovery. Each anchor has:

- **Name** — shown directly in the schedule
- **Anchor type** — determines when the anchor is placed in the schedule
- **Energy effect** — how the anchor affects the mental battery
- **Counts toward work target** — determines whether the anchor duration reduces the remaining generated work

Anchor types:

- **Fixed time** — placed at a specific start and end time. The start and end times are configured directly. In the anchor list, these show their start and end time.
- **Before work** — placed immediately before the work window starts, with a configurable duration. In the anchor list, these show their type label and duration instead of a time range.
- **After work** — placed immediately after the last generated work block ends, with a configurable duration. Fixed-time anchors scheduled later in the day are not affected. In the anchor list, these show their type label and duration instead of a time range.

Energy effects:

- **Draining** — behaves like mental work for battery purposes
- **Neutral** — reserves time without changing the battery
- **Restoring** — behaves like a restorative break for battery purposes

Work-accounting defaults:

- **Fixed time** anchors default to counting toward the work target
- **Before work** anchors default to not counting toward the work target
- **After work** anchors default to not counting toward the work target
- You can override this per anchor in the anchor dialog without changing its battery effect

The scheduler never places generated work inside a fixed anchor. Instead, it fills the gaps before, between, and after anchors.

In settings, each anchor card uses a compact two-row layout: the first row shows the anchor icon, name, and metadata; the second row contains the enable switch and edit/delete controls.

Overlap behavior for fixed-time anchors:

- You can save overlapping fixed-time anchors.
- If overlapping fixed-time anchors are both **enabled**, their cards are highlighted with a red border in settings.
- Schedule generation is blocked when enabled fixed-time anchors overlap. Disable one of the conflicting anchors and generate again.

---

### 3.3 Interface

#### Language
Choose between **English** and **Dutch**. The app will display all text in the selected language.

#### Interface Mode
**Default:** Calm

ErgoTimer offers three interface modes:
- **Standard** — task blocks show task name, duration, and per-task energy range (start % → end %). The active-task header shows the live battery percentage bar.
- **Calm** — task blocks show task name and duration with softer visual styling; per-task energy range is hidden in blocks. The active-task header still shows the live battery percentage bar.
- **Minimal** — task blocks are icon-only and the active-task header hides the battery percentage bar.

#### Alerts

##### Task Notification Sound
Select which sound plays when a task ends. Tap the selector to choose from the available options:
- **None** (silent — the task ends without an audible alarm)
- **System default** (uses your phone's default notification sound)
- A specific task-end sound

Use the play icon beside the selector to preview the current task sound (disabled when **None** is selected).

##### Micro-Pause Reminder Sound
Choose which sound plays for micro-pause reminders. You can select:
- **None** (silent reminder)
- **System default** (uses your phone's default notification sound)
- A specific micro-pause sound

Use the play icon beside the selector to preview the currently selected micro-pause sound (disabled when **None** is selected).

---

### 3.4 Advanced

#### Debug Mode (Fast Timers)
**Default:** Off

When enabled, time is accelerated: 1 hour is treated as 1 minute. This mode is intended for testing and development only. Do not use this mode during normal use.

---

## 4. Schedule View

The schedule is displayed as a scrollable vertical timeline (calendar view). A time axis on the left shows clock times; colour-coded task blocks are placed at their exact positions on the axis. A horizontal "now" line moves through the timeline as time passes, so you can always see where you are in your day at a glance.

If there is an empty gap between two scheduled tasks that is larger than the configured breathing space, ErgoTimer shows a subtle tappable gap row in that slot. Tapping the gap opens the same Add Anchor dialog used in settings, pre-filled with that gap's start and end time so you can create a fixed-time anchor in that free period. Gaps that are only as long as the breathing space remain visually quiet and do not show add-task text.

### Task Block Layout

Each block shows:
- **Colour** — indicates task type (see [Section 10](#10-task-types))
- **Task name** — e.g. "Mental Task", "Physical Break", or your fixed anchor name
- **Time range** — start time and end time
- **Duration** — shown in hours and/or minutes
- **Mental battery range** — the energy level at the start and end of the task

Task block colours still map to task type, but the block fill is softened for better readability and less visual intensity.

Tapping any task block, including the currently running task, opens the task detail sheet.

Short tasks (less than 20 minutes) use a compact single-line layout to prevent overflow.

### Task States

- **Upcoming** — normal appearance, full colour
- **Active (current task)** — pulses gently to draw attention; shown with countdown timer
- **Completed** — shown with reduced opacity

---

## 5. Active Task Controls

When a task is running, the current task panel appears at the top of the screen, showing:

- **Task name**
- **Start and end times**
- **Countdown timer** — displayed in MM:SS format in a large, colour-coded block
- **Mental battery indicator** — a progress bar showing your current energy level (see [Section 7](#7-mental-battery))
- **Control buttons** — Pause, Stop, and Next

### Pause / Resume
Tap **Pause** to pause the countdown timer. The task end time adjusts accordingly, and the foreground service is stopped. Tap **Resume** to continue the task, which restarts the foreground service and re-arms the completion alarm.

When the app is paused, the alarm is cancelled so it will not fire while the task is paused. When you resume, the alarm is rescheduled for the new end time.

**Note:** Pausing stops the ongoing countdown notification from appearing in the background. This is intentional — the task is not actively running while paused.

### Stop
Tap **Stop** to end the current task immediately without moving to the next one. The schedule remains as-is. Use this if you need to exit the current task flow without advancing.

### Next
Tap **Next** to end the current task early and move to the next task. The remaining time from the current task is rounded to the nearest 5 minutes and added as an additional mental task at the end of the schedule, so that your total work hours are still met.

---

## 6. Adjusting the Schedule

You can modify individual tasks in the schedule while the day is running (or before starting).

Tap any task block to open its detail sheet with the available actions.

### Adding a Task in an Empty Gap
If there is visible free time between two tasks that exceeds the configured breathing space, tap the gap row between them to open the Add Anchor dialog. The dialog is the same as in Settings and is pre-filled with that gap's start and end time. After saving, ErgoTimer regenerates the schedule using the updated anchor list and immediately applies Catch Up when the day is already running, so the current timeline stays aligned with now. If the new anchor creates an invalid setup, ErgoTimer shows a validation message and keeps the previous schedule. Breathing-space-sized gaps stay quiet in the UI so they are not presented as fillable work slots.

### Increasing Task Duration (+10 min)
Tap **+10 min** to add 10 minutes to a task. For mental tasks, the duration cannot exceed the configured maximum mental task time. For rest and physical breaks, the duration can be increased freely.

### Decreasing Task Duration (−10 min)
Tap **−10 min** to reduce a task by 10 minutes. The minimum duration for any task is 10 minutes. For rest and physical breaks, the minimum allowed duration is calculated based on the preceding mental task (see [Section 9](#9-scheduling-logic)).

### Toggling Break Type
For rest and physical breaks, a toggle button switches the task between **Rest** and **Physical** type. This does not affect the duration or position in the schedule.

### Schedule Recalculation
After any adjustment, the schedule automatically recalculates:
- **When you decrease a task**: if total work hours fall short, an extra mental task is added at the end to fill the gap
- **When you increase a task**: previously auto-generated filler tasks are shortened or removed if no longer needed

---

## 7. Mental Battery

The mental battery represents your cognitive energy level throughout the day. It is displayed as a percentage bar in the current task panel.

### How It Works

- **Drains** during mental tasks and draining fixed anchors
- **Charges** during physical breaks, rest breaks, and restoring fixed anchors
- **Stays level** during neutral fixed anchors
- **Range**: 0% (empty) to 100% (full)
- The battery starts at 100% at the beginning of the day

### Drain and Charge Rates

The battery drains and charges at rates derived from your settings:
- **Drain rate** is based on the Max Mental Task Duration setting: a full-length mental task drains the battery from the level at the start of that task to 0%
- **Charge rate** is based on the Min Physical Task Duration setting: a minimum-length break charges the battery to match the drain from the preceding task

### Battery Display

The energy range for each task (start % → end %) is shown in the schedule tile. The live current percentage is shown in the active task panel during a running task.

---

## 8. Notifications

ErgoTimer uses Android notifications and a background foreground service to ensure reliable task tracking even when the app is backgrounded or removed from recents.

### Current Task Notification (Persistent / Foreground)
When a task is active, a persistent notification is shown in the Android notification bar. It displays:
- The current task name
- A live countdown timer — implemented using Android's native chronometer, so the displayed time updates continuously and correctly even when the app is in the background, without requiring app interaction

This notification is backed by a **foreground service** that keeps the app's process alive while a task is running. This is essential for reliable:
- Schedule progression (advancing to the next task automatically)
- Alarm rescheduling (re-arming alarms after boundaries are crossed)
- Recovery after app backgrounding or process restart

**Note:** If an app is removed from Android's recent apps list while in the background, the system may kill the process. The foreground service, combined with persisted session state, allows ErgoTimer to recover and continue the schedule when the process restarts.

### Task Completion Notification
When a task's timer reaches zero:
- An alarm sound plays (if enabled)
- A notification is shown with the message "Task Complete!"
- A dialog appears in the app (if the app is in the foreground)

If the app is open, ErgoTimer handles the task change directly in the app. If the app is in the background, Android handles the scheduled alarm. You do not hear the same task-end sound twice.

Task completion alarms are scheduled using Android's alarm clock mechanism (`AlarmManager.setAlarmClock()`). This ensures the alarm fires at the exact scheduled time even if:
- The device is in power-saving or Doze mode
- The app is backgrounded
- The app is removed from recents

A small alarm clock icon (⏰) appears in the Android status bar while a task alarm is pending. The alarm sound is handled reliably by the Android system, independent of whether the Flutter app is running.

**Important:** To ensure alarms fire reliably, exempt ErgoTimer from battery optimization in your Android settings. See the battery optimization exemption instructions in **Getting Started, Step 1**.

### Next Task Notification (Idle Gap)
When a task completes and the following task is not scheduled to start until a later time, ErgoTimer enters an idle period and returns to the schedule view. A background alarm is pre-scheduled for the next task's start time. When that time arrives:
- If the app is in the foreground, the task starts automatically
- If the app is in the background, a notification is shown to alert you that your next scheduled task is about to begin
- The schedule progresses automatically even if you do not open the app

### Micro-Pause Notification
If micro-pause reminders are enabled, a notification appears at the configured interval during mental tasks, suggesting a short break. Like task completion alarms, micro-pause reminders also use the alarm clock mechanism for reliable delivery.

### Background Schedule Progression
Schedule progression is now reliable and continues even when the app is backgrounded or removed from recents. After a task completes:
1. The task-completion alarm fires at the exact scheduled time (guaranteed by `AlarmManager.setAlarmClock()`)
2. If the next task starts immediately, it does so automatically without requiring app interaction
3. If there is an idle gap, the next-task alarm is armed and fires at the correct time
4. The foreground service is stopped during idle periods and restarted when the next task begins

This is achieved through:
- **Persistent session state** — saved to the device after every state change
- **Exact alarm orchestration** — via Android's `AlarmManager` and `AlarmClock` mode
- **Foreground service** — keeps the process alive while a task is active
- **Broadcast receivers** — recover and re-arm alarms after reboot, time changes, or timezone changes

### Notification Channels
ErgoTimer uses three notification channels:
- **Current Task** — the persistent foreground-service countdown notification
- **Task Completion Alerts** — task end alarms
- **Micro-Pause Reminders** — micro-pause reminder notifications

You can manage these channels individually in Android's system notification settings for ErgoTimer.

---

## 9. Scheduling Logic

### Schedule Generation

When you tap **Generate Schedule**, ErgoTimer builds a complete day schedule as follows:

1. ErgoTimer first runs feasibility checks; if your settings cannot produce a safe schedule, generation is blocked with a clear error
2. **Fixed anchors** are sorted by start time
3. **Mental tasks** are generated into the available gaps, each up to the maximum mental task duration
4. **Breaks** are inserted between mental blocks as needed
5. **Fixed-time anchors** are inserted unchanged at their configured times
6. **Remaining work** continues in any later gaps until the total work target is reached, after subtracting any anchors that count toward work
7. **After-work anchors** are placed immediately after the last generated work block, regardless of any fixed-time anchors scheduled later in the day
8. If no generated work block exists on that day, **after-work anchors** are not placed; they stay enabled in settings and ErgoTimer returns a warning instead

Anchors that are very close together are treated as one block. In those cases, ErgoTimer does not insert generated tasks between them.

### Rest Duration Calculation

The minimum rest time after a mental task is calculated from the battery drain since the last restorative break:

```
min_rest = (battery_at_cycle_start − battery_after_mental_task) × min_physical_duration
```

This value is always rounded up to the nearest 10 minutes.

**Example:**  
Max mental duration = 120 min, Min physical duration = 30 min, Mental task = 60 min  
→ min_rest = (60 / 120) × 30 = 15 min → rounded up to 20 min

If a draining anchor reduced your battery before that mental task, that drain is included in this calculation. This prevents too-short breaks after anchor-heavy periods.

### Anchor-Aware Scheduling

If a generated mental block would overlap a fixed anchor, the scheduler stops filling that gap and inserts the anchor at its exact configured time. Mental work resumes only in the next available gap, and the anchor's energy effect is applied to the mental battery using the anchor duration.

### Work Hours Preservation

The scheduler always ensures that the total mental work time equals the configured Total Work Hours:
- When a task is shortened, an auto-generated task is appended at the end
- When a task is lengthened, previously auto-generated tasks are reduced or removed
- When "Next" is pressed, the unused time is added as a new task at the end (rounded to 5 minutes)

### Hard Constraints

- A mental task will never exceed the configured maximum mental task duration
- A rest or physical break following a mental task will never be shorter than the calculated minimum
- Fixed anchor times are fixed and cannot be overridden
- All tasks have a minimum duration of 10 minutes

---

## 10. Task Types

| Type | Colour | Description |
|---|---|---|
| **Mental Task** | 🟢 Green | Focused work requiring concentration. Drains the mental battery. |
| **Physical Break** | 🔴 Red | Active physical activity (e.g. walking, cycling). Charges the mental battery. |
| **Rest Break** | 🔵 Blue | Quiet rest with minimal activity. Charges the mental battery. |
| **Fixed Anchor (Draining)** | 🟢 Green | A fixed block that drains energy like mental work, for example a meeting. |
| **Fixed Anchor (Neutral)** | ⚪ Grey | A fixed block that reserves time without changing energy, for example lunch or travel. |
| **Fixed Anchor (Restoring)** | 🔵 Blue | A fixed block that restores energy like a break, for example therapy or a planned recovery block. |

---

## 11. Languages

ErgoTimer supports the following languages:

| Language | Code |
|---|---|
| English | `en` |
| Dutch (Nederlands) | `nl` |

To change the language, open Settings → Interface → Language.

---

*For questions or support, contact [ddt3@redgrendel.com](mailto:ddt3@redgrendel.com)*

<div class="right-align">
ErgoTimer version 0.2.9
</div>
