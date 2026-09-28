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




