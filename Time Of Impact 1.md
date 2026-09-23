# Time of Impact (Sphere and Plane)

Vector decomposition using the identity $\vec{v} = (\vec{v} \cdot \hat{n})\hat{n} + (\vec{v} - (\vec{v} \cdot \hat{n})\hat{n})$ splits a vector into parallel 
and perpendicular components relative to a unit normal vector ($\hat{n}$).

## Detect Collision

$P_{p}$ Plane position (plane.transform.position)   
$P_{s}$ Sphere position ( sphere.transform.position)
$\hat{n}$ Plane Normal ( plane.transform.up)

$P_{p to s} = P_{s} - P_{p} $

$P_{p to s} \cdot \hat{n}$  Raw perpendicular "distance" from sphere centre to plane

$d_{1} = P_{p to s} \cdot \hat{n} - r $

Collision is detected if $d_{1} <0 $

##  Find and resolve Time of impact

### Note::  For efficiency
We will have in the code for the sphere
```csharp
velocity += acceleration * Time.deltaTime;
transform.position += velocity * Time.deltaTime;
```
so we cache them before adjusting 
```csharp
Vector3 oldVelocity = velocity;   // Local variable
Vector3 oldPosition = transform.position;  // Local variable
oldD1 = d0     // Global variable


velocity += acceleration * Time.deltaTime;
transform.position += velocity * Time.deltaTime;
```
### Calculate Time of Impact

$P_{0}$ old position

$v_{0}$ old velocity

$a$  acceleration

$T = T_{1} - T_{0}$  Total time (Time.deltaTime)

$d_{1}, d_{0}$  distances from surface to plane $d_{1} <0$

$v_{drop}  =\frac{ d_{1} - d_{0} } {T}$ :      Drop speed for frame (float)

$T_{impact} = \frac{-d_{0}} {v_{drop}}$ :     Time of impact (float)

$v_{impact} = v_{0} + a * T_{impact}$   :       velocity at time of impact (Vector3)

$P_{impact} = P_{0} + v_{impact}* T_{impact}$ :   position at time of impact (Vector3)

### Resolve collision (adjust the velocity for the bounce)

$v_{\parallel} = (\vec{v} \cdot \hat{n})\hat{n} $

$v_{\perp}  =  (\vec{v} - (\vec{v} \cdot \hat{n})\hat{n})$

$v_{impact out} = v_{\perp} - CoR * v_{\parallel} $

### Fast forward to current frame
$T_{remaining} = T - T_{impact}$

$v = v_{impact out} + a * T_{remaining}$   Here was assign the final velocity, i.e. the velocity vector in code

$P = P_{impact} + v*T_{remaining}$          Here we assign the final position i.e. transform.position










