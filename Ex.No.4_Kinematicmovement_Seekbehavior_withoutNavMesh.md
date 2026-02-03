# Ex.No: 4  Implementation of Kinematic movement -seek and Flee behavior in Unity
### DATE:  02/02/2026                                                                         
### REGISTER NUMBER : 212224040316
### AIM: 
To write a program to simulate the process of seek and Flee behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12.  Write a script for flee behavior and attach it to target
13.  Run the game
14. Stop the program
    
### Program:
Seek Script
```csharp
using UnityEngine;

public class seekScript : MonoBehaviour
{
    public Transform target;      // Object to seek
    public float speed = 5f;      // Movement speed
    public float stopDistance = 1.5f; // Distance at which movement stops

    void Update()
    {
        if (target == null) return;

        float distance = Vector3.Distance(transform.position, target.position);

        // Stop moving if within stop distance
        if (distance <= stopDistance) return;

        Vector3 direction = (target.position - transform.position).normalized;
        transform.position += direction * speed * Time.deltaTime;
    }
}

```

Flee Script

```csharp
using UnityEngine;

public class fleeScript : MonoBehaviour
{
    public Transform target;      // Object to flee from
    public float speed = 5f;      // Movement speed
    public float safeDistance = 6f; // Distance at which movement stops

    void Update()
    {
        if (target == null) return;

        float distance = Vector3.Distance(transform.position, target.position);

        // Stop moving if already far enough
        if (distance >= safeDistance) return;

        Vector3 direction = (transform.position - target.position).normalized;
        transform.position += direction * speed * Time.deltaTime;
    }
}

```
### Output:


<img width="1918" height="1198" alt="ex4_1" src="https://github.com/user-attachments/assets/27b7d629-6331-4355-9508-ca28575f055a" />


<img width="1918" height="1198" alt="ex4_2" src="https://github.com/user-attachments/assets/ed84c028-ab93-4572-8d7d-522c8c25ef77" />



<img width="1918" height="1198" alt="ex4_3" src="https://github.com/user-attachments/assets/e678ea96-6aa4-4e46-b072-bf91e63298b2" />


### Result:
Thus the simple seek behavior was implemented successfully.
