# Ex.No: 3  Basic movements in Unity 
### DATE: 30/01/2026                                                                          
### REGISTER NUMBER : 212224040316
### AIM: 
 To learn the basic movements translation,scaling and rotation of game objects through code.
### Procedure:
1. Setup the Scene
2. Open Unity and create a 3D Scene.
3. Add three objects:Cube → Rename to Object1 (for movement),Sphere → Rename to Object2 (for rotation).Capsule → Rename to Object3 (for scaling).
4. Add the Script,Create a C# Script → Name it TransformOperations.cs.
5. Write the code for translation,scaling and rotation,save and close the script
6. Save the script
7. Select any empty GameObject (or create one: GameObject → Create Empty).
8. Attach the TransformOperations script to it.
9. In the Inspector, assign Object1 → Drag the Cube,Object2 → Drag the Sphere.Object3 → Drag the Capsule.
10. Run the Scene Press Play ▶️ in Unity
11. Stop the program.
### Program 
```csharp
using UnityEngine;

public class TransformOperations : MonoBehaviour
{
    public Transform object1; // Move
    public Transform object2; // Rotate
    public Transform object3; // Scale

    // Stop values
    public float maxMoveX = 5f;
    public float maxRotateY = 90f;
    public float maxScale = 2f;

    void Update()
    {
        // Move object1 on X-axis (STOP at maxMoveX)
        if (object1 != null && object1.position.x < maxMoveX)
        {
            object1.Translate(0.02f, 0f, 0f);
        }

        // Rotate object2 on Y-axis (STOP at maxRotateY)
        if (object2 != null && object2.rotation.eulerAngles.y < maxRotateY)
        {
            object2.Rotate(0f, 0.5f, 0f);
        }

        // Scale object3 (STOP at maxScale)
        if (object3 != null && object3.localScale.x < maxScale)
        {
            object3.localScale += new Vector3(0.02f, 0.02f, 0.02f);
        }
    }
}

```
### Output:



<img width="1918" height="1142" alt="Screenshot 2026-02-03 100753" src="https://github.com/user-attachments/assets/6143f835-1559-4fc7-b9a3-37fe1411eae8" />


<img width="1918" height="1198" alt="Screenshot 2026-02-03 101011" src="https://github.com/user-attachments/assets/869190f4-8ea6-4b04-b1d5-3f0b342db48f" />



### Result:
Thus the basic movement is learned through scripting


