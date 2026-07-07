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

## Greenhouse Systems (Per-Kerbal Baseline)
All greenhouse types share the same inputs. Outputs and crew efficiency vary by tier.

### Input (all tiers)
| Resource | Rate (L/s) |
| -------- | ---------- |
| WasteWater | 0.00005 |
| CarbonDioxide | 0.005 |
| ElectricCharge | 0.02 |

### Output by Tier
| Tier | Part | Type | Efficiency | O₂ (L/s) | Food (L/s) | Water (L/s) |
| ---- | ---- | ---- | ---------- | -------- | ---------- | ----------- |
| 1 | KPBS Greenhouse, SSPX greenhouse-* | Greenhouse | 1.2× | 0.0045 | 0.00005 | 0.00005 |
| 2 | SSPX cupola-greenhouse-* | Hydroponics | 1.6× | 0.006 | 0.00008 | 0.00008 |
| 3 | SSPX aquaculture-* | Aquaculture | 2.0× | 0.005 | **0.00012** | 0.00006 |
| 4 | SSPX dome-greenhouse-* | Aeroponics | 2.5× | 0.008 | 0.0001 | 0.0001 |

### Crew Efficiency
| Type | Crew Efficiency |
| ---- | --------------- |
| **Greenhouse** | 1.2× per crew |
| **Hydroponics** | 1.6× per crew |
| **Aquaculture** | 2.0× per crew |
| **Aeroponics** | 2.5× per crew |

The effective output rate is `baseRate × (1 + (crewCount - 1) × crewEfficiency)`.

### Example Output Scaling (Tier 1 Greenhouse)
| Crew | O₂ effective | Food effective | Water effective | Kerbals supported (O₂) |
| ---- | ------------ | -------------- | --------------- | ---------------------- |
| 1 | 0.0045 | 0.00005 | 0.00005 | 0.9 |
| 2 | 0.0099 | 0.00011 | 0.00011 | **2.0** |
| 3 | 0.0184 | 0.00020 | 0.00020 | **3.7** |
| 4 | 0.0299 | 0.00033 | 0.00033 | **6.0** |

### Example Output Scaling (Tier 4 Aeroponics)
| Crew | O₂ effective | Food effective | Water effective | Kerbals supported (O₂) |
| ---- | ------------ | -------------- | --------------- | ---------------------- |
| 1 | 0.008 | 0.0001 | 0.0001 | 1.6 |
| 2 | 0.028 | 0.00035 | 0.00035 | **5.6** |
| 3 | 0.068 | 0.00085 | 0.00085 | **13.6** |
| 4 | 0.148 | 0.00185 | 0.00185 | **29.6** |

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
