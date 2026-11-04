# CHANGELOG

All notable changes to the Sampler-DIOT are documented in this file.

## v3.0

**Release owner:** Mikołaj Sowiński (TS)

**Designers:** 
- Krzysztof Belewicz (WUT)

**Reviewers:** 
- Maciej Przybysz (TS)
- Marta Fąfara (TS)

**Contributors:** 
- Marcin Kiepiela (TS)

**Funded by:** 
- WUT ISE
- Technosystem

Updated according to DIOT template
All schematic files updated according to DIOT template.
Change list in respect to the previous revision:

project parameters:
-added link to repository
-set version number to 2.3.1 (same as previous release, to be moved)

schematic pages:
-Unified ADC_IN_P/N and IN_P/N net naming accross the schematic pages
-Unified TERM_IND/ TERM_STAT net naming accross the schematic pages
-Front panel connectors, LEDs and mezzanine connectors moved to a dedicated page
-Mechanical components moved to a dedicated page
-IC3 changed from P3V3_MP to P3V3
-DRC exclusions changed from 'All violations' to 'specific violations' where applciable
-Added schematic notes about inversed LVDS polarity at LVDS drivers
-Rearanged power supply section for better readability
-Added missing decoupling capacitors to IC27, IC26
-Added additional Testpoints and LEDs to the power rails
-P12V0/P3V3_MP testpoint symbol unified with the rest of the project
-Front panel LEDs: Power-On (D24) changed from red/3V3 to green/PGOOD to match DIOT template; green DUAL-EEM mode (D22) changed to red overtemperature to match DIOT template
-Front panel LEDs PN changed to 571-0122F due to placement/pcb outline constraints

variants:
Project previously had variants: STD/4HP/DIOT/EEM, while only STD variant was present in the releases.
"STD" variant differs by not mounting shield clips, and not mounting C6 in ADC input filter
"4HP" variant differs by erroneously mounting opposing power regulator footprints where multiple options are present for redundancy (REF_VCC/ N12V0A/ P2V5A/ REF_P4V096)
"EEM" variant differs by not mounting DIOT connectors and erroneously mounting opposing power regulator footprints for REF_P4V096
"DIOT" variant differs by not mounting EEM connectors/ external power connector and not mounting EEPROM packages (except single EEM0 device, for all other variants all EEPROM packages are mounted - including redundant footprint device)

As such, variants were unified into "EEM" and "DIOT" to both match the DIOT template and correct the errors listed above. "STD" variant was treated as the correct source.

BOM count reductions:
T_C12 changed from 22pF 0402 C0G 5% to 18pF 0603 5% C0G
C40, C42, C46, C75, C82 changed from 10nF 0603 50V 10% X7R to 10nF 0402 50V 5% X7R
R75 changed from 20k 0402 to 2x 10k 0402
T_R30 changed from 3k9 to 2k7 + 1k2
T_R29 changed from 100k 0402 to 100k 0603
R70/R71 divider changed from 51k/47k to 36k/33k (2.544V changes to 2.551V)
100nF 0402 16V 10% X5R/X7R changed to 100nF 0402 50V 10% X7R (same as DIOT template)
C87-C90, C92-C93 changed from 100nF 0603 16V 10% X7R to 100nF 0402 50V 10% X7R (same as DIOT template)
Total of 10 BOM positions dropped
potential additional changes:
R2/R9 A-H can be changed from 0R 0603 to 0R 0402

pcb:
corrected board outline, added mounting holes/ new components as per DIOT template

C99 moved closer to the ADC
RN3A mirrored for better routing
RN3C-RN3B swapped for better routing
RN4D mirrored for better routing
RN3A-RN3D swapped for better routing
RN3C mirrored for better routing
C103/C106 moved to be placed at opamp pins, not at resistor pins
removed unnecesary vias to keep as much on top layer as possible
IC35A/B swapped for better routing
IC35/RN3/RN4 rotated by 180deg to bring P4V096V input closer to the source
Removed unnecesarry vias (eg at C6B/C7B) - too many to list
Rotated IC19 to match IC20 and improve routing
SPI traces between IC19 and IC20 moved to consider reference plane and crosstalk

Added xsignals to the project
Added and enabled missing design rules

Updated stackup to the unified 4 layer 1.6mm version
- corrected trace geometry
- length matched DIOT/EEM signals

- added SMA connectors to the board

Modified mezzanine scheme
- added Wurth threaded standoffs
- moved half of LEDs to the mezzanine
- changed board-to-board distance from 11mm to 12mm
- changed connector positions to match new front panel

Additional associated changes:
- moved AFE section (including shield) ~3.5mm towards the backplane
- moved IO I2C expander towards the front panel

Updated to match DIOT Template v1.4 (both main PCB and the front panel adapter PCB)
- updated project parameters
- updated schematic sheet templates
- modified sheet order in the project
- added Draftsman file to the project
- enabled component clearance rules, added exceptions
- added fiducials on the adapter board

Aligned mainboard to adapter connectors and mounting holes
Locked position on PcbDocs
Moved project version to 3.0.0

---

## Prior releases

**Designers:**
- Grzegorz Kasprowicz (WUT)
- Łukasz Pająk (WUT)

**Reviewers:**
- unspecified

**Contributors:**
- unspecified