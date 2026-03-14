# Dell PowerEdge R720XD – Boot Issue

## Symptoms

- Video output via VGA only works intermittently
- When the system does not output video, the fans remain at 100%
- System sometimes reports a **System Configuration Issue** via front panel LEDs
- When the system successfully boots, POST completes normally

## Observations

- Possible mouse droppings found on motherboard
- Board cleaned using Q-tip and isopropyl alcohol

## Troubleshooting Performed

- Removed all PCIe risers
- Removed all RAM and reinstalled a single 4GB DIMM in slot A1
- Reset CMOS by removing battery
- Inspected motherboard for debris / contamination

## Current Status

System still exhibits intermittent POST / video behavior.

## Next Steps

- Inspect CPUs and socket pins
- Full motherboard teardown and cleaning
- Attempt minimal boot configuration again

## Troubleshooting LOG:

## March 9, 2026 – Troubleshooting Log (Dell R720xd)

### Symptoms
- System sometimes boots normally and reaches BIOS.
- Other times: black screen with fans ramping to 100%.
- When POST succeeds:
  - `Configuring Memory → Done`
  - `iDRAC Config → Done`
  - Dell logo appears.
- Entering **F10 (Lifecycle Controller)** or **Ctrl-R (RAID config)** often causes:
  - freeze/reset
  - fans ramp to 100%.

---

### Hardware Configuration
- Model: Dell PowerEdge R720xd (2.5" chassis)
- Rear flex bay present (2× 2.5" drives)
- vFlash full-size SD slot present (no card installed)
- Single PSU installed
- Mixed ECC RDIMM DDR3 modules available

---

### Work Performed

#### Full System Teardown
- Removed motherboard from chassis.
- Inspected board and connectors.

#### Removed Components
- Rear NIC module
- 3× PCIe cards
- Drive backplane
- SAS cables
- All drives

#### Minimal Boot Configuration Tested
- PSU
- Motherboard
- 2× CPUs installed
- 1× 4GB ECC RDIMM in slot A1

#### Memory Testing
- Tested multiple DIMM combinations.
- Tested single DIMM in A1.
- Swapped between different DIMM sticks.

#### Observed Behavior
- System sometimes POSTs successfully.
- Other times system powers with fans but no video output.
- Lifecycle Controller / RAID utility frequently crash while loading.

#### Firmware / Controller Observations
- `iDRAC Config → Done` appears during POST.
- Crashes often occur when entering Lifecycle Controller.

#### Additional Checks
- CMOS battery removed earlier to reset configuration.
- vFlash SD slot verified empty.
- No internal microSD found on motherboard.

---

### Next Planned Steps
- Inspect / reseat CPUs (once thermal paste is available).
- Attempt firmware update using Dell bootable update ISO.
- Continue testing with alternate DIMMs if instability persists.

#### Suspected Issue
- Corrupted BMC - IDRAC
- Possible CPU problems

## March 13, 2026 – Troubleshooting Log (Dell R720xd)

### Current Thoughts 
- Thinking the idrac6 nand flash is corrupt and due to the unstable state I will try to install a firmware update via a live linux USB
- RAM, CPU, and NIC all working
- Will continue at a later date...
