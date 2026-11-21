# Multistage Countercurrent Liquid-Liquid Extraction (Python)

Acetone / water / 1,1,2-trichloroethane at 25 °C, solved in Python. Based on Exercise 8.12 of
Seader, Henley & Roper, *Separation Process Principles with Applications Using Process Simulators* (4th ed.).

**Problem:** 1000 kg/h feed, 45 wt% acetone in water, extracted countercurrently with pure
trichloroethane to a raffinate with 10 wt% acetone.

## What the notebook does
- Fits the tie-line data with the Othmer-Tobias correlation
- Finds the minimum solvent rate (feed on an extended tie line)
- Steps off stages on a right-triangular diagram using the difference point P
- Solves the flow of every stream with a 3-component balance (acetone, solvent, water)
- Validates the balance on every stage and overall (residuals ~1e-11 kg/h)
- Plots the triangular diagram, a McCabe-Thiele-type diagram and the acetone profile

## Results
| Item | Value |
|---|---|
| Minimum solvent rate | 222.3 kg/h |
| Solvent at 1.5 x minimum | 333.5 kg/h (4.69 stages, so 5 ideal stages) |
| Solvent for exactly 5 stages and 10% acetone raffinate | 322.7 kg/h |

## Run it
```bash
pip install numpy scipy pandas matplotlib jupyter
jupyter notebook Multistage_Countercurrent_LLE_Acetone_TCE.ipynb
```

## Credits
Inspired by the notebook by Yoseph Christian (iamyosephch/chemical-engineering) on the same exercise.
This version rebuilds the workflow and adds a validation of all three component balances on every stage.

*For learning purposes only.*
