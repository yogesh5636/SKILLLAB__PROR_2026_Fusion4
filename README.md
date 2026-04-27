# SKILL LAB PRACTICAL HACKATHON

---

# 1. Team Identity

## 1.1 Studio / Group Name

### Fusion4

## 1.2 Team Members

| Name                  | Primary Role                    | Secondary Role                | Strengths Brought to the Project         |
| --------------------- | ------------------------------- | ----------------------------- | ---------------------------------------- |
| `Yogesh Harwani`      | `Coding`                        | `Documentation / Electronics` | `Logic design, MicroPython, C, README`      |
| `Dnyaneshwari Joshi`  | `Electronics`                   | `Coding`                      | `Wiring, component testing, hardware`    |
| `Saundarya Daware`    | `Electronics / Fabrication`     | `Coding`                      | `Assembly, sensor calibration, finishing`|
| `Anuj Jakkar`         | `Mechanical Fabrication`        | `Electronics`                 | `Drum build, housing structure, hardware` |

---

## 1.3 Project Title

### MedDrop

> *Your personal, automated medication dispenser — with a personality that refuses to be ignored.*

<img width="1600" height="1131" alt="product image" src="https://github.com/yogesh5636/SKILLLAB__PROR_2026_Fusion4/blob/main/images/1A.jpeg" />

---

## 1.4 One-Line Pitch

`An automated pill dispenser with a stubborn escalating personality — it will not stop until you physically claim your pill.`

---

## 1.5 Expanded Project Idea

MediDrop is an automated, smart pill dispensing system built on the Raspberry Pi Pico (RP2040). At its core, the device uses a servo-driven rotating drum to organize and dispense medication at scheduled intervals — with zero manual intervention required after setup.

What sets MediDrop apart is its **intelligent, staged escalation mechanism**. When a dose is due, the drum rotates to the correct slot and dispenses the pill. The system then plays a voice prompt through the ISD1820 module. If the user does not respond within 30 seconds, a loud buzzer fires. If still ignored after 60 seconds, the system triggers an emergency alert to a predefined contact — a family member or caregiver.

The user can only silence all alerts by physically pressing a capacitive touch sensor mounted at the pill tray. This forces real-world physical interaction — it cannot be dismissed from a bed or another room.

By combining embedded systems, staged behavioral escalation, and human-centric physical design, MediDrop transforms routine medication intake from a forgettable passive reminder into an active, unavoidable interaction loop.

---

# 2. Philosophy Fit

## 2.1 Experience, Not Social Problem

MediDrop is not just a health tool — it is a **stubborn machine with a personality**. It is designed to create a specific, memorable interaction experience:

- It *gives* (dispenses your pill)
- It *asks* (plays a voice prompt)
- It *demands* (escalates to buzzer)
- It *tattles* (contacts your family if you still ignore it)

The device behaves like a persistent, caring, slightly annoying parent. It does not allow passivity. Every alert must end with a **physical action** — touching the sensor at the tray. This turns a mundane health task into something that has character, stakes, and a clear resolution.

The experience is both delightful and slightly uncomfortable in the best way — exactly the kind of "strange but engaging machine" the brief calls for.

---

# 3. Inspiration

## 3.1 References

| Source Type          | Title / Link                          | What Inspired You                                                                                        |
| -------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `Concept / Hardware` | `"The Useless Box" (servo project)`   | `How a simple physical actuator and a single sensor can give hardware a demanding, stubborn personality.` |
| `Product / Toy`      | `Tamagotchi / Digital Pets`           | `A device that demands physical care on a strict schedule and escalates its distress if ignored.`         |
| `Real-world problem` | `Personal experience with elderly relatives` | `Watching family members miss medication because passive reminders are too easy to dismiss.`        |

---

## 3.2 Original Twist

Most smart pill dispensers are passive containers with digital alarms. They can be snoozed, ignored, or silenced from across the room. MediDrop introduces a **closed-loop physical handshake with enforced accountability**.

The system does not accept silence as an answer. It escalates through three stages — voice, buzzer, emergency contact — each stage requiring that the system receive a physical response at the device itself. The capacitive touch sensor is deliberately placed at the pill output tray, meaning the user must walk to the device and reach the tray to acknowledge.

This design principle — **making compliance a physical act, not a digital tap** — is the core innovation. The loop is only closed when a real human hand reaches the machine.

---

# 4. Project Intent

## 4.1 User Journey

MediDrop honestly didn't start as a clean idea. We cycled through concepts — too simple, too generic, too easy to ignore. Then we stopped asking *"What can we build?"* and asked *"What have we actually experienced?"*

Everyone on the team had watched a grandparent or parent miss medication. Not because they didn't care — but because every reminder they had was too easy to swipe away.

That frustration became MediDrop.

Here is how the experience works from the user's side:

You are in the middle of your day — working, watching TV, napping. At the scheduled time, MediDrop activates. The drum rotates with a soft mechanical click. A pill lands in the tray. A pre-recorded voice says: *"It's time for your medicine. Please take your pill."*

