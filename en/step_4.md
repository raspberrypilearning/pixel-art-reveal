## Reveal the art

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will add a ball that uncovers the pixel art as it rolls.
</div>
<div>
![Step Four Output.](images/step-four-output.png){:width="350px"}
</div>
</div>

### Add a ball

--- task ---

Create a sphere and name it 'Player1'.

--- /task ---


--- task ---

Position the sphere where you want it to start. 

--- /task ---


--- task ---

Choose a material for the player and drag it on to the sphere in the Scene view.

--- /task ---

--- task ---

Tag the sphere 'Player'.

--- /task ---


--- task ---

Add a 'PlayerController' script to your sphere and set it up to use the keys of your choice. 

--- collapse ---
---
title: Roll a ball with keys
---

+ Add the RigidBody component to the 'Player1' GameObject.

+ Add a new script called 'PlayerController' to the 'Player1' GameObject:

--- code ---
---
language: cs 
filename: PlayerController.cs 
line_numbers: true 
line_number_start: 1 
line_highlights: 
---

using System.Collections; using System.Collections.Generic; using UnityEngine;

public class PlayerController : MonoBehaviour { 
    public Transform cameraTransform; 
    public string forwardKey; 
    public string leftKey; 
    public string backwardKey; 
    public string rightKey; 
    Rigidbody rb;

// Start is called before the first frame update
void Start()
{
    rb = this.GetComponent<Rigidbody>();
    rb.transform.forward = cameraTransform.forward;
}

// FixedUpdate is called once per fixed frame-rate frame
void FixedUpdate()
{
    // Calculates cameraTransform.forward without the y value so the ball doesn't move up and down on the Y axis
    Vector3 forward = new Vector3(cameraTransform.forward.x, 0, cameraTransform.forward.z).normalized;
    Vector3 right = Quaternion.AngleAxis(90, Vector3.up) * forward;
    Vector3 left = -right;
    Vector3 backward = -forward;

    if (Input.GetKey(forwardKey))
    {
        rb.AddForce(forward * 10f);
    }

    if (Input.GetKey(rightKey))
    {
        rb.AddForce(right * 5f);
    }

    if (Input.GetKey(backwardKey))
    {
        rb.AddForce(backward * 2f);
    }

    if (Input.GetKey(leftKey))
    {
        rb.AddForce(left * 5f);
    }
}
}

--- /code ---

+ Select the 'Player1' GameObject to view the 'Inspector' options.

+ Drag the 'Main Camera' game object to the 'Camera Transform' variable in the 'Inspector'. 

+ Set the 'Forward Key', 'Left Key', 'Backward Key', and 'Right Key' to the lowercase letters that you want to use to control Player1. We used 'w', 'a', 's' and 'd'.

![The inspector for Player1 showing the PlayerController script with Camera Transform set to Main Camera and four key variables set to lowercase w, a, s and d.](images/player1-settings.png)

**Tip:** The letters for the keys need to be in lower case. 

--- /collapse ---

--- /task ---

### Reset the art

--- task ---



--- /task ---