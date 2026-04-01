# System Overview — PLC Fault & Alarm Management System

## Purpose

This project demonstrates a structured approach to alarm and fault handling in a PLC-controlled system using Studio 5000.

The goal was to move beyond basic logic and build a system that can:

* detect faults
* latch them
* record when they occurred
* require proper reset conditions before clearing

---

## System Architecture

The program is divided into dedicated routines:

* Fault Detection — identifies real-time fault conditions
* Fault Latching — stores faults once they occur
* Fault Timestamps — records the exact time of occurrence
* Fault Reset — ensures faults can only be cleared safely
* Fault Summary — combines all faults into system-level status
* Fault Display — assigns fault codes for operator visibility

---

## Key Features

* 10 independent fault conditions
* Unique fault codes for each condition
* Timestamp capture using real-time clock (GSV)
* One-shot logic to prevent repeated event logging
* Reset interlock requiring condition clearance
* System-wide fault summary and alarm output

---

## Design Approach

Each fault follows the same structure:

Condition → Latch → Timestamp → Reset Permissive → Reset

This ensures:

* faults are not lost
* operators understand what happened
* the system cannot be reset into an unsafe state

---

## Why This Matters

In real-world systems, fault handling is just as important as normal operation.

This project reflects how industrial systems:

* track failures
* enforce safe recovery
* provide meaningful diagnostics to operators


## Example Fault Flow

Condition Detected → Fault Latched → Timestamp Captured → Alarm Triggered → Reset Allowed Only After Condition Clears

## Example Timestamp

E-Stop Fault:
[2026, 3, 30, 14, 22, 18]

## Program Structure

- Modular routines for clarity and scalability
- Fault logic separated from process logic
- Designed for maintainability and troubleshooting