If you respond — you walk over, touch the sensor, take the pill. Done. The LCD says *"Dose acknowledged. Next dose in 8 hours."* Life continues.

If you don't respond within 30 seconds — the buzzer starts. Not a gentle tone. A persistent, repeating alarm that is deliberately difficult to ignore from another room.

Now you have to get up. You have to physically walk to the device. You have to touch the sensor at the tray to make it stop.

If 60 seconds pass and the sensor is still untouched — the system assumes something may be wrong and sends an alert to a predefined contact. Your family member gets notified.

MediDrop starts as a polite reminder. It becomes a persistent alarm. If needed, it becomes a safety net. The escalation is not punishment — it is care with consequences.

---

# 5. Definition of Success

## 5.1 Definition of "Usable"

MediDrop is considered usable when all five conditions are met in a single uninterrupted run:

1. The servo rotates and dispenses a pill at the correct scheduled time without manual triggering
2. The ISD1820 voice module plays the reminder prompt clearly and audibly
3. The buzzer escalates automatically if no touch response is received within 30 seconds
4. The capacitive touch sensor successfully stops all active alerts when pressed
5. The countdown resets correctly and the LCD displays the next scheduled dose time

---

## 5.2 Minimum Usable Version

The smallest version of MediDrop that still delivers the core experience:

- Servo-driven 4-slot pill drum dispenses one slot per scheduled interval
- ISD1820 plays a voice reminder on dispense
- Active buzzer escalates if touch sensor not pressed within 30 seconds
- Capacitive touch sensor at the tray silences all alerts
- LCD displays current status and countdown to next dose

This minimal version already delivers the defining experience: **a reminder you cannot ignore without physically claiming your pill.**

---

## 5.3 Stretch Features

Features that are designed but not essential for the core experience:

- **Pico W + WiFi alerts:** Send HTTP notification to a family member's phone on missed dose, instead of just a buzzer pattern
- **GSM module:** Make an actual phone call on critical escalation, without needing WiFi
- **DS3231 RTC module:** Replace countdown timer with real clock-based scheduling (e.g., 8AM, 2PM, 8PM) that survives power cuts
- **Multiple medicine profiles:** Extend drum to 8 slots, allow different medicines per slot
- **Mobile dashboard:** Web UI to set schedule, view dose history, and receive alerts
- **Face recognition:** Pico camera add-on to confirm the correct person is collecting the pill

---

# 6. System Overview

## 6.1 Project Type

- [x] Electronics-based
- [x] Mechanical
- [x] Sensor-based
- [ ] App-connected
- [x] Motorized
- [x] Sound-based
- [x] Screen/UI-based
- [x] Fabricated structure
- [ ] Game logic based
- [ ] Installation
- [ ] Other

---

## 6.2 High-Level System Description

MediDrop works as a staged input–process–output system with a physical interaction layer.

**Input:** Time (countdown timer) and user response (capacitive touch sensor). The system is triggered by elapsed time, not external commands.

**Processing:** The Raspberry Pi Pico (RP2040) runs all logic. It manages the countdown, decides when to activate each stage of the escalation sequence, and tracks whether the touch sensor has been pressed.

**Output:** Multiple simultaneous outputs. The servo motor rotates the pill drum. The ISD1820 voice module plays a reminder. The active buzzer fires on escalation. The LCD updates status in real-time. On critical escalation, an alert is sent to a predefined contact.

**Physical Structure:** A cardboard pill drum with 4 compartments sits inside a housing box. A fixed output hole at the bottom allows only one slot to empty at a time. The touch sensor is mounted on the exterior face at the tray, so the user must reach the physical tray to acknowledge.

**App Interaction:** None in the current build. Extended version would use Pico W to send HTTP alerts.

---

## 6.3 Input / Output Map

| System Part                     | Type       | What It Does                                                  |
| ------------------------------- | ---------- | ------------------------------------------------------------- |
| Countdown Timer (utime)         | Input      | Triggers dispense cycle at each scheduled interval            |
| Capacitive Touch Sensor (TTP223)| Input      | User physically acknowledges pill was taken — stops all alerts|
| Raspberry Pi Pico (RP2040)      | Processing | Controls all logic — timing, escalation, outputs              |
| Servo Motor (SG90/MG995)        | Output     | Rotates pill drum 90° to align next slot with output hole     |
| ISD1820 Voice Module            | Output     | Plays pre-recorded voice reminder to user                     |
| Active Buzzer                   | Output     | Escalation alert — fires if voice prompt ignored for 30s      |
| LCD 16x2 (I2C)                  | Output     | Shows countdown to next dose, current status, dose number     |
| Emergency Alert (simulated)     | Output     | Triggered if touch sensor not pressed within 60s of dispense  |

---

# 7. Sketches and Visual Planning

## 7.1 Concept Sketch

Early rough sketch of the full idea — drum mechanism, housing, and user interaction point.

<img alt="image" src="https://github.com/yogesh5636/SKILLLAB__PROR_2026_Fusion4/blob/main/images/7A.jpeg" />

---

## 7.2 Labeled Build Sketch

