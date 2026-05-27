# toki-run
toki-run: A lightweight background daemon for AI to scheduling and executing orchestrated bash routines within precise time windows.

The name comes from the native Japanese word **Toki (時)**, meaning "time," "occasion," or the "right moment"—reflecting the tool's strict adherence to scheduled execution windows.

## 🚀 How It Works

`toki-run` operates quietly in the background as a system daemon, waiting for the exact alignment of your routine's schedule:

1. **Schedule:** A client CLI (like *Anti-Gravity*) registers an action—consisting of a series of bash commands and a strict execution window.
2. **Idle/Wait:** `toki-run` manages the queue in the background, sleeping until the time window opens.
3. **Execute:** Once the window is hit, `toki-run` triggers the bash sequence directly on the host machine.
4. **Finalize:** Upon completion, the tool immediately updates state memory to acknowledge and finalize that the action was successfully executed.

## 🛠️ Features

* **Decoupled Architecture:** Built to sit seamlessly behind external clients.
* **Deterministic Execution:** Strict time-window guarding ensures scripts never run outside of their allowed boundaries.
* **State Persistence:** Instant memory updates upon task finalization to prevent double-execution or lost states.
* **Native Bash Integration:** Runs native shell sequences without complex wrapper overhead.
