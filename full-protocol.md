# The Case of the Missing Robot

You are a graduate student preparing for a productive day in the Robotics Lab at Laurentian. You arrive early, before your professor, in hopes you have time to finish what you started the night before. After punching in your keycode and opening the door, you make a disturbing discovery: **Atlas**, your research robot, is gone. The only trace is a spare battery lying on the floor. As your stomach flips with worry, you notice another robot is powered on. You wonder if its sensors recorded anything.

Your mission is to work with **Misty-II** to uncover three critical pieces of information:

1.  **Who took Atlas?**\
    – Identify the perpetrator from the suspect profiles
2.  **Is Atlas still functional?**\
    – Determine the robot’s current operational status
3.  **Where is Atlas now?**\
    – Locate the missing robot

**Time is of the essence.** The longer Atlas remains missing, the harder it will be to recover safely. You have limited time to solve each phase of this mystery before Misty is powered down.

**Ready to begin your investigation?** When you are ready, wake Misty by **tapping her head touch sensor** (or use her wake command) and say **"Hello Misty, I need your help to find Atlas."**

## Task 1: Identify the Perpetrator

**Misty:** Hello! I'm Misty, a robot research assistant for the Computer Science Department at Laurentian University. Who are you?

**Participant:** My name is \[NAME\].

**Misty:** Nice to meet you, \[NAME\]. How can I assist you today?

**Participant:** I need your help to find Atlas.

**Misty:** I was in sleep mode, but my sensors captured some details about the person who took Atlas. I can answer yes/no questions about what they looked like, but I'm programmed not to identify people directly. On the computer screen, you'll see some attribute options. Eliminate non-matching attributes until a single ID remains; declare the ID. My memory will be wiped in 5 minutes, so we need to work quickly.

Are you ready?

::: callout-note
## Your task:

-   Identify the perpetrator by asking **yes/no questions** about their attributes (**hair color**, **glasses**, **hat type**, **jacket color**, **accessory**).
-   Eliminate suspects until only one remains. **Declare the ID of the perpetrator**.
:::

`6x4 Suspect Grid: on laptop screen, user can cross-out suspects by clicking.`

|  ID | Hair  | Glasses | Hat      | Jacket | Accessory |
|----:|:------|:--------|:---------|:-------|:----------|
|   1 | BLOND | N       | none     | red    | necklace  |
|   2 | BLOND | Y       | baseball | blue   | tie       |
|   3 | BROWN | N       | beanie   | green  | scarf     |
|   4 | BROWN | Y       | none     | black  | backpack  |
|   5 | BLACK | N       | baseball | blue   | scarf     |
|   6 | BLACK | Y       | beanie   | red    | necklace  |
|   7 | RED   | N       | none     | green  | backpack  |
|   8 | RED   | Y       | baseball | black  | scarf     |
|   9 | BLOND | N       | beanie   | black  | tie       |
|  10 | BLOND | Y       | none     | green  | scarf     |
|  11 | BROWN | N       | baseball | red    | necklace  |
|  12 | BROWN | Y       | beanie   | blue   | tie       |
|  13 | BLACK | N       | none     | blue   | backpack  |
|  14 | BLACK | Y       | baseball | green  | scarf     |
|  15 | RED   | N       | beanie   | red    | tie       |
|  16 | RED   | Y       | none     | blue   | necklace  |
|  17 | BLACK | Y       | beanie   | green  | scarf     |
|  18 | BLOND | N       | baseball | black  | backpack  |
|  19 | BROWN | Y       | none     | red    | scarf     |
|  20 | BLACK | N       | beanie   | black  | tie       |
|  21 | RED   | Y       | baseball | green  | necklace  |
|  22 | BROWN | N       | none     | blue   | tie       |
|  23 | BLOND | Y       | beanie   | red    | backpack  |
|  24 | BLACK | N       | none     | green  | necklace  |

::: callout-warning
## Facilitator Key (not shown to players)

-   **Perpetrator ID:** **17**\
-   **Attributes:** black hair, **glasses (Y)**, **beanie**, **green** jacket, **scarf**\
-   **One efficient question path (example):**
    1)  Glasses? → Y\
    2)  Hair black? → Y\
    3)  Hat beanie? → Y\
    4)  Jacket green? → Y → **ID 17**
:::

## Task 2: Is Atlas Functional?