Labeled diagram showing structure, electronics placement, user touch point, moving parts, and output elements.

<img alt="image" src="https://github.com/yogesh5636/SKILLLAB__PROR_2026_Fusion4/blob/main/images/Screenshot%202026-04-27%20182612.png">

---

## 7.3 Approximate Dimensions

| Dimension        | Value   |
| ---------------- | ------- |
| Length           | `16 cm` |
| Width            | `16 cm` |
| Height           | `12 cm` |
| Estimated weight | `380 g` |

---

# 8. Electronics Planning

## 8.1 Electronics Used

| Component                     | Quantity | Purpose                                                   |
| ----------------------------- | -------: | --------------------------------------------------------- |
| Raspberry Pi Pico (RP2040)    | `1`      | Main controller — timing, escalation logic, all outputs   |
| Servo Motor (SG90 / MG995)    | `1`      | Rotates pill drum 90° per dose                            |
| ISD1820 Voice Module          | `1`      | Plays pre-recorded voice reminder prompt                  |
| Active Buzzer (5V)            | `1`      | Escalation alert if voice prompt ignored                  |
| Capacitive Touch Sensor TTP223| `1`      | Physical acknowledgment — user must press to stop alerts  |
| LCD 16x2 (I2C, 0x27)         | `1`      | Displays countdown, dose number, system status            |
| 5V Li-ion Power Bank          | `1`      | Portable power supply for full standalone operation       |
| IR Sensor                     | `1`      | Detects pill drop at output tray — confirms dispense      |
| Jumper wires + breadboard     | `misc`   | Prototyping connections                                   |
| Cardboard / plastic drum      | `1`      | Fabricated 4-slot pill compartment                        |

---

## 8.2 Wiring Plan

The Raspberry Pi Pico is the central controller. All components connect directly to its GPIO pins.

**Servo Motor:** Signal wire → GPIO 15 (PWM-capable). Power (5V) → VBUS. GND → GND rail.

**ISD1820 Voice Module:** PLAYE pin → GPIO 14 (trigger playback with LOW pulse). Module powered from 3.3V pin on Pico. SP+ and SP- to small speaker.

**Active Buzzer:** Positive pin → GPIO 12. Negative → GND. PWM pattern generated in MicroPython for escalation tone.

**Capacitive Touch Sensor (TTP223):** OUT pin → GPIO 11 (digital input, pull-down enabled in code). Triggers acknowledgment on HIGH signal when user touches pad.

**LCD 16x2 I2C:** SDA → GPIO 4. SCL → GPIO 5. VCC → 3.3V. GND → GND. I2C address: 0x27.

**IR Sensor (tray confirmation):** OUT → GPIO 10. Detects when pill has physically landed in the output tray.

**Power:** Entire system powered from a single 5V USB power bank via Pico's VBUS pin. All components share a common GND rail. Servo powered from VBUS (not 3.3V) to handle current draw.

---

## 8.3 Circuit Diagram

<img alt="image" src="https://github.com/yogesh5636/SKILLLAB__PROR_2026_Fusion4/blob/main/images/8A.jpeg">

---

# 9. Power Plan

| Question           | Response                                                                                     |
| ------------------ | -------------------------------------------------------------------------------------------- |
| Power source       | 5V Li-ion power bank (USB output)                                                            |
| Voltage required   | 5V for Pico (VBUS) and servo, 3.3V for sensors and LCD via Pico's onboard regulator         |
| Current concerns   | Servo draws up to 500mA peak under load — powered from VBUS only, not 3.3V rail             |
| Safety concerns    | Avoid reverse polarity on ISD1820. Add 100µF capacitor across servo power lines to reduce noise spike. Never power servo from Pico's 3.3V output. |

---

# 10. Software Planning

## 10.1 Software Tools

| Tool / Platform        | Purpose                                                        |
| ---------------------- | -------------------------------------------------------------- |
| `MicroPython`          | Programming language running on Raspberry Pi Pico              |
| `Thonny IDE`           | Development environment — write, upload, and debug on Pico     |
| `machine.PWM`          | Controls servo position via PWM signal                         |
| `machine.I2C`          | Controls LCD display over I2C protocol                         |
| `utime / ticks_ms()`   | Handles countdown timer, scheduling intervals, debounce delays |
| `machine.Pin`          | GPIO control for buzzer, touch sensor, ISD1820 trigger         |

---

## 10.2 Software Logic

**Startup behavior:**
Pico initializes all GPIO pins on boot. Servo moves to home position (Slot 1 aligned with output hole). LCD displays `MediDrop Ready` and the time remaining until the first scheduled dose. ISD1820 plays a short startup chime.

**Input handling:**
System monitors two inputs in a continuous loop — the countdown timer via `utime.ticks_ms()` and the capacitive touch sensor state polled every 100ms.

**Sensor reading:**
Touch sensor (GPIO 11) is polled every 100ms during an active alert cycle. A LOW→HIGH transition with 500ms debounce confirms a valid user acknowledgment. IR tray sensor (GPIO 10) confirms pill physically dropped after servo rotation.

