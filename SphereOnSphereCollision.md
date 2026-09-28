# Sphere on Sphere collision resolution

<img width="528" height="403" alt="image" src="https://github.com/user-attachments/assets/99d2667c-be59-4147-8c30-ac31df3c688b" />

## Detecting a collision

A collision occurs when the distance $d$ between the centres of the spheres is less than the sum of the radii i.e. $d<R=r$

## Resolving the collision 

$S_{1}$ Sphere 1 which has position $P_{1}$ and a radius of $r_{1}$ a velocity of $v_{1}$ and a mass of $m_{1}$

Similarly:
$S_{2}$ Sphere 2 which has position $P_{2}$ and a radius of $r_{2}$ a velocity of $v_{2}$ and a mass of $m_{2}$

<img width="535" height="427" alt="image" src="https://github.com/user-attachments/assets/a096da7c-da36-4463-8ebd-5e818748e04b" />


The normal of the collision will be parallel to the line which joins the centres of the spheres

i.e. $n = (P_{2} - P_{1}).normalised$

As with the sphere on plane calculations we decompose the velocity (in this case the velocities) into parallel and perpendicular components

So $v_{1} = v_{1\parallel} + v_{1\perp}$

and $v_{2} = v_{2\parallel} + v_{2\perp}$

To resolve the collision we "reverse" the parallel and leave the perpendicular untouched

Unlike the plane calculations, both spheres are moving so we have to use the conservation of momentum formulae to resolve

<img width="695" height="215" alt="image" src="https://github.com/user-attachments/assets/f4f4a97e-82e4-4e4b-965a-7099eca61861" />

Here we use the masses of our spheres and the parallel components of the velocities to calculate the resolved parallel components of the velocities of the spheres

$v_{1\parallel}^{*}$  resultant paralell component (to n) of velocity of sphere 1 after collision

$v_{2\parallel}^{*}$  resultant parallel component (to n) of velocity of sphere 1 after collision

Overall velocities will be
$v_{1}^{\*}$ = CoR * $v_{1\parallel}^{\*} + v_{1\perp}$
Similarly for $v_{2}$

##  Implementing Time of impact calculations

Follow the logic as before

$d_{1}$ will be $d - (r_{1} + r_{2})$ when the collision was detected
$d_{0}$ was the same value calculated in the previous frame

As before the following must be done:

- calculate the Time of Impact (using the same formula as before)
- Calculate positions, velocities at the time of impact
- Resolve the vleocities at time of impact
- Fast forward to present frame be calculating new postions and velocities
  