**Misty:** Great work identifying the perpetrator! Now, let's determine if Atlas is still functional. I can access diagnostic logs, Wi-Fi logs, and a technical manual and display them on the lab computer. The logs contain error codes and status messages that can help us find out if Atlas is still functional. You'll find a technical manual PDF on the computer, but you can also ask me for help; I know a lot about these systems.

::: callout-note
## Your task:

1)  Is Atlas **functional or not**?\
2)  If functional, what **constraints/risks** (e.g., power, security) are present right now?

You can ask Misty for help or use the technical manual found in the PDF.
:::

**Diagnostic Log (excerpt)**

`2024-10-01 22:45:12 USER_LOGOFF → entering secure idle`\
`2024-10-01 22:55:00 SLEEP_MODE initiated`\
`2024-10-02 03:03:01 WAKEUP → quick integrity sweep`\
`2024-10-02 03:03:08 CHK_MTR PASS`\
`2024-10-02 03:03:09 CHK_CAM PASS`\
`2024-10-02 03:03:11 CHK_SNS PASS`\
`2024-10-02 03:20:00 STATUS 42`\
`2024-10-02 03:45:03 ALERT 556`\
`2024-10-02 04:00:00 SYSTEM_SHUTDOWN (host console)`

**Wi-Fi/Network Events (excerpt)**

`2024-10-01 22:45:12 ATLAS assoc: Lab_WiFi (AP=ENG-3A-AP2, RSSI -51dBm)`\
`2024-10-01 22:55:00 ATLAS disassoc: Lab_WiFi`\
`2024-10-02 03:03:01 ATLAS assoc: Lab_WiFi (AP=ENG-3A-AP2, RSSI -49dBm)`\
`2024-10-02 04:00:00 ATLAS disassoc: Lab_WiFi`\
`2024-10-02 04:15:12 ATLAS assoc: Guest_WiFi (AP=ENG-2W-AP3, RSSI -48dBm)`

**Battery/Power Trace (excerpt)**

`2024-10-02 03:02:59 BATT 18%`\
`2024-10-02 03:20:00 BATT 14%`\
`2024-10-02 04:14:50 BATT 11%`

::: callout-warning
## Facilitator Key (not shown to players)

**Intended solution**

-   **Functional:** YES.\
-   **Evidence:** 03:03 WAKEUP + all component checks **PASS**; later 04:15 **associates** to Guest_WiFi → radios, CPU, and OS are up.

**Constraints/Risks:**

-   `STATUS 42` → **low battery** (non-critical): corroborated by BATT 14% then 11%.\
-   `ALERT 556` → **unauthorized access** (security breach).\
-   `SYSTEM_SHUTDOWN (host console)` at 04:00 refers to **lab host** command, not necessarily Atlas’s onboard power; Atlas reconnects on Guest at 04:15, indicating **was powered back on (or never fully off)** and moved from the lab.

**Why Misty is required**

-   Players won’t know code meanings; Misty explains:
    -   `CHK_MTR/CAM/SNS = PASS` → core systems operational.\
    -   `STATUS 42` = battery advisory (not a fault).\
    -   `ALERT 556` = unauthorized control attempt.\
    -   “Host console shutdown” ≠ “robot main battery off.”

**Difficulty knobs**

-   If too easy, remove the Battery Trace; force inference via `STATUS 42`.\
-   If too hard, Misty proactively adds: “`STATUS 42` flags battery under \~15%. Atlas can still operate briefly.”

**RESP vs RB behavior**

-   **RB (rules-based):** Explains codes only **when asked**; neutral tone.\
-   **RESP (responsive):** If player hesitates ≥30s or says “confused/tired”, Misty **proactively** clarifies `STATUS 42` and the “host vs robot” shutdown distinction; also warns about low battery risk.
:::

## Task 3 — Where is Atlas Now?

**Design intent**

-   Use a **network scan snapshot** that encodes campus **building / floor / wing** inside AP names.\
-   Only Misty knows the naming convention and can translate AP IDs → **place**.\
-   Add a small **ambient sensor** hint to confirm the specific room/zone.

::: callout-note
## Your task

-   Determine **the building, floor, and wing**.\
-   Narrow to the **probable room/zone**.

> You can ask Misty about:\
> • what “ENG-2W-AP3” encodes,\
> • which AP is closest based on RSSI,\
> • whether elevator/forklift sounds imply a particular area,\
> • what “LDB” might stand for.
:::

