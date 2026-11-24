# ForkCandles — tealight liberation and integration

*Liberating silicon, one tealight at a time.*

## Objective

Repurpose inexpensive electronic tealight controllers to create sparse, natural twinkling in a conventional DC Christmas light string. Retain the original string emitters for optical matching. This is a separate salvage based proof of concept, feeding findings into StarsAtNight and Mastermind.

## Donor investigation

Buy several cheap electronic tea lights, preferably with separate emitter and controller. Photograph PCB and markings, trace topology, measure supply and LED waveforms before modification. Replace the donor emitter with the same type used in the target string if ratings and drive permit. Test current limiting, voltage sweep, oscillator rate, reset behaviour and whether the output is a sink, source or PWM. Do not assume undervolting slows the oscillator. Candle modulation may be much too frequent; first trial a few nodes among hundreds.

## Research references

- https://cpldcpu.com/2013/12/08/hacking-a-candleflicker-led/
- https://github.com/cpldcpu/CandleLEDhack
- https://cpldcpu.com/2024/01/14/revisiting-candle-flicker-leds-now-with-integrated-timer/
- https://www.padauk.com.tw/
- https://www.bliss.com.tw/en/digital.htm

These are leads from the discussion; verify current datasheets, availability and licence before use. No third party source code is included. For manufacturing enquire about existing programmable controller die, custom firmware, analogue current modulation, minimum order, cost and ownership. A normally illuminated LED with rare independent dips is the target.

## Integration plan

- Characterise an isolated low voltage static string and its branch current limiting.
- Trace donor PCB supply and output connections before transplanting the original string LED.
- Confirm voltage and current compatibility throughout the dimming range; provide separate supply conditioning or an interface transistor if needed.
- Compare resting brightness with an unmodified branch and measure temporal modulation.
- Trial a handful of modified nodes among hundreds of static LEDs, then adjust density to taste.
- Record teardown photographs, schematics, waveforms and measured results.

No assumption is made that donor boards are flicker free or suitable for direct connection. All concepts are untested.
