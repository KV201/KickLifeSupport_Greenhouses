# Consumables
Most of the resources, including base consumables, are provided by the Community Resource Pack.

Note: Rates per "day" are rates in Kerbal Days (6 hours)
## Food -> Waste
Kerbals consume `Food` at a rate of 0.00002 L/s/kerb (0.072 L/hour/kerb; 0.432 L/day/kerb). `Food` is digested into `Waste`, a generic type of trash, which is collected in an onboard tank. `Waste` can be pumped out to a disposal spacecraft (a disposable resupply vehicle, munar module before jettison, etc). As of the current version, food is consumed on a continuous basis.
## Water -> WasteWater
Kerbals consume `Water` at a rate of 0.00003 L/s/kerb (0.108 L/hour/kerb; 0.648 L/day/kerb). `Water` is digested into `WasteWater`, which is collected in an onboard tank. `WasteWater` can be pumped out to a disposal spacecraft or released into space via an `FTE-1 Drain Valve` or similar.
## Greenhouses
Greenhouses convert `WasteWater + CO2 + EC → O2 + Food + Water`. Output is flat (no crew scaling) and scales by part size.

| Size | O2 (L/s) | Food (L/s) | Water (L/s) | Kerbals Supported |
| ---- | -------- | ---------- | ----------- | ----------------- |
| Small (1.25m) | 0.01 | 0.00004 | 0.00006 | ~2 |
| Medium (2.5m) | **0.02** | 0.00008 | 0.00012 | **4** |
| Large (3.75m) | 0.03 | 0.00012 | 0.00018 | ~6 |
| XL (5m) | 0.04 | 0.00016 | 0.00024 | ~8 |

All greenhouse parts include a CDRA scrubber.
The KPBS Water Purifier container (`KKAOSS_LS_container_waterpurifier`) converts `WasteWater` back into `Water` using EC. Purification rate is 0.000045 L/s Water output from 0.00005 L/s WasteWater + 0.05 EC/s input.
## Oxygen -> CarbonDioxide
Kerbals consume `Oxygen` at a rate of 0.005 L/s/kerb (18 L/hour/kerb; 108 L/day/kerb). Kerbals expel `CarbonDioxide` into the cabin air where it will build up over time. Kerbals produce CO2 at a rate of 0.0041 L/s/kerb (14.76 L/hour/kerb; 88.56 L/day/seat). The scrubber system extracts `CarbonDioxide` from the cabin air and consumes `LithiumHydroxide` in the process, or uses the CDRA zeolite beds (hardware parts only). See the [[Cabin Air System]] for more details.
## LithiumHydroxide -> Waste (LiOH Scrubber)
The LiOH Scrubber uses `LithiumHydroxide` (labeled `LiOH`) to remove `CarbonDioxide` from the cabin. The `LithiumHydroxide` gets turned to `Waste` by volume. The scrubber uses EC at a rate of 0.05 EC/s/seat (180 EC/hour/seat; 1080 EC/day/seat), and uses `LithiumHydroxide` at a rate of 0.000015 L/s/seat (0.054 L/hour/seat, 0.324 L/day/seat). A single LiOH cartridge holds 0.5 L of `LithiuymHydroxide`. It takes about 3 hours to deplete a single cartridge for a crew of 3.
## CDRA Scrubber (Zeolite)
CDRA scrubbers are found on hardware parts (greenhouses, science labs). They use EC (0.5 EC/s/seat) and zeolite beds to capture CO2 without consumables. The beds saturate after ~1 hour of continuous scrubbing (1 crew). Start regeneration from the PAW — regenerating consumes 2.5 EC/s for ~5 minutes. During regen the module cannot scrub.
## Emergency O2 Reserve
Each LS-equipped part carries an Emergency O2 Reserve (100 L default) that can be toggled on from the PAW. When active, it releases O2 at 0.005 L/s/kerb until depleted.
## CO2 Vent Valve
The "Vent CO2 Overboard" button (found on any LS module's PAW) instantly dumps all cabin CO2. Useful in emergencies or when switching scrubber modes.
## Air Filter
All scrubbers include a replaceable air filter that degrades during operation. Replace it via the PAW button (costs 0.5 EC). Degrades at 0.00005/s/crew; lasts ~5.5 hours with 1 crew.
