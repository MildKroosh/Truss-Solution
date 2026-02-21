# Truss-Solution
1. Problem Idealization

The structure is modeled as a 2D pin-jointed truss.

Assumptions made:

• All joints are frictionless pins
• Members carry only axial force
• Loads are applied only at joints
• Self-weight is neglected
• Structure is statically determinate

Each joint has two equilibrium equations:

∑Fx=0
∑Fx=0
∑Fy=0
∑Fy=0

2. Identification of Unknowns

Unknown member forces:

FAB
FBC
FCD
FAE
FED
FBE
FCE

Unknown reaction:

Ey

Total unknowns = 8

Since each joint provides 2 equilibrium equations,
5 joints × 2 = 10 equations

System is solvable.

3. Direction Cosine Calculation

Members inclined at 60° are resolved into components.

Using:

c60=cos⁡(60∘)
c60=cos(60∘)
s60=sin⁡(60∘)
s60=sin(60∘)

For diagonal members with length 4 units:

Horizontal projection = 2
Vertical projection = 3.464

Direction ratios:

24,3.4644
4
2,
4
3.464
	

These ratios convert axial force into x and y components.

4. Joint-by-Joint Equilibrium Formulation

Each joint is isolated as a free body diagram.

All unknown forces are assumed tensile (away from joint).

If result is negative → member is in compression.

Joint A

Horizontal equilibrium:

FABcos⁡60+FAE=0
FABcos60+FAE=0

Vertical equilibrium:

FABsin⁡60=0
FABsin60=0
Joint B

Horizontal equilibrium:

−FABcos⁡60+FBC+FBE(2/4)=0
−FABcos60+FBC+FBE(2/4)=0

Vertical equilibrium:

−FABsin⁡60−FBE(3.464/4)=0
−FABsin60−FBE(3.464/4)=0
Joint C

Horizontal equilibrium:

−FBC+FCDcos⁡60−FCE(2/4)=0
−FBC+FCDcos60−FCE(2/4)=0

Vertical equilibrium:

FCDsin⁡60−FCE(3.464/4)=0
FCDsin60−FCE(3.464/4)=0
Joint D

External load of 8 kN downward applied.

Horizontal equilibrium:

−FCDcos⁡60−FED=0
−FCDcos60−FED=0

Vertical equilibrium:

−FCDsin⁡60−8=0
−FCDsin60−8=0
Joint E

Includes vertical support reaction Ey.

Vertical equilibrium:

Ey−FBE(3.464/4)−FCE(3.464/4)=0
Ey−FBE(3.464/4)−FCE(3.464/4)=0

Horizontal equilibrium:

FAE+FED+FBE(2/4)−FCE(2/4)=0
FAE+FED+FBE(2/4)−FCE(2/4)=0
5. Formation of Simultaneous Equation System

All 10 equilibrium equations are written symbolically using:

syms FAB FBC FCD FAE FED FBE FCE Ey


Each equation is stored as:

eq1 = ...


All equations are passed into:

solve([eq1 eq2 ... eq10], [unknowns])


MATLAB Symbolic Solver performs simultaneous algebraic elimination.

6. Solution Extraction

The symbolic results are converted into numerical values using:

double(sol.variable)


Member forces are printed in kN.

7. Interpretation of Results

Sign Convention:

Positive → Tension
Negative → Compression

Verification:

• Check equilibrium at one joint manually
• Verify reaction balances external load
• Ensure sum of vertical reactions = 8 kN


Total upward reactions = 8 kN
Internal forces satisfy all equilibrium equations

Then structure satisfies static equilibrium
