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
   - 3.3 [Alerts](#33-alerts)
   - 3.4 [Interface](#34-interface)
   - 3.5 [Advanced](#35-advanced)
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
- **Add Task** — insert a manual task into your schedule
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

The total number of hours of mental work to schedule in the day. Physical breaks, rest periods, and fixed anchors are not included in this count — only mental tasks.

#### Max Mental Task Duration
**Range:** 30 minutes to 180 minutes (3 hours), in 30-minute increments  
**Default:** 120 minutes (2 hours)

The maximum continuous duration of a single mental task. When a mental task reaches this limit, the scheduler will always insert a break before allowing further mental work. This setting is a hard limit — no mental task in the generated schedule will exceed this value.

#### Min Physical Task Duration
**Range:** 5 minutes to 60 minutes, in 5-minute increments  
**Default:** 15 minutes

The minimum length of a physical or rest break inserted between mental tasks. This is used as a baseline — actual break lengths are calculated using the ratio described in [Section 9](#9-scheduling-logic).

#### Start Time
The time your working day begins. Set the hour and minute using the time picker. The scheduler uses this as the start of the first gap it can fill with generated work.

---

### 3.2 Breaks & Recovery

#### Fixed Anchors

Fixed anchors are non-movable schedule blocks that reserve time for lunch, meetings, appointments, therapy, travel, or planned recovery. Each anchor has:

- **Name** — shown directly in the schedule
- **Anchor type** — determines when the anchor is placed in the schedule
- **Energy effect** — how the anchor affects the mental battery

Anchor types:

- **Fixed time** — placed at a specific start and end time. The start and end times are configured directly. In the anchor list, these show their start and end time.
- **Before work** — placed immediately before the work window starts, with a configurable duration. In the anchor list, these show their type label and duration instead of a time range.
- **After work** — placed immediately after the last generated work block ends, with a configurable duration. Fixed-time anchors scheduled later in the day are not affected. In the anchor list, these show their type label and duration instead of a time range.

Energy effects:

- **Draining** — behaves like mental work for battery purposes
- **Neutral** — reserves time without changing the battery
- **Restoring** — behaves like a restorative break for battery purposes

The scheduler never places generated work inside a fixed anchor. Instead, it fills the gaps before, between, and after anchors.

In settings, each anchor card uses a compact two-row layout: the first row shows the anchor icon, name, and metadata; the second row contains the enable switch and edit/delete controls.

Overlap behavior for fixed-time anchors:

- You can save overlapping fixed-time anchors.
- If overlapping fixed-time anchors are both **enabled**, their cards are highlighted with a red border in settings.
- Schedule generation is blocked when enabled fixed-time anchors overlap. Disable one of the conflicting anchors and generate again.

---

### 3.3 Alerts

#### Sound Alarm on Task End
**Default:** On

When enabled, an audible alarm plays when a task's countdown timer reaches zero. When disabled, the task ends silently (a notification is still shown).

#### Alarm Ringtone
Select which sound plays when a task ends. Tap the dropdown to choose from the available options. Use the **Test Sound** button to preview the selected sound.

#### Micro Pause Reminder
**Range:** Off, 5 to 60 minutes in 5-minute increments  
**Default:** Off

When enabled, a reminder notification is shown during mental tasks at the specified interval. For example, if set to 30 minutes, a reminder will appear 30 minutes after a mental task begins, encouraging a short break (like making a cup of coffee). Micro-pauses are not separate scheduled tasks — they are reminders within the current task.

---

### 3.4 Interface

#### Language
Choose between **English** and **Dutch**. The app will display all text in the selected language.

#### Interface Mode
**Default:** Calm

ErgoTimer offers three interface modes:
- **Standard** — task blocks show task name, duration, and per-task energy range (start % → end %). The active-task header shows the live battery percentage bar.
- **Calm** — task blocks show task name and duration with softer visual styling; per-task energy range is hidden in blocks. The active-task header still shows the live battery percentage bar.
- **Minimal** — task blocks are icon-only and the active-task header hides the battery percentage bar.

---

### 3.5 Advanced

#### Debug Mode (Fast Timers)
**Default:** Off

When enabled, time is accelerated: 1 hour is treated as 1 minute. This mode is intended for testing and development only. Do not use this mode during normal use.

---

## 4. Schedule View

The schedule is displayed as a scrollable vertical timeline (calendar view). A time axis on the left shows clock times; colour-coded task blocks are placed at their exact positions on the axis. A horizontal "now" line moves through the timeline as time passes, so you can always see where you are in your day at a glance.

If there is an empty gap between two scheduled tasks, ErgoTimer shows a subtle tappable gap row in that slot. Tapping the gap opens the Add Task dialog pre-filled with the full start and end time of that gap, so you can insert a manual task directly into the free period.

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
Tap **Pause** to pause the countdown timer. The task end time adjusts accordingly. Tap **Resume** to continue the task.

When the app is paused and moved to the background, the alarm is pre-scheduled so it fires at the correct time even if the app is minimised.

### Stop
Tap **Stop** to end the current task immediately without moving to the next one. The schedule remains as-is. Use this if you need to exit the current task flow without advancing.

### Next
Tap **Next** to end the current task early and move to the next task. The remaining time from the current task is rounded to the nearest 5 minutes and added as an additional mental task at the end of the schedule, so that your total work hours are still met.

---

## 6. Adjusting the Schedule

You can modify individual tasks in the schedule while the day is running (or before starting).

Tap any task block to open its detail sheet with the available actions.

### Adding a Task in an Empty Gap
If there is visible free time between two tasks, tap the gap row between them to open the time-blocked Add Task dialog. The dialog is pre-filled with the full gap boundaries. ErgoTimer then passes the task directly to the scheduler, which may insert a safety break or split a large mental task into multiple mental and break blocks if needed.

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

ErgoTimer uses Android notifications to keep you informed while the app is running in the background.

### Current Task Notification (Persistent)
A persistent notification is shown in the Android notification bar while a task is active. It displays:
- The current task name
- A live countdown timer — implemented using Android's native chronometer, so the displayed time updates continuously and correctly even when the app is in the background, without requiring the app to be running.

### Task Completion Notification
When a task's timer reaches zero:
- An alarm sound plays (if enabled)
- A notification is shown with the message "Task Complete!"
- A dialog appears in the app (if the app is in the foreground)

Task completion alarms are scheduled using Android's alarm clock mechanism (`AlarmManager.setAlarmClock()`). This ensures the alarm fires at the exact scheduled time even if the device is in power-saving or Doze mode. A small alarm clock icon (⏰) appears in the Android status bar while a task alarm is pending.

### Next Task Notification (Idle Gap)
When a task completes and the following task is not scheduled to start until a later time, ErgoTimer enters an idle period and returns to the schedule view with no active task. A background alarm is pre-scheduled for the next task's start time. When that time arrives:
- If the app is in the foreground, the task starts automatically
- If the app is in the background, a notification is shown to alert you that your next scheduled task is about to begin

### Micro-Pause Notification
If micro-pause reminders are enabled, a notification appears at the configured interval during mental tasks, suggesting a short break. Like task completion alarms, micro-pause reminders also use the alarm clock mechanism for reliable delivery.

### Notification Channels
ErgoTimer uses two notification channels:
- **Current Task** — the persistent task-progress notification
- **Task Completion Alerts** — alarm notifications and micro-pause reminders

You can manage these channels individually in Android's system notification settings for ErgoTimer.

---

## 9. Scheduling Logic

### Schedule Generation

When you tap **Generate Schedule**, ErgoTimer builds a complete day schedule as follows:

1. **Fixed anchors** are sorted by start time
2. **Mental tasks** are generated into the available gaps, each up to the maximum mental task duration
3. **Breaks** are inserted between mental blocks as needed
4. **Fixed-time anchors** are inserted unchanged at their configured times
5. **Remaining work** continues in any later gaps until the total work target is reached
6. **After-work anchors** are placed immediately after the last generated work block, regardless of any fixed-time anchors scheduled later in the day

### Rest Duration Calculation

The minimum rest time after a mental task is calculated proportionally:

```
min_rest = (mental_task_duration / max_mental_duration) × min_physical_duration
```

This value is always rounded up to the nearest 10 minutes.

**Example:**  
Max mental duration = 120 min, Min physical duration = 30 min, Mental task = 60 min  
→ min_rest = (60 / 120) × 30 = 15 min → rounded up to 20 min

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
ErgoTimer version 0.2.0
</div>
