# TCP51Prime
LLL chal, we used sage to get our answer.

## Rearranging the Equation
To solve for a and b, you can rearrange the equation as follows:
$𝑝−𝑎^(51)=51⋅𝑏^(51)$
If we isolate $𝑏^(51)$:

![image](https://github.com/user-attachments/assets/19c7c01e-c304-40fc-91c1-838342f4a239)

 
Now, in modular arithmetic, we are trying to work modulo p, so you want to consider this equation modulo p.
However, since we are dealing with an equation involving $a^51 and 51.b^51$,you end up looking for solutions where:
$x^51≡−51modp$
Here, x represents a potential candidate for b.
The reason we are solving for −51 is because the term 51⋅b^51 on the right side of the equation corresponds to −51
−51 in modular arithmetic, and we are trying to find the values of 𝑏 such that:
$𝑏^51 ≡−51modp$

## Steps to Find 51st Roots Modulo 
Start with the Modular Equation: we are given 
$x^51≡−51modn$
Work Modulo n: This means both sides of the equation are reduced modulo n.
we are trying to find x such that when x is raised to the power 51, the result is congruent to −51 under modulon.
So we are not working with exact values like in standard arithmetic but rather their equivalence classes modulo n.
Use a Root-Finding Method: In this case, we are using Sage's function nth_root. This function is designed to solve for roots modulo a number n.
All Solutions: Modular equations often have multiple solutions because there may be several values of x that satisfy:
$x^51≡−51(modn)$
## Breakdown of the Matrix Components
### First Row: [n, 0]
The first row consists of two elements:
#### Element 1: The first element is the large prime n, which represents the value you're trying to match with the equation:
$a^51+51b$
#### Element 2: The second element is 0. This forms a standard row structure that helps in the reduction process and provides a baseline in the lattice.
This row essentially creates a "target" for the lattice, as it sets one dimension of the space to be equal to n.

### Second Row: [Integer(x), 1]

The second row consists of:
#### Element 1: The first element is Integer(x), which is the current root of −51 found modulo n.
This root is significant because it represents a candidate value for b when manipulated in the equation.
#### Element 2: The second element is 1. This introduces another dimension to the lattice that allows the LLL algorithm to explore combinations that can generate values related to a.
This row incorporates the candidate root x as part of the structure, allowing the LLL algorithm to find combinations that might lead to valid a and b.