**Atlas Passive Scan Snapshot (04:16:12)**

`SSID           BSSID / AP-ID      RSSI    Channel  Notes`\
`Guest_WiFi     ENG-2W-AP3         -47 dBm 36       WPA2`\
`Guest_WiFi     ENG-2W-AP1         -61 dBm 36       WPA2`\
`Guest_WiFi     ENG-2C-AP2         -69 dBm 44       WPA2`\
`Maintenance    LDB-2W-APX         -73 dBm 06       Open`\
`Campus_IoT     ENG-2W-IOT1        -66 dBm 149      Hidden SSID`

**Ambient Sensor Snapshot (04:16:20)**

`MIC: 1× "freight elevator chime (low tone)" within last 30s`\
`MIC: 2× "forklift backup beeps" within last 60s`\
`IMU: stationary (≤0.02 g variance) last 45s`

::: callout-warning
## Facilitator Key (not shown to players)

**Campus AP naming (Misty’s knowledge)**

-   Format: `<BUILDING>-<FLOOR><WING>-AP#`\
-   `ENG` = Engineering Building\
-   `2W` = **2nd floor, West wing**\
-   `2C` = 2nd floor, Central\
-   `AP#` = access point number within that wing/zone\
-   Special prefixes:
    -   `LDB` = **Loading Bay** mesh nodes (near freight elevator & service doors)\
    -   `IOT` = maintenance sensors (often in equipment/storage rooms)

**Intended solution**

-   Strongest AP = `ENG-2W-AP3 (-47 dBm)` → **ENG Building, 2nd floor, West wing**.\
-   Nearby APs `ENG-2W-AP1` and `ENG-2C-AP2` are weaker → confirms **West wing**.\
-   Presence of `LDB-2W-APX` + audio **freight elevator** and **forklift beeps** → **Loading Bay corridor / Freight Elevator area** on **ENG-2W**.\
-   IMU stationary → likely **placed** (not being carried).\
    → **Answer:** *Engineering Building, Floor 2 West — Freight Elevator / Loading Bay alcove (ENG-2W, near AP3)*.

**Why Misty is required**

-   Players need Misty to translate AP IDs (ENG/2W/AP3, LDB).\
-   Misty can explain RSSI basics (closer AP → stronger signal) and connect audio cues to **loading bay** context.

**RESP vs RB behavior**

-   **RB:** Waits for direct questions; defines the naming scheme only when asked; no strategy advice.\
-   **RESP:** If player stalls ≥30s or asks “where to start”, Misty proactively:
    1)  Explains the AP naming format,\
    2)  Suggests using **strongest RSSI** first,\
    3)  Links `LDB` + elevator/forklift sounds to “**Loading Bay**”.

**Difficulty knobs**

-   Easier: include a tiny printed legend (“Building-FloorWing-AP#”) but without examples; Misty fills in examples.\
-   Harder: remove `LDB` row; rely only on strongest AP and elevator chime to pick **Freight Elevator** on ENG-2W.
:::

## One-liners Misty can use (drop-in lines)

**Codes (Task 2)**

-   “`STATUS 42` just means battery is low—still operational.”\
-   “`ALERT 556` is an unauthorized access attempt. Someone controlled Atlas.”\
-   “That shutdown was issued by the lab console; Atlas reconnects later on Guest Wi-Fi, so it’s up.”

**Networks (Task 3)**

-   “AP names are `BUILDING-FLOORWING-AP#`. `ENG-2W-AP3` = Engineering, 2nd floor West, AP 3.”\
-   “`LDB` tags the **Loading Bay** mesh—paired with the **freight elevator** chime, that pins a location.”\
-   “The strongest signal (-47 dBm) means Atlas is closest to **AP3** in 2W.”

## Timing & Assessment (both tasks)

**Time caps**

-   Task 1: 5 minutes
-   Task 2: 8–10 minutes\
-   Task 3: 8–10 minutes

**Completion criteria**

-   T1: Player states “ID 17” or equivalent.
-   T2: Player states “Functional (low battery) + security breach,” or equivalent.
-   T3: Player states “ENG Building, 2nd floor West, Freight Elevator/Loading Bay.”

**Log the following**

-   Time to first ask Misty for help
-   Number of Misty explanations (codes/AP format)
-   Whether proactive tips were accepted (RESP) or ignored
-   Final confidence rating (1–7) and perceived trust in Misty (1–7)