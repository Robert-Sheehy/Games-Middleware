Vector decomposition using the identity $\vec{v} = (\vec{v} \cdot \hat{n})\hat{n} + (\vec{v} - (\vec{v} \cdot \hat{n})\hat{n})$ splits a vector into parallel and perpendicular components relative to a unit normal vector ($\hat{n}$). This specific mathematical framework is the foundational baseline for physics engines, custom collision responses, and steering behaviors in Unity.
------------------------------
## 1. The Mathematical Breakdown
For this identity to work, $\hat{n}$ must be normalized (length = 1).

* The Identity: $\vec{v} = \vec{v}_{\parallel} + \vec{v}_{\perp}$
* Parallel Component ($\vec{v}_{\parallel}$): $(\vec{v} \cdot \hat{n})\hat{n}$
* $\vec{v} \cdot \hat{n}$ is a scalar. It yields the projected length.
   * Multiplying by $\hat{n}$ converts it back into a vector.
   * This points directly along the normal axis.
* Perpendicular Component ($\vec{v}_{\perp}$): $\vec{v} - (\vec{v} \cdot \hat{n})\hat{n}$
* This subtracts the parallel component from the original vector.
   * It isolates the remaining motion.
   * This component runs purely along the surface plane.

------------------------------
## 2. Unity C# Implementation
You can write this identity manually using Vector3.Dot, or use Unity's highly optimized built-in wrappers.
## Manual Implementation (Pure Math)

using UnityEngine;
public class ManualDecomposition : MonoBehaviour
{
    public Vector3 v = new Vector3(3f, 5f, 2f);
    public Vector3 surfaceNormal = new Vector3(0f, 1f, 0f); // Must be normalized

    void Start()
    {
        // Ensure n is a unit vector
        Vector3 n = surfaceNormal.normalized;

        // 1. Parallel component: (v . n)n
        float dotProduct = Vector3.Dot(v, n);
        Vector3 vParallel = dotProduct * n;

        // 2. Perpendicular component: v - (v . n)n
        Vector3 vPerpendicular = v - vParallel;

        Debug.Log($"Parallel Component: {vParallel}");
        Debug.Log($"Perpendicular Component: {vPerpendicular}");
    }
}

## The Unity Shortcut Implementation
Unity provides explicit functions that run this exact vector math under the hood.

* Vector3.Project(v, n) computes $(\vec{v} \cdot \hat{n})\hat{n}$.
* Vector3.ProjectOnPlane(v, n) computes $\vec{v} - (\vec{v} \cdot \hat{n})\hat{n}$.

using UnityEngine;
public class UnityDecomposition : MonoBehaviour
{
    public Vector3 v = new Vector3(3f, 5f, 2f);
    public Vector3 n = Vector3.up; 

    void Start()
    {
        // Matches: (v . n)n
        Vector3 vParallel = Vector3.Project(v, n);

        // Matches: v - (v . n)n
        Vector3 vPerpendicular = Vector3.ProjectOnPlane(v, n);

        // Verification
        Vector3 reconstructed = vParallel + vPerpendicular; 
    }
}

------------------------------
## 3. Quick Reference Table

| Math Component | Geometric Meaning | Unity Alternative | Common Game Dev Use Case |
|---|---|---|---|
| $(\vec{v} \cdot \hat{n})\hat{n}$ | Parallel projection onto normal | Vector3.Project(v, n) | Calculating bounce impact force |
| $\vec{v} - (\vec{v} \cdot \hat{n})\hat{n}$ | Perpendicular rejection | Vector3.ProjectOnPlane(v, n) | Moving along a slope smoothly |

Would you like to see how to use this identity to build a custom elastic reflection (bounce) script, or apply it to friction calculations when sliding?

