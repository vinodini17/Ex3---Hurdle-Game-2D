# <p align="center">Hurdle Game - 2D</p>

## AIM:
To develop a 2D game using C# program in Unity.

## ALGORITHM:
Step 1: Create a new project.

Step 2: Click Content browser -> Drag the file into Unity -> Place the assets inside the viewport in Unity.

Step 3: Define the physics properties of the objects such as the collider.

Step 4: Assets -> Create -> # Script.

Step 5: Create a Coding folder and create a C# file to add the coding.

Step 6: To add our C# Script file to our selected object, click on the C# Script file drag it to our selected objects in the Hierarchy window and run the application.

Step 7: Stop.

## PROGRAM:
### Player.cs
```cs
using System.Collections;
using System.Collections.Generic;
using System.Security.Cryptography;
using UnityEngine;
using UnityEngine.SocialPlatforms.Impl;

public class player : MonoBehaviour
{
    public float speed;
    public float jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(moveinp, 0, 0) * speed * Time.deltaTime;
        if (Input.GetKeyDown(KeyCode.Space) &&Mathf.Abs(rb.velocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    { 
        if(other.CompareTag("Destroy"))
        {
            //cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}
```
### Score.cs

```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
public class Score : MonoBehaviour
{
    public int coincount;
    public Text value;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        value.text = coincount.ToString();
    }
}
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/6f96994f-e2c4-41b9-832e-ccc5891c368e)
![image](https://github.com/user-attachments/assets/ecf74f15-1e34-4056-86d7-5dd65108afe8)

## RESULT:
Thus a 2D game using the C# program in Unity is developed successfully.
