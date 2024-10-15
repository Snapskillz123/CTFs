# TCP51Prime
LLL chal, we used sage to get our answer.

## Rearranging the Equation
To solve for a and b, you can rearrange the equation as follows:
```𝑝−𝑎^51=51⋅𝑏^51```
If we isolate ```𝑏^51```:

![image](https://github.com/user-attachments/assets/19c7c01e-c304-40fc-91c1-838342f4a239)

 
Now, in modular arithmetic, you're trying to work modulo p, so you want to consider this equation modulo p.
However, since you're dealing with an equation involving ```a^51 and 51.b^51```,you end up looking for solutions where:
```x^51≡−51modp```
Here, x represents a potential candidate for b.
The reason you're solving for −51 is because the term 51⋅b^51 on the right side of the equation corresponds to −51
−51 in modular arithmetic, and you're trying to find the values of 𝑏 such that:
```𝑏^51 ≡−51modp```

## Steps to Find 51st Roots Modulo 
𝑛
n
Here’s how the process works:

Start with the Modular Equation: You're given 
```x^51≡−51modn```
Work Modulo n: This means both sides of the equation are reduced modulo n.
You're trying to find x such that when x is raised to the power 51, the result is congruent to −51 under modulon.
So you're not working with exact values like in standard arithmetic but rather their equivalence classes modulo n.
Use a Root-Finding Method: In this case, you're using Sage's function nth_root. This function is designed to solve for roots modulo a number n.
All Solutions: Modular equations often have multiple solutions because there may be several values of x that satisfy:
$x^51≡−51(modn)$

51
 ≡−51modn. The all=True argument in Sage ensures that you're getting all possible 51st roots of 
−
51
−51 modulo 
𝑛
n.