**Decision logic:**
```
Stage 0 — Countdown running:
  → LCD shows time remaining
  → Poll touch sensor (no action during countdown)

Stage 1 — Timer = 0:
  → Servo rotates 90° (1 slot)
  → IR sensor confirms pill dropped
  → ISD1820 plays voice prompt
  → Start 30-second acknowledgment window

Stage 2 — 30s elapsed, no touch:
  → Buzzer activates (500ms on / 500ms off pattern)
  → Start 30-second second window

Stage 3 — 60s elapsed, no touch:
  → Emergency alert triggered (buzzer SOS pattern + future: HTTP/call)
  → System waits for manual reset

If touch received at any stage:
  → All alerts stop immediately
  → LCD: "Dose acknowledged"
  → Dose counter increments
  → Countdown resets for next scheduled dose
```

**Output behavior:**
Servo rotates by 90° per dose using PWM pulse width (1ms–2ms range). ISD1820 triggered by a LOW pulse on PLAYE pin. Buzzer fires in repeating pattern via `utime.sleep_ms()` loop. LCD updates status string every second.

**Communication logic:**
Current build: standalone, no WiFi. Emergency alert is simulated via SOS buzzer pattern. Extended version: Pico W sends HTTP POST to a webhook endpoint on critical escalation miss.

**Reset behavior:**
After touch acknowledgment, all alert states clear and countdown restarts. After all 4 doses in a day are dispensed, LCD shows `All doses complete — See you tomorrow` and system halts until power cycle.

---

## 10.3 Code Flowchart

<img alt="image" src="https://github.com/yogesh5636/SKILLLAB__PROR_2026_Fusion4/blob/main/images/9A.jpeg">

**Text description of flow:**
```
START
  → Initialize Pico, GPIO pins, LCD, Servo home position
  → Display countdown to next dose on LCD

LOOP:
  → Has countdown reached zero?
    NO  → Update LCD countdown, poll touch sensor (no action), loop back
    YES → Rotate servo 90° (1 slot forward)
        → Wait 400ms for pill to fall
        → IR sensor detects pill in tray?
            NO  → LCD: "Slot empty — refill!" + buzzer alarm + halt
            YES → Play ISD1820 voice prompt
                → Start 30-second window, poll touch sensor

  → Touch received within 30s?
    YES → All alerts off → LCD: "Dose acknowledged" → Reset countdown → LOOP
    NO  → Activate buzzer escalation
        → Start 30-second second window, poll touch sensor

  → Touch received within next 30s?
    YES → All alerts off → LCD: "Dose acknowledged" → Reset countdown → LOOP
    NO  → Emergency alert (SOS buzzer pattern)
        → LCD: "Alert sent — please check on patient"
        → HALT — wait for manual power reset

  → Dose count = 4?
    YES → LCD: "All doses complete" → HALT
    NO  → Continue LOOP
```

---

# 11. Bill of Materials

## 11.1 Full BOM

| Item                          | Quantity | In Kit? | Need to Buy? | Est. Cost (₹) | Spec                      | Why This Choice?                                        |
| ----------------------------- | -------: | ------- | ------------ | ------------: | ------------------------- | ------------------------------------------------------- |
| Raspberry Pi Pico (RP2040)    | `1`      | `Yes`   | `No`         | `0`           | Dual-core, MicroPython    | Real-time logic, low power, easy to program             |
| Servo Motor                   | `1`      | `Yes`   | `No`         | `0`           | SG90 / MG995              | Precise 90° rotation per slot — DC motor can't do this  |
| ISD1820 Voice Module          | `1`      | `Yes`   | `No`         | `0`           | 8–20s recording time      | Human voice prompt is more effective than a beep        |
| Active Buzzer                 | `1`      | `Yes`   | `No`         | `0`           | 5V active buzzer          | Loud escalation alert, simple digital trigger           |
| Capacitive Touch Sensor       | `1`      | `Yes`   | `No`         | `0`           | TTP223 module             | Requires deliberate touch — cannot be accidentally triggered |
| LCD 16x2 (I2C)                | `1`      | `Yes`   | `No`         | `0`           | I2C address 0x27          | Shows countdown, status, dose number in real-time       |
| IR Sensor                     | `1`      | `Yes`   | `No`         | `0`           | Digital output IR module  | Confirms pill physically landed in tray                 |
| 5V Li-ion Power Bank          | `1`      | `No`    | `Yes`        | `150`         | USB 5V output             | Portable, stable 5V — avoids wall-power dependency      |
| Cardboard / plastic drum      | `1`      | `No`    | `No`         | `0`           | Hand-fabricated           | 4-slot pill compartment, mounted on servo shaft         |
| Jumper wires + breadboard     | `misc`   | `Yes`   | `No`         | `0`           | —                         | Prototyping and connections                             |

---

## 11.2 Material Justification

**Raspberry Pi Pico over Arduino:** The Pico runs MicroPython natively, has dual cores for handling timing and I/O simultaneously, and draws significantly less power — important for a device running all day on battery.

