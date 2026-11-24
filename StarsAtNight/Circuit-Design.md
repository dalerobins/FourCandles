# Circuit and preliminary BOM

Use an isolated, current limited low voltage bench supply. Confirm the donor topology before connecting: independently ballasted parallel LED branches are assumed; a bipolar or series string requires redesign. A third conductor is not proof of a separate switched channel. Never bypass a mains isolation barrier.

| Ref | Part / function |
|---|---|
| D1, D2 | Identical warm white LEDs from one bin |
| R1, R2 | Identical branch ballast, value based on measured Vf and desired current |
| Q1 | Logic level NMOS, characterised at minimum gate voltage; suitable linear SOA for fades |
| R3 | Gate pulldown, e.g. 100kΩ starting point |
| R4 | Optional gate series resistor |
| U1 | Low power OTP or Flash MCU |
| C1 | Local supply decoupling, e.g. 100nF subject to datasheet |
| Optional | DAC or filtered event-only PWM with analogue output, gate buffer, supply protection |

For example only, 4.5 V rail, 2.8 V LED and 330 Ω gives about 5.2 mA resting current. Full shunt draws about 13.6 mA through the resistor and dissipates about 61 mW. Verify worst case rail, tolerances, temperature and simultaneous events. Do not place a shunt directly across an unballasted supply. A branch constant current source avoids the increased current but needs headroom and a dimming reference.

For deep dimming, verify MCU supply range, brownout behaviour and FET threshold. Gate pulldown should keep the LED on if MCU is unpowered. Keep the rail within MCU absolute limits; use conditioning if necessary. A separate heavier distribution bus may be required for long strings. Fuse appropriately and measure far-end voltage. Target optical matching at multiple brightness levels, not just nominal current.

Production path: donor candle boards → discrete PCB → small OTP board → co-packaged LED die and controller. Supplier firmware may require porting. Preserve original design and review IP/licensing before disclosure.
