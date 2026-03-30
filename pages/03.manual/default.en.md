---
title: Manual
---

# ErgoTimer — Reference Manual

## Table of Contents

1. [Overview](#1-overview)
2. [Main Screen](#2-main-screen)
3. [Settings](#3-settings)
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

Once a schedule is generated, the screen shows the full day in a colour-coded list. Two buttons appear at the bottom:
- **Start Day** — starts the schedule from the first task
- **Start from Now** — starts from the task that corresponds to the current time

---

## 3. Settings

Open settings by tapping the **⚙️** icon in the top-right corner of the main screen. Settings are organised into collapsible sections. Tap a section header to expand or collapse it. Tap **Generate Schedule** at the bottom to apply your settings and create a new schedule.

### 3.1 Core Schedule

#### Total Work Hours
**Range:** 1 hour to 9 hours, in 0.5-hour increments  
**Default:** 4 hours

The total number of hours of mental work to schedule in the day. Physical breaks, rest periods, bike rides, and lunch are not included in this count — only mental tasks.

#### Max Mental Task Duration
**Range:** 30 minutes to 180 minutes (3 hours), in 30-minute increments  
**Default:** 120 minutes (2 hours)

The maximum continuous duration of a single mental task. When a mental task reaches this limit, the scheduler will always insert a break before allowing further mental work. This setting is a hard limit — no mental task in the generated schedule will exceed this value.

#### Min Physical Task Duration
**Range:** 5 minutes to 60 minutes, in 5-minute increments  
**Default:** 15 minutes

The minimum length of a physical or rest break inserted between mental tasks. This is used as a baseline — actual break lengths are calculated using the ratio described in [Section 9](#9-scheduling-logic).

#### Start Time
The time your working day begins. Set the hour and minute using the time picker. If a bike ride before work is configured, the bike ride will start at this time and the first mental task will begin after the bike ride ends.

---

### 3.2 Breaks & Recovery

#### Lunch Break
**Default:** Off

Toggle on to include a fixed lunch break in your schedule. When enabled, set:

- **Lunch Start** — the time at which lunch begins (e.g. 12:30)
- **Lunch End** — the time at which lunch ends (e.g. 13:00)

Lunch is a fixed anchor in the schedule. It cannot be moved by task adjustments. When a mental task would overlap with lunch, it is automatically split. A 30-minute rest period is automatically inserted after lunch ends.

#### Bike Ride Before Work
**Range:** 0 to 60 minutes, in 5-minute increments  
**Default:** 0 (disabled)

If set to a value greater than 0, a bike ride task is added to the start of the schedule, beginning at the configured start time. The first mental task begins after the bike ride ends.

#### Bike Ride After Work
**Range:** 0 to 60 minutes, in 5-minute increments  
**Default:** 0 (disabled)

If set to a value greater than 0, a bike ride task is added to the end of the schedule, after all mental work and rest tasks.

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

#### Calm Interface Mode
**Default:** Off

When enabled, the interface reduces visual complexity:
- Increased spacing between elements
- Secondary controls are hidden behind a single tap
- Better suited for people who find dense interfaces overwhelming

---

### 3.5 Advanced

#### Debug Mode (Fast Timers)
**Default:** Off

When enabled, time is accelerated: 1 hour is treated as 1 minute. This mode is intended for testing and development only. Do not use this mode during normal use.

---

## 4. Schedule View

The schedule is displayed as a vertical list of tasks, each represented as a coloured tile.

### Task Tile Layout

Each tile shows:
- **Task colour** (left border) — indicates task type (see [Section 10](#10-task-types))
- **Task name** — e.g. "Mental Task", "Physical Break", "Lunch"
- **Time range** — start time and end time (e.g. 09:00 – 10:30)
- **Duration** — shown in hours and/or minutes
- **Mental battery range** — the energy level at the start and end of the task (for mental tasks and breaks)

### Task States

- **Upcoming** — normal appearance, full colour
- **Active (current task)** — shown prominently at the top of the screen with a large timer
- **Completed** — shown with strikethrough text

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

You can modify individual tasks in the schedule list while the day is running (or before starting).

To reveal adjustment controls for a task, tap the **edit icon** on the right side of the task tile.

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

- **Drains** during mental tasks and lunch
- **Charges** during physical breaks, rest breaks, and bike rides
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
- The remaining time (updated approximately every 30 seconds)

### Task Completion Notification
When a task's timer reaches zero:
- An alarm sound plays (if enabled)
- A notification is shown with the message "Task Complete!"
- A dialog appears in the app (if the app is in the foreground)

### Micro-Pause Notification
If micro-pause reminders are enabled, a notification appears at the configured interval during mental tasks, suggesting a short break.

### Notification Channels
ErgoTimer uses two notification channels:
- **Current Task** — the persistent task-progress notification
- **Task Completion Alerts** — alarm notifications and micro-pause reminders

You can manage these channels individually in Android's system notification settings for ErgoTimer.

---

## 9. Scheduling Logic

### Schedule Generation

When you tap **Generate Schedule**, ErgoTimer builds a complete day schedule as follows:

1. **Optional bike ride (before)** — added at the start time if configured
2. **Mental tasks** — work hours divided into blocks, each up to the maximum mental task duration
3. **Breaks** — a physical or rest break is inserted after each mental task block
4. **Lunch** — inserted as a fixed anchor at the configured lunch time, with a 30-minute rest afterwards
5. **Remaining work** — mental tasks continue after the post-lunch rest
6. **Optional bike ride (after)** — appended at the end if configured

### Rest Duration Calculation

The minimum rest time after a mental task is calculated proportionally:

```
min_rest = (mental_task_duration / max_mental_duration) × min_physical_duration
```

This value is always rounded up to the nearest 10 minutes.

**Example:**  
Max mental duration = 120 min, Min physical duration = 30 min, Mental task = 60 min  
→ min_rest = (60 / 120) × 30 = 15 min → rounded up to 20 min

### Lunch Splitting

If a mental task would overlap with the configured lunch time, it is automatically split:
- The first part ends at lunch start time (minimum 10 minutes)
- Lunch is inserted at the fixed time
- A 30-minute rest follows lunch
- The remaining work resumes after the rest

### Work Hours Preservation

The scheduler always ensures that the total mental work time equals the configured Total Work Hours:
- When a task is shortened, an auto-generated task is appended at the end
- When a task is lengthened, previously auto-generated tasks are reduced or removed
- When "Next" is pressed, the unused time is added as a new task at the end (rounded to 5 minutes)

### Hard Constraints

- A mental task will never exceed the configured maximum mental task duration
- A rest or physical break following a mental task will never be shorter than the calculated minimum
- Lunch time is fixed and cannot be overridden
- All tasks have a minimum duration of 10 minutes

---

## 10. Task Types

| Type | Colour | Description |
|---|---|---|
| **Mental Task** | 🟢 Green | Focused work requiring concentration. Drains the mental battery. |
| **Physical Break** | 🔴 Red | Active physical activity (e.g. walking, cycling). Charges the mental battery. |
| **Rest Break** | 🔵 Blue | Quiet rest with minimal activity. Charges the mental battery. |
| **Lunch** | 🟣 Purple | Fixed lunch period. Does not charge or drain the battery in the same way as work or rest. |
| **Bike Ride (Before)** | 🔴 Red | Cycling before the working day begins. |
| **Bike Ride (After)** | 🔴 Red | Cycling after the working day ends. |
| **Rest (After Lunch)** | 🔵 Blue | Automatic 30-minute rest inserted after every lunch period. |

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