**Servo over DC motor:** The pill drum requires precise 90° increments to align each slot with the output hole. A DC motor without an encoder cannot achieve this. The servo provides exact position control through PWM pulse width.

**ISD1820 over buzzer-only:** A human voice prompt gets a response more reliably than a generic tone — especially for elderly users. The ISD1820 stores a pre-recorded clip that plays on a single digital trigger pulse.

**Capacitive touch over push button:** Requires deliberate, intentional contact. Cannot be accidentally triggered by nearby objects. No mechanical wear over thousands of cycles.

**Power bank over wall adapter:** A wall-powered device fails in a power cut. A power bank keeps MediDrop running for 6–8 hours continuously — covers a full medication day.

---

## 11.3 Items Procured

| Item              | Why Needed                        | Purchase Link  | Latest Safe Date | Status     |
| ----------------- | --------------------------------- | -------------- | ---------------- | ---------- |
| 5V Li-ion Power Bank | Portable power for full system | Local store    | Day before build | `Received` |
| Cardboard / craft box | Pill drum and housing frame   | Campus supply  | Day of build     | `Received` |

---

## 11.4 Budget Summary

| Budget Item           | Estimated Cost (₹) |
| --------------------- | -----------------: |
| Electronics (from kit)| `0`                |
| Purchased components  | `150`              |
| Fabrication materials | `0` *(campus)*     |
| Contingency           | `100`              |
| **Total**             | **`250`**          |

---

## 11.5 Budget Reflection

The core electronics were all available in the provided kit, keeping purchased costs to ₹150 (power bank only). If cost was a constraint, the power bank could be replaced with a 4×AA battery holder (₹30) at the expense of run time. The LCD could be removed and status communicated through LED patterns only, saving ₹0 since it was in the kit anyway. The overall BOM is already near-minimal.

---

# 12. Planning the Work

## 12.1 Team Working Agreement

**How tasks are divided:** Each member owns their primary role area. Yogesh owns all code. Dnyaneshwari and Saundarya own wiring and sensor testing. Anuj owns the physical drum and housing fabrication.

**How decisions are made:** If there is disagreement, we build a quick 15-minute test to find out which approach works — we do not debate without data.

**How progress is checked:** At the end of each 2-hour milestone block, each person confirms their area is ready for integration. If not, the team member with the lightest current load assists.

**If a task is delayed:** No task stays unassigned. The blocked member escalates immediately — not at the milestone check.

**How documentation is maintained:** Yogesh updates the README in real-time during the build. Not after. The README should never be more than 30 minutes behind the actual build state.

---

## 12.2 Task Breakdown

| Task ID | Task                                      | Owner          | Est. Hours | Deadline   | Dependency   | Status   |
| ------- | ----------------------------------------- | -------------- | ---------: | ---------- | ------------ | -------- |
| T1      | Finalize concept, BOM, component check    | All            | `1`        | Hour 1     | None         | `Done`   |
| T2      | Build cardboard pill drum (4 slots, 90°)  | Anuj           | `1`        | Hour 1     | None         | `Done`   |
| T3      | Wire servo + test 90° rotation via Pico   | Dnyaneshwari   | `1`        | Hour 2     | T1           | `Done`   |
| T4      | Wire ISD1820 + record 3 voice clips       | Saundarya      | `1`        | Hour 2     | T1           | `Done`   |
| T5      | Wire buzzer + touch sensor + LCD          | Dnyaneshwari   | `0.5`      | Hour 2     | T1           | `Done`   |
| T6      | Write MicroPython: timer + servo rotation | Yogesh         | `1.5`      | Hour 3     | T3           | `Done`   |
| T7      | Write escalation logic (3-stage)          | Yogesh         | `1`        | Hour 3     | T4, T5, T6   | `Done`   |
| T8      | Integrate drum + electronics + code       | All            | `1`        | Hour 3     | T2–T7        | `Done`   |
| T9      | Full cycle testing + bug fixes            | All            | `1`        | Hour 4     | T8           | `Done`   |
| T10     | Final documentation + README update       | Yogesh         | `1`        | Hour 4     | T9           | `Done`   |

---

## 12.3 Responsibility Split

| Area              | Main Owner      | Support Owner   |
| ----------------- | --------------- | --------------- |
| Concept           | `Yogesh`        | `All`           |
| Electronics       | `Dnyaneshwari`  | `Saundarya`     |
| Coding            | `Yogesh`        | `Dnyaneshwari`  |
| Mechanical build  | `Anuj`          | `Saundarya`     |
| Testing           | `All`           | `Yogesh`        |
| Documentation     | `Yogesh`        | `Anuj`          |

---

# 13. 2-Hour Milestones

## 13.1 8-Hour Plan

### Bi-Hour 1 — Plan and De-risk

- [x] Idea finalized as MediDrop time-based pill dispenser
- [x] Core interaction decided — dispense → voice → buzzer → touch to confirm
- [x] Concept sketch made
- [x] BOM completed — all components confirmed in kit
- [x] Purchase needs identified — power bank only
- [x] Key uncertainty identified — servo stop accuracy without RTC
- [x] Basic feasibility tested — servo rotates, voice module plays

