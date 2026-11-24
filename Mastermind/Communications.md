# Crossed Lines — communications and topper

Use a robust wired bus appropriate to string length, e.g. low speed differential serial with termination and addressing; choose after measuring cable and load. Fixed node supply avoids brownouts when the passive rail dims. Common ground or isolated interfaces as appropriate. Specify connector current rating, pinout, ESD and hot plug behaviour before construction.

Each node holds an address, local calibrated resting current, maximum current, event state and timeout. On communications loss return to safe static brightness. A DAC plus op amp/MOSFET current sink gives I_LED ≈ Vref/Rsense while in compliance. Use a stable loop and check FET dissipation. True analogue output is the goal, not direct PWM.

The controller maps nodes to installation order (wrap from bottom to top); sparse nodes may require placement planning for convincing motion. A rare comet progresses upward, then sends a coordinated radial burst to the topper. Topper geometry can be configured manually initially; discovery optional later.

Effects: dip, gentle sparkle, brief glint, irregular shimmer, comet with fast attack and slow decay. Keep global background steady. Scale event amplitude with brightness, and provide a fully static mode.
