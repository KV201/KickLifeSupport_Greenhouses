# Rates Tables
## Basic Systems

| System    | Resource In | In Rate (L/s/kerb) | Resource Out  | Out Rate (L/s/kerb) | Notes                                    |
| --------- | ----------- | ------------------ | ------------- | ------------------- | ---------------------------------------- |
| Breathing | Oxygen      | 0.005              | CarbonDioxide | 0.0041              | CarbonDioxide builds up in the cabin air |
| Eating    | Food        | 0.00002            | Waste         | 0.000018            |                                          |
| Drinking  | Water       | 0.00003            | WasteWater    | 0.000028            |                                          |
## Complex Systems
| System   | Res 1 In      | Res 1 In Rate (L/s/seat) | Res 2 In         | Res 2 Rate (L/s/seat) | EC Rate (EC/s) | Resource Out | Out Rate (L/s/seat) | Thermal Flux (kW/seat) | Notes                |
| -------- | ------------- | ------------------------ | ---------------- | --------------------- | -------------- | ------------ | ------------------- | ---------------------- | -------------------- |
| Scrubber | CarbonDioxide | 0.005                    | LithiumHydroxide | 0.000015              | 0.05           | Waste        | 0.000015            | 0.02                   | EC rate is EC/s/seat |
| CDRA     | CarbonDioxide | 0.005                    | N/A              | N/A                   | 0.5            | N/A          | N/A                 | 0.0075                 | EC rate is EC/s/seat |

## CDRA Regeneration
| Parameter       |  Rate                      |
| --------------- |----------------------------|
| EC Draw         | 2.5 EC/s                   |
| Duration        | ~5 min                     |
| Saturation Rate | 3.858e-7/s/crew (~30 days) |

## Air Filter
| System    | Degrade Rate        | Cost to Replace |
| --------- | ------------------- | --------------- |
| Scrubber Filter | 3.858e-7/s/crew (~30 days) | 0.5 EC |

## Water Purifier
| Input      | Rate      | Output | Rate         | EC Cost |
| ---------- | --------- | ------ | ------------ | ------- |
| WasteWater | 0.00005   | Water  | 0.000045 L/s | 0.05 EC/s |

## Sabatier Reactor
| Input        | Rate    | Output       | Rate    | EC Cost |
| ------------ | ------- | ------------ | ------- | ------- |
| CarbonDioxide | 0.01    | LiquidFuel   | 0.004   | 2.0 EC/s |
|              |         | Oxidizer     | 0.005   |         |
|              |         | Water        | 0.001   |         |

## ISRU Water Extraction
| Input   | Rate    | Output | Rate    | EC Cost |
| ------- | ------- | ------ | ------- | ------- |
| Ore     | 0.01    | Water  | 0.01    | 0.5 EC/s |
| Hydrogen | 0.005  |        |         |         |

## ISRU Waste Recycling
| Input | Rate      | Output    | Rate    | EC Cost |
| ----- | --------- | --------- | ------- | ------- |
| Waste | 0.000018  | Fertilizer | 0.0005  | 0.2 EC/s |
| Ore   | 0.001     |           |         |         |

## Algae Farm (Stock Lab)
| Input        | Rate    | Output | Rate    | EC Cost |
| ------------ | ------- | ------ | ------- | ------- |
| Water        | 0.00005 | Oxygen | 0.008   | 0.5 EC/s |
| CarbonDioxide | 0.005   | Food   | 0.00002 |         |

## Bioreactor (Moldavite Machines)
| Input        | Rate      | Output    | Rate    | EC Cost |
| ------------ | --------- | --------- | ------- | ------- |
| CarbonDioxide | 0.005     | Fertilizer | 0.0005  | 0.5 EC/s |
| Waste        | 0.000018  | Oxygen    | 0.004   |         |

## Emergency O2 Reserve
| Parameter   | Value         |
| ----------- | ------------- |
| Reserve Size | 100 L (fixed, one-time use) |
| Release Rate | 0.005 L/s/kerb |

## CO2 Vent Valve
Dumps all stored CarbonDioxide resource overboard. Limited to 2 uses per craft — bring a scrubber!

## Greenhouse Systems
All greenhouses share the same inputs.

### Input (all sizes)
| Resource | Rate (L/s) |
| -------- | ---------- |
| WasteWater | 0.00005 |
| CarbonDioxide | 0.005 |
| Fertilizer | 0.00025 (1.25m) / 0.0005 (2.5m) / 0.00075 (3.75m) / 0.001 (5m) |
| ElectricCharge | 0.02 |

### Output by Size
| Size | Part Diameter | O2 (L/s) | Food (L/s) | Water (L/s) | Kerbals Supported |
| ---- | -------------  | -------- | ---------- | ----------- | ----------------- |
| Small | 1.25m | 0.01 | 0.00004 | 0.00006 | ~2 |
| Medium | 2.5m | **0.02** | 0.00008 | 0.00012 | **4** |
| Large | 3.75m | 0.03 | 0.00012 | 0.00018 | ~6 |
| Extra-Large | 5m | 0.04 | 0.00016 | 0.00024 | ~8 |

All greenhouse parts include a CDRA scrubber.

## Electrical Systems
| System          | EC Rate (EC/s) | Thermal Flux (kW) | Notes                                                                                 |
| --------------- | -------------- | ----------------- | ------------------------------------------------------------------------------------- |
| Avionics        | 0.02           | 0.02              | If disabled or no power, pod is not controllable                                      |
| SAS             | 0.01           | 0.01              | If no power, SAS will not work                                                        |
| RCS             | 0.01           | 0.01              | If no power, RCS will not work                                                        |
| Climate Control | 0.003          | 0.03              | If disabled/no power, heater and radiators will not work, and air will not circulate. |
## Heater System
| System | EC Rate (EC/s/kW/seat) | Thermal Flux (kW/seat) | Notes                                                                                              |
| ------ | ---------------------- | ---------------------- | -------------------------------------------------------------------------------------------------- |
| Heater | 1                      | 1                      | This is adjustable in the editor and in-game. Settings default to 1.0 kW of heater power per seat. |