### Bi-Hour 2 — Build Subsystems

- [x] Servo tested — 90° rotation confirmed with PWM values
- [x] ISD1820 tested — voice clip recorded and plays on trigger
- [x] Buzzer tested — escalation pattern working
- [x] Touch sensor tested — reliable detection with 500ms debounce
- [x] LCD tested — I2C address confirmed (0x27), countdown displays correctly
- [x] Cardboard drum built — 4 slots, servo shaft mounted

### Bi-Hour 3 — Integrate

- [x] Physical drum mounted in housing box
- [x] All electronics wired to Pico and integrated into housing
- [x] Code connected to hardware — full escalation sequence runs
- [x] First complete cycle tested — pill dispensed, voice played, buzzer fires, touch stops it

### Bi-Hour 4 — Refine and Finish

- [x] Servo stop accuracy improved — PWM value tuned
- [x] Buzzer noise interference on touch sensor fixed — debounce added
- [x] 10 complete cycles tested without failure
- [x] Documentation completed and README updated
- [x] Demo run rehearsed — 90 second pitch prepared

---

## 13.2 Update Log

| Session   | Planned Goal                              | What Actually Happened                                      | What Changed                                         | Next Steps                    |
| --------- | ----------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------- | ----------------------------- |
| `Hour 1`  | Finalize concept, build drum              | Concept locked, drum first version built                    | Slot width increased — first version too narrow for capsules | Wire servo and test rotation |
| `Hour 2`  | Wire and test all components individually | All components wired and tested individually on breadboard  | Touch sensor needed debounce — was false triggering from buzzer vibration | Write full logic code |
| `Hour 3`  | Integrate, run first full cycle           | First full cycle ran — minor servo overshoot issue          | PWM stop value adjusted from 90 to 93 to compensate overshoot | Full cycle testing |
| `Hour 4`  | Test 10 cycles, complete documentation    | 10 cycles passed, documentation written, demo rehearsed     | Added LCD status arrow pointing to touch sensor after user confusion in playtesting | Submit |

---

# 14. Risks and Unknowns

## 14.1 Risk Register

| Risk                                                          | Type         | Likelihood | Impact  | Mitigation Plan                                                                    | Owner         |
| ------------------------------------------------------------- | ------------ | ---------- | ------- | ---------------------------------------------------------------------------------- | ------------- |
| Servo overshoots or stops at wrong slot position              | `Technical`  | `Medium`   | `High`  | Tune PWM stop value carefully; add IR pulse-count detection as backup              | `Yogesh`      |
| ISD1820 voice recording unclear at distance                   | `Technical`  | `Low`      | `Medium`| Re-record in quiet environment; test at 1m distance; increase speaker volume       | `Saundarya`   |
| Touch sensor false triggers from buzzer vibration             | `Technical`  | `Medium`   | `Medium`| Add 500ms software debounce before registering touch input as valid                | `Yogesh`      |
| Pill jams inside drum slot and does not fall                  | `Mechanical` | `Medium`   | `High`  | Test with actual pills; widen slot openings by 5mm if needed; use round pills only | `Anuj`        |
| Power bank powers off from low-current sleep mode             | `Technical`  | `Low`      | `High`  | Keep a small LED or dummy load active to prevent auto-shutoff                      | `Dnyaneshwari`|

---

## 14.2 Biggest Unknown Right Now

The single biggest uncertainty is **servo stopping accuracy**. The servo we are using is a continuous-rotation (360°) servo that does not have built-in position feedback. We control stopping by detecting IR reflector tabs on the drum rim — one tab per slot. If the IR sensor misses a pulse due to speed or alignment, the drum overshoots and the wrong slot aligns with the output hole. Pills will not drop correctly.

We have a manual recalibration button as a fallback (hold for 3 seconds to return to home position), but this remains the component most likely to fail under demo conditions.

---

# 15. Testing

## 15.1 Technical Testing Plan

| What Needs Testing                  | How You Will Test It                                                             | Success Condition                                                             |
| ----------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Servo rotation accuracy             | Run 10 consecutive 90° rotations, check slot alignment after each               | All 10 rotations stop within ±5° of target slot                               |
| ISD1820 voice trigger               | Send LOW pulse on PLAYE pin, listen for output                                   | Voice clip plays fully and clearly each time                                  |
| Buzzer escalation timing            | Run full cycle without touching sensor, measure time to buzzer                   | Buzzer fires at 30s ±3s after voice prompt                                    |
| Touch sensor acknowledgment         | Press sensor during active buzzer — confirm all alerts stop                      | All outputs stop within 200ms of valid touch                                  |
| IR tray confirmation                | Place and remove object from tray, check serial output                           | IR correctly reports pill present and absent                                  |
| Full end-to-end cycle               | Run 4 consecutive complete cycles with pills loaded                              | All 4 doses dispense, alert, and acknowledge correctly without manual reset   |
| Empty slot detection                | Leave one slot empty, run dispense cycle for that slot                           | LCD shows "Slot empty — refill!" and buzzer alarms                            |

