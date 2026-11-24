# Much Ado About Nothing — firmware concept

Candidate: Padauk PMS150C or equivalent low resource OTP MCU. Target around 1K words program memory, 32–64 bytes RAM, internal oscillator, timer wake, low microamp standby and one output. Confirm exact voltage range, sleep timer, package, programmer and current from current datasheet before selecting. Flash MCU preferable for repeated prototype iterations.

## Behaviour

Default is shunt OFF. Each module receives a distinct seed (programmed serial seed or validated entropy). Never use identical fixed seeds across all modules. On reset, initialise safe output before enabling drive. Use low power timed wake where supported.

```text
initialise output OFF
seed PRNG with unique nonzero seed
loop:
    wait random interval (initial trial 10–300 s)
    choose event duration (initial trial 50–1500 ms)
    choose dip depth and envelope if analogue hardware supports it
    activate shunt for event
    restore shunt OFF
```

Start with hard dips, then test gentle dips and recoveries. A short event-only filtered PWM signal can generate a DC gate reference, but verify actual optical ripple; direct DAC is preferred. No repetitive modulation during idle. Measure event occupancy rather than promising a fixed percentage: mean duration / (mean idle + mean duration). With 20 modules and mean idle 155 s, expect roughly one event every 8 s across the tree. Tune by observation. Avoid synchronisation on power cycling.

Firmware is original pseudocode, not a buildable or tested implementation.
