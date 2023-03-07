
--- question ---

---
legend: Question 3 of 3
---

Which code would you use if you wanted a game to move the player back to the start position without changing the rest of the game?

--- choices ---

- ( ) 

--- code ---
---
language: cs 
filename: Reset.cs 
line_numbers: true 
line_number_start: 1 
line_highlights: 
---

public class Reset : MonoBehaviour
{
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

  --- feedback ---

  That's not correct. This code will send the player back to the start position but it will also reset other GameObjects in the scene. 

  --- /feedback ---

- (x) 

   
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

public class Reset : MonoBehaviour
{
    Rigidbody rb;
    Vector3 spawnPoint;

    // Start is called before the first frame update
    void Start()
    {
        spawnPoint = transform.position;
    }

    // Update is called once per frame
    void Update()
    {

        if (this.transform.position.y < -10)
       {
           rb.velocity = Vector3.zero;
           transform.position = spawnPoint;
       }
    }
}

--- /code ---

  --- feedback ---

That's correct. This code will move the player back to the starting position without changing anything else in the scene. 

  --- /feedback ---


--- /choices ---

--- /question ---
