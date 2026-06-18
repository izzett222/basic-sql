# MISSION BRIEFING: THE AURELIA PRIME INCIDENT

**CLASSIFICATION:** RESTRICTED EYE ONLY  
**TO:** Chief Investigator  
**FROM:** Port Security Command  
**SYSTEM DATE:** March 13, 2084  
**SUBJECT:** Disappearance of Dr. Evelyn Vance  

---

### THE SITUATION
At 06:00 AM this morning, **Dr. Evelyn Vance**, the station's Chief Xenobiologist, failed to report for her shift in the Bio-Dome. Corporate executives from Aurelia Corp are claiming she was simply reassigned, but her quarters are cleared out, and her primary research files have been heavily modified. 

We suspect corporate foul play or an unsanctioned escape. Unfortunately, Aurelia Corp has locked down the station's primary AI and security consoles. They are trying to sweep her disappearance under the rug.

### YOUR OBJECTIVE
You have successfully established a raw, backdoor SQL connection to Aurelia Prime’s core station database. **You must trace Dr. Vance's footsteps, identify who helped her, and locate her current coordinates before corporate security sweeps the database.**

### HOW THE INVESTIGATION WORKS (THE RULES)
This is not a typical exam. To solve this case, you must act like a real detective:
1. **The Database is Your Witness:** Every query you run will return data. **Read the text fields carefully.** The logs, transcripts, diaries, and flight notes contain the narrative "coordinates" and clues you need to write your next query.
2. **The Chain of Clues:** You cannot skip ahead. The output of Step 1 will give you the specific IDs, dates, or search terms required to build the query for Step 2, and so on.
3. **Beware of Corporate Traps:** The database is massive, containing thousands of daily logs, system alerts, and routine maintenance entries. Corporate security has also planted several "red herrings" (fake clues, previous cases, and other employees with similar names or patterns). Only precise, structurally perfect SQL queries will bypass the noise and extract the truth.

---

### THE DATABASE SCHEMA & DATA DICTIONARY

To construct effective queries, you must understand what files you are looking at. Below is the documentation of the station's tables, what they record, and how to link them together.

#### 1. `crew`

_This is the master directory of every individual living and working on Aurelia Prime._

- **`crew_id` (Primary Key):** The unique identification number assigned to each employee.
- **`name`:** The employee's full name.
- **`role`:** Job title (e.g., 'Rookie Officer', 'Chief Xenobiologist').
- **`department`:** Sector assignment (e.g., 'Security', 'Engineering', 'Xenobiology').
- **`manager_id` (Foreign Key):** The `crew_id` of this employee's direct supervisor.
    - _Detective Note:_ If an employee is an independent contractor or freelancer, they do not report to anyone. Their `manager_id` will be **`NULL`**. Standard comparison operators like `=` or `!=` do not work on `NULL`—you must use special handlers.
- **`salary`:** Monthly salary in station credits.

#### 2. `investigator_dashboard`

_Your personal station console. It houses emergency alerts and active files assigned to your unit._

- **`case_id` (Primary Key):** Incident tracking number.
- **`title`:** Brief summary of the emergency.
- **`assigned_to`:** The investigator or deputy handling the case.
- **`status`:** Current state of the file ('Active', 'Resolved', 'Closed', 'Pending').
- **`urgency`:** Severity score rated from 1 (minor glitch) to 5 (critical emergency).
- **`content`:** Detailed case file text, containing coordinates, intel updates, and next-step instructions.
- **`created_at`:** Timestamp of when the report was filed.

#### 3. `police_reports`

_Official incident logs and transcripts filed by security patrol staff._

- **`report_id` (Primary Key):** File log index.
- **`officer_id` (Foreign Key):** The `crew_id` of the security officer who wrote the report (links to `crew.crew_id`).
- **`subject`:** Short title of the incident (e.g., 'Vandalism', 'Lost Keycard').
- **`transcript`:** Full written record of the incident, including witness testimonies and statements.
- **`created_at`:** Date and time the report was submitted.

#### 4. `personal_diaries`

_Encrypted journal entries recovered from personal datapads left in crew quarters._

- **`diary_id` (Primary Key):** Journal index.
- **`owner_id` (Foreign Key):** The `crew_id` of the diary's owner (links to `crew.crew_id`).
- **`password_hint`:** The security question set by the owner.
- **`entry_text`:** The actual diary entry containing private thoughts, plans, and secrets.

#### 5. `comms_network`

_A log of intercepted radio and text transmissions between personnel terminals._

- **`msg_id` (Primary Key):** Data packet index.
- **`sender_id` (Foreign Key):** The `crew_id` of the sender.
- **`receiver_id` (Foreign Key):** The `crew_id` of the recipient.
- **`message`:** The decrypted text of the conversation.
- **`sent_at`:** Date of transmission.

#### 6. `station_doors`

_The directory mapping out every locked door, gate, airlock, and ventilation hatch on the station._