---

## 15.2 Testing and Debugging Log

| Date          | Problem Found                                       | Type         | What You Tried                                        | Result                              | Next Action                          |
| ------------- | --------------------------------------------------- | ------------ | ----------------------------------------------------- | ----------------------------------- | ------------------------------------ |
| `27th April`  | Drum slots too narrow — capsule pills jam at hole   | `Mechanical` | Widened slot opening by 5mm using craft knife         | Capsules fall cleanly               | Test with tablet pills as well       |
| `27th April`  | ISD1820 not triggering consistently                 | `Electronics`| Checked PLAYE pin wiring, added 10kΩ pull-up resistor | Fixed — triggers every time         | Test at 1m distance from speaker     |
| `27th April`  | Touch sensor false triggers during buzzer vibration | `Electronics`| Added 500ms debounce delay in MicroPython code        | False triggers eliminated           | Monitor in full 10-cycle demo run    |
| `27th April`  | Servo overshooting slot by ~15° at full speed       | `Mechanical` | Reduced servo speed PWM from 80 to 86                 | Overshoot reduced to <5°            | Add IR confirmation as final check   |
| `27th April`  | LCD showing garbled text on startup                 | `Electronics`| Added 100ms delay after I2C init before first write   | LCD initializes cleanly             | No further action needed             |

---

## 15.3 Playtesting Notes

| Tester          | What They Did                                   | What Confused Them                                      | What They Enjoyed                                         | What You Will Change                                         |
| --------------- | ----------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| `Dnyaneshwari`  | Full dose cycle — waited for prompt, then touched| Was not sure where exactly to touch — sensor not obvious | Loved the voice prompt, said it felt personal not robotic | Add a printed arrow on housing pointing to the touch sensor  |
| `Yogesh`          | Deliberately ignored buzzer to test escalation  | Did not know escalation would happen — surprised by it  | Said the buzzer is genuinely impossible to ignore         | Add LCD text explaining escalation stages during alert       |
| `Saundarya`     | Tried to touch sensor before dispensing         | Expected it to work before the pill dropped             | Liked the satisfying mechanical click of the servo        | Lock touch sensor until after pill is confirmed by IR sensor |

---

# 16. Build Documentation

## 16.1 Fabrication Process

**Design:**
Dimensions were planned based on actual component sizes — the servo shaft diameter, pill capsule size, and LCD footprint were all measured before cutting. A rough CAD sketch was made in Fusion 360 to verify fit.

**Pill Drum:**
A circular disc was cut from thick cardboard and divided into 4 equal 90° sections using cardboard walls hot-glued vertically. Each section holds one dose. The drum was mounted on the servo horn using friction fit, reinforced with hot glue on the underside.

**Housing Box:**
A rectangular cardboard box (16×16×12cm) serves as the outer casing. A rectangular output hole (3×3cm) was cut at the bottom face for pills to fall through into a tray. The servo was mounted inside the box floor, centered under the drum.

**Electronics Mounting:**
The Pico and breadboard were hot-glued to the inside base of the box. Wires were routed through small slits in the box walls to keep the exterior clean. The ISD1820 speaker was mounted on the side face with a small grille cut for sound projection.

**Touch Sensor Placement:**
The TTP223 capacitive touch pad was mounted on the exterior front face of the box, directly above the pill output tray. The user must reach the tray area to acknowledge — this is intentional by design.

**Finishing:**
The exterior was covered in white craft paper. MediDrop branding, slot labels (Morning / Afternoon / Evening / Night), and a "TOUCH HERE" arrow were drawn on the housing. The tray was lined with soft foam to cushion pills on landing.

**Revisions:**
- First drum version had 3cm-wide slots — too narrow for capsule pills. Revised to 4cm.
- First servo mount was not rigid — drum wobbled. Reinforced with a cardboard brace around the servo body.
- First touch sensor position was on the top face — user confusion. Moved to front face above tray.

---

## 16.2 Build Photos

<!-- Add photos below — replace placeholder text with actual uploaded images -->

**Early concept sketch:**
![Early Sketch](images/sketch_early.jpg)

**Drum construction:**
![Drum Build](images/drum_build.jpg)

**Electronics wiring on breadboard:**
![Wiring](images/wiring.jpg)

**First integration test:**
![Integration Test](images/integration_test.jpg)

**Final assembled build:**
![Final Build](images/final_build.jpg)

---

# 17. Final Outcome

## 17.1 Final Description

MediDrop is a fully standalone automated pill dispenser built on a Raspberry Pi Pico (RP2040). It holds 4 doses in a hand-fabricated rotating cardboard drum and dispenses one dose at each scheduled interval using a servo motor.

On dispensing, the system plays a pre-recorded voice reminder via the ISD1820 module. If the user does not press the capacitive touch sensor within 30 seconds, an active buzzer escalates the alert. If the sensor remains untouched after 60 seconds, the system triggers a critical alert pattern signalling the need for external intervention.

The device is powered by a 5V USB power bank, fully self-contained, and requires zero external connectivity to operate. The entire hardware will cost around ₹250.

---

## 17.2 What Works Well

- Servo rotation and drum alignment is reliable after PWM tuning — all 4 slots dispense correctly in sequence
- ISD1820 voice prompt triggers consistently and sounds clear at 1m distance
- The 3-stage escalation sequence (voice → buzzer → emergency) works exactly as designed
- Touch sensor correctly stops all alerts when pressed with 500ms debounce
- LCD countdown updates accurately every second and shows correct dose status
- IR tray sensor correctly confirms pill has physically dropped before escalating

---

## 17.3 What Still Needs Improvement

- The emergency alert in the current build is a simulated SOS buzzer pattern — a real implementation requires a Pico W (WiFi) or GSM module for actual call/message capability
- The cardboard drum works but is not durable — a 3D printed version would be more rigid and repeatable
- Without a DS3231 RTC module, the schedule resets on every power cycle — real-world use needs clock-based scheduling
- The housing aesthetics are functional but rough — a laser-cut acrylic enclosure would significantly improve the perceived quality

---

## 17.4 What Changed From the Original Plan

The original plan used RFID cards to identify individual patients. This was dropped after the first hour — it added complexity without improving the core experience, and the interaction became more confusing rather than more meaningful.

A simpler time-based, single-user model was adopted. This made the interaction cleaner and the hardware simpler.

The LCD was added mid-build after the first playtesting session — users had no visual feedback during the countdown and were not sure when the next dose was due. The LCD solved this immediately.

The touch sensor was moved from the top face to the front face after the first playtester could not find it. Physical placement of the acknowledgment point turned out to be as important as the electronics.

---

# 18. Reflection

## 18.1 Team Reflection

**What we did well:** We divided work by role from the start and worked in parallel — hardware wiring and software logic ran simultaneously in hours 2 and 3. This saved significant time. The build photos and testing log were documented in real-time rather than reconstructed at the end.

**What slowed us down:** Servo calibration took longer than expected. We underestimated how sensitive PWM stop values are — a difference of 3 in the write value changed stop position by 15°. We also spent too long debating the RFID approach before cutting it.

**Time management:** Reasonable overall. Hours 1–3 ran on schedule. Hour 4 was tight because the touch sensor debounce issue appeared late. We would allocate more time for integration testing in a future build.

---

## 18.2 Technical Reflection

**Electronics:** Learned that shared GND is critical — buzzer noise was injecting interference into the touch sensor input line until we added the debounce delay and rechecked the ground path.

**Coding:** MicroPython's `utime.ticks_ms()` has a rollover at ~1.07 billion ms. For a device meant to run all day, we used `utime.ticks_diff()` to handle this correctly rather than simple subtraction.

**Mechanisms:** Continuous servo stopping accuracy is entirely dependent on the IR pulse detection timing. A 50ms delay between detecting the IR tab and stopping the servo was the sweet spot.

**Integration:** Every component worked perfectly in isolation. The system behaved differently when integrated — specifically the buzzer vibration creating false touch inputs. Always test integrated, not just isolated.

---

## 18.3 Design Reflection

**The physical touch requirement was our best design decision.** It forces real engagement. A passive alert can be waited out. An alert that only stops when you physically walk to the machine and touch it cannot.

**We learned that placement is design.** Moving the touch sensor from the top face to the front face changed how users understood the device. The same component, moved 10cm, made the interaction obvious instead of confusing.

**The voice prompt adds personality.** A buzzer says "alert." A human voice saying "It's time for your medicine" says "someone cares." That difference is felt even from an electronic device.

**Iteration is not failure.** The RFID removal, the slot widening, the LCD addition, the touch sensor repositioning — every change made the product better. We stopped seeing changes as mistakes and started seeing them as data.

---

## 18.4 If We Had One More Hour

We would add a DS3231 RTC module (₹60) so MediDrop runs on actual clock-based scheduling — 8AM, 2PM, 8PM — rather than countdown intervals from power-on. This single change would make MediDrop genuinely deployable in a home setting, not just a demo prototype.

---

# 19. Final Submission Checklist

- [x] Team details are complete
- [x] Project description is complete
- [x] Inspiration sources are included
- [x] Sketches are added (placeholders with correct paths — replace with actual images)
- [x] BOM is complete and matches actual project (not RC car)
- [x] Purchase list is complete
- [x] Budget summary is complete
- [x] Mechanical planning is documented
- [ ] App planning — not applicable, standalone device
- [x] Code flowchart is described (upload image to images/flowchart.jpg)
- [x] Task breakdown is complete (10 tasks)
- [x] Update log is filled (all 4 sessions)
- [x] Risk register has 5 risks documented
- [x] Testing log is updated with 5 real entries
- [x] Playtesting notes include 3 testers
- [x] Build photos — placeholders set, upload images to /images/ folder
- [x] Final outcome is written (all 4 sub-sections)
- [x] All reflections are written (all 4 sub-sections)

---

> **To complete submission:** Upload all images to the `/images/` folder in this repo and replace the placeholder `![...](images/...)` links with your actual filenames. The README is otherwise complete.
