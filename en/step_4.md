## Reveal the art

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will add a ball that uncovers the pixel art as it rolls.
</div>
<div>
![Step Three Output.](images/step-three-output.png){:width="350px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
The word <span style="color: #0faeb0">"pixel" stands for "picture element".</span> The first record of the word is in a research paper by Frederic C. Billingsley in 1965 when refering to images of the Moon and Mars. He did not claim to invent the word and it is unclear exactly when it was first used.
</p>

### Add a ball

--- task ---

Create a sphere and name it 'Player1'.

**Reset** the 'Transform'.

--- /task ---

--- task ---

**Choose** a size for your ball by changing the 'Transform Scale' properties.

--- /task ---

--- task ---

Position the sphere where you want it to start. 

--- /task ---

--- task ---

Choose a material and drag it on to the sphere in the Scene view.

![A strip of images showing the different ball options. The first is a large mirror ball. The second is a small ball with GlossBlack material. The third has a purple marble effect. The fourth has a beetle pattern effect.](images/ball-examples.png)

--- /task ---

--- task ---

Tag the sphere 'Player'.

--- /task ---

--- task ---

Add a RigidBody to the Player.

[[[unity-rigidbody]]]

Create a 'PlayerController' script to your sphere and set it up to use the keys of your choice. 

[[[unity-control-ball]]]
[[[unity-keyboard-conventions]]]

--- /task ---

### Set up your camera view

--- task ---

Changed your camera rotation to X = `85` so that it looks down on the art but with depth. 

![The Game view with camera rotation applied so the tile floor is all visible but angled slightly away from the camera.](images/camera-rotation.png)

--- /task ---

--- task ---

**Test** your project by pressing 'Play'. You should be able to move your player using the chosen keys on your keyboard.

<video width="640" height="360" controls preload="none" poster="images/ball-move.png">
<source src="images/ball-move.mp4" type="video/mp4">
Your browser does not support WebM video, try FireFox or Chrome.
</video>

--- /task ---

### Reset the art

--- task ---

Add a reset option to reload your scene. This will position the ball at the start position and cover up the pixel art.

**Choose:** You can add a reset button or reset the game when the player Y position is below the floor.

[[[unity-text-meshpro]]]

[[[unity-add-position-text]]]

[[[unity-reset-button]]]

--- collapse ---
---
title: Add code to reset the ball and tiles if the ball is below the floor
---

Create a new `Reset` script on the ball:

--- code ---
---
language: cs 
filename: Reset.cs 
line_numbers: true 
line_number_start: 1 
line_highlights: 
---
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;
public class Reset : MonoBehaviour
{

    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
       if (this.transform.position.y < -10)
       {
           SceneManager.LoadScene(SceneManager.GetActiveScene().name);
       }
    }
}

--- /code ---

--- /collapse ---

--- /task ---

--- task ---

**Test:** Play your game. After you have revealed some of your artwork, click on your reset button or deliberately fall off your pixel art platform to check that the ball and tiles reset. 

<video width="640" height="360" controls preload="none" poster="images/reset-ball.png">
<source src="images/reset-ball.mp4" type="video/mp4">
Your browser does not support WebM video, try FireFox or Chrome.
</video>

--- /task ---

