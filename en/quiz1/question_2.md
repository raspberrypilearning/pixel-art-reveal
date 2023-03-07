
--- question ---

---
legend: Question 2 of 3
---

You are designing a game that has a 'TileController' script with the following code:


--- code ---
---
language: cs 
filename: TileController.cs 
line_numbers: true 
line_number_start: 1 
line_highlights: 
---

public class TileController : MonoBehaviour
{
  public Material start;
  public Material reveal;
  Renderer rend;

  // Start is called before the first frame update
  void Start()
  {
      rend = GetComponent<Renderer>();
      rend.sharedMaterial = reveal;
  }

  void OnCollisionEnter(Collision collision)
  {
      if (collision.gameObject.tag == "Player"){
          rend.sharedMaterial = start;
      }
  }

}

--- /code ---

There's a bug which means that the tiles are not changing colour correctly.

Which lines of code would you need to fix to make the Tile change from the `start` material to the `reveal` material when an object with the 'Player' tag collides with the tile?

--- choices ---

- ( ) 

Lines 14 and 15

  --- feedback ---

Not quite. Look for the lines that change the `sharedMaterial` of the Renderer component. 

  --- /feedback ---

- ( ) 

Line 21

  --- feedback ---

Not quite. Look for the lines that change the `sharedMaterial` of the Renderer component. 

  --- /feedback ---

- ( ) 

Lines 14, 15 and 21

  --- feedback ---

Not quite. Look for the lines that change the `sharedMaterial` of the Renderer component. 

  --- /feedback ---

- (x)

Lines 15 and 21

  --- feedback ---

That's correct. These lines are the wrong way around! You need to use the `start` material in `Start` and the `reveal` material in `OnCollisionEnter`.

  --- /feedback ---

--- /choices ---

--- /question ---
