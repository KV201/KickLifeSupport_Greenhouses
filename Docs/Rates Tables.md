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
| Parameter       | Rate          |
| --------------- | ------------- |
| EC Draw         | 2.5 EC/s      |
| Duration        | ~5 min        |
| Saturation Rate | 0.00028/s/crew |

## Air Filter
| System    | Degrade Rate | Cost to Replace |
| --------- | ------------ | --------------- |
| Scrubber Filter | 0.00005/s/crew | 0.5 EC |

## Water Purifier (KPBS)
| Input        | Rate      | Output | Rate         | EC Cost |
| ------------ | --------- | ------ | ------------ | ------- |
| WasteWater   | 0.00005   | Water  | 0.000045 L/s | 0.05 EC/s |

## Emergency O₂ Reserve
| Parameter   | Value         |
| ----------- | ------------- |
| Reserve Size | 100 L (default) |
| Release Rate | 0.005 L/s/kerb |

## CO₂ Vent Valve
Instantly vents all cabin CO₂. No resource cost.

## Greenhouse Systems
All greenhouses share the same inputs. Output is flat (no crew scaling) and scales by part size.

### Input (all sizes)
| Resource | Rate (L/s) |
| -------- | ---------- |
| WasteWater | 0.00005 |
| CarbonDioxide | 0.005 |
| ElectricCharge | 0.02 |

### Output by Size
| Size | Part Diameter | Parts | O₂ (L/s) | Food (L/s) | Water (L/s) | Kerbals Supported |
| ---- | ------------- | ----- | -------- | ---------- | ----------- | ----------------- |
| Small | 1.25m | cupola greenhouse | 0.01 | 0.00004 | 0.00006 | ~2 |
| Medium | 2.5m | greenhouse, KKAOSS Greenhouse | **0.02** | 0.00008 | 0.00012 | **4** |
| Large | 3.75m | greenhouse, aquaculture | 0.03 | 0.00012 | 0.00018 | ~6 |
| Extra-Large | 5m | greenhouse, dome greenhouse | 0.04 | 0.00016 | 0.00024 | ~8 |

Output is flat — does not scale with crew count. All greenhouse parts include a CDRA scrubber.

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
