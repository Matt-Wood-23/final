# First Steps
To begin, you will need to have **Unity Hub and a Unity Editor installed** as well as iOS or Android support from [Unity's Website](https://unity3d.com/get-unity/download).<br>
1. Create a new 3D project inside of Unity Hub
2. Once it is ready, right-click inside your hierarchy underneath your Main Camera and Directional Light, or use the tab at the top of the screen that says GameObject, go down to 3D Object and choose Sphere from the dropdown
3. Now, you will want to create a script for movement. Go into the Sphere's inspector, click add component, and then click new script and call it Movement.<br> 
```
  using System.Collections;
  using System.Collections.Generic;
  using UnityEngine;

  public class Movement : MonoBehaviour
  {
    float mousePosx;
    float mousePosy;
    
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        //Find mouse position
        mousePosx = Input.mousePosition.x;
        mousePosy = Input.mousePosition.y;

        //Convert mouse position to world position
        Vector3 worldPos = Camera.main.ScreenToWorldPoint(new Vector3(mousePosx, mousePosy, 10));

        //Set sphere's position to mouse position
        transform.position = new Vector3(worldPos.x, worldPos.y, 0);
    }
}
```
4. Now save your code and go back to Unity. Push play at the top, you will see that if you move your mouse over the game window, the sphere tracks to your mouse.