- **`door_id` (Primary Key):** The code of the physical door (e.g., 'D-909').
- **`sector_name`:** The station sector where the door resides (e.g., 'Sector 9', 'Sub-Level 4C').
- **`description`:** Blueprints, room layout notes, and security access instructions.

#### 7. `door_access_logs`

_Every time a person swipes their card at a door, the physical console writes a log here._

- **`access_id` (Primary Key):** Unique transaction index.
- **`crew_id` (Foreign Key):** The `crew_id` of the cardholder (links to `crew.crew_id`).
- **`door_id` (Foreign Key):** The door being swiped (links to `station_doors.door_id`).
- **`access_time`:** Timestamp of card reader read.
- **`status`:** 'Success' if passed, 'Denied' if rejected, or **`NULL`** indicating a hardware failure, power loss, or a physical wire cut.

#### 8. `shuttles`

_The hangar directory tracking all registered flight vehicles currently docked or assigned to the station._

- **`shuttle_id` (Primary Key):** Vessel code.
- **`name`:** The name of the shuttle (e.g., 'The Wanderer').
- **`last_docking_bay`:** Hangar bay where the ship is parked (e.g., 'Bay 3').
- **`flight_notes`:** Post-flight landing remarks, terminal commands, or emergency pilot logs.

#### 9. `shuttle_manifest`

_Boarding logs registering everyone who boarded a specific shuttle before launch._

- **`manifest_id` (Primary Key):** Boarding log number.
- **`shuttle_id` (Foreign Key):** The vehicle being boarded (links to `shuttles.shuttle_id`).
- **`passenger_id` (Foreign Key):** The employee boarding (links to `crew.crew_id`).
    - _Detective Note:_ If a passenger boards using a forged, unregistered, or erased credential to bypass terminal security, their `passenger_id` will be logged as **`NULL`**.
- **`board_time`:** Timestamp of passenger registration.

#### 10. `environmental_telemetry`

_Real-time sensor logs reporting life support conditions across the station's grid._

- **`telemetry_id` (Primary Key):** Sensor sweep index.
- **`area_name`:** The sector name being measured (corresponds to `station_doors.sector_name`).
- **`oxygen_level`:** Atmospheric oxygen percentage (0% represents vacuum, normal is 21%).
- **`temperature`:** Room temperature measured in Celsius.
- **`scanned_at`:** Timestamp of sensor reading.
### YOUR DATABASE SCHEMA
Use this blueprint to construct your SQL queries.

```text
               +-----------------------+
               |         CREW          |
               +-----------------------+
               | crew_id (PK)          |
               | name                  |
               | role                  |
               | department            |
               | manager_id            | <----+ (Reports to another crew_id)
               | salary                |
               +-----------------------+
                           |
         +-----------------+-----------------+
         |                 |                 |
+-----------------+ +--------------+ +-----------------+
|  DIARIES        | | COMMS        | | POLICE REPORTS  |
+-----------------+ +--------------+ +-----------------+
| diary_id (PK)   | | msg_id (PK)  | | report_id (PK)  |
| owner_id (FK)   | | sender_id    | | officer_id (FK) |
| password_hint   | | receiver_id  | | subject         |
| entry_text      | | message      | | transcript      |
+-----------------+ | sent_at      | +-----------------+
                    +--------------+
                           |
               +-----------------------+
               |   DOOR ACCESS LOGS    |
               +-----------------------+
               | access_id (PK)        |
               | crew_id (FK)          |
               | door_id (FK) ---------+------+
               | access_time           |      |
               | status ('Success'/    |      |
               |         'Denied'/NULL)|      |
               +-----------------------+      |
                                              v
                                   +-----------------------+
                                   |     STATION DOORS     |
                                   +-----------------------+
                                   | door_id (PK)          |
                                   | sector_name           |
                                   | description           |
                                   +-----------------------+
                                              |
                                              v (Exists correlation)
                                   +-----------------------+
                                   |  ENV TELEMETRY        |
                                   +-----------------------+
                                   | telemetry_id (PK)     |
                                   | area_name             |
                                   | oxygen_level          |
                                   | temperature           |
                                   | scanned_at            |
                                   +-----------------------+

               +-----------------------+
               |       SHUTTLES        |
               +-----------------------+
               | shuttle_id (PK)       |
               | name                  |
               | last_docking_bay      |
               | flight_notes          |
               +-----------------------+
                           |
                           v
               +-----------------------+
               |   SHUTTLE MANIFEST    |
               +-----------------------+
               | manifest_id (PK)      |
               | shuttle_id (FK)       |
               | passenger_id (FK)     | (NULL = unregistered)
               | board_time            |
               +-----------------------+
```

---

### FIRST STEP: THE COLD START
To begin your investigation, check your active case assignments. 

**Write a SQL query against the `investigator_dashboard` table to find the latest, most urgent `Active` case assigned to you (the 'Chief Investigator').** 

*Tip: Sort the cases so that the newest and most urgent cases appear first, and limit your result to exactly 1 row to block out the console noise.*

**Good luck, Investigator. The clock is ticking.**
