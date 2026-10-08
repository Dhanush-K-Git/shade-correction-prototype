# Shade-correction prototype (synthetic data)

A small notebook that tests one idea: **if a printer responds to colour changes in a roughly steady way, a calibrated correction calculator can fix a shade mismatch in about 1-2 correction rounds.**

Everything here is simulated. No real production data is used, and the results say nothing about any real printer.

## What is in the notebook
- A made-up printer with 6 colour channels and 4 measured spots on a tile
- A one-time setup from 13 test tiles that learns how each channel moves the colour
- A calculator that suggests the smallest channel changes to cancel a measured colour difference
- 300 simulated changeovers compared with a crude "guess and check" stand-in
- Stress tests: noisy measurements, a curved (non-steady) response, and larger starting drift

## Files
- `shade_correction_prototype.ipynb`: the notebook, already run with its outputs saved
- `rounds.png`: the result chart

## Run it
```
pip install numpy matplotlib scikit-image jupyter
jupyter notebook shade_correction_prototype.ipynb
```

## Honest limits
The method works in this simulation only while measurement noise is low and the response is close to a straight line. Strong curvature or a very noisy device breaks it, and the notebook shows where.
