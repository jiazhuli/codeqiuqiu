# codeqiuqiu
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class pigg : MonoBehaviour

  

{

    private bool canbig;
    public int body = 10;
    // Start is called before the first frame update
    void Start()
    {
        canbig = true;
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    void OnTriggerEnter2D(Collider2D other)
    {
        //Check the provided Collider2D parameter other to see if it is tagged "PickUp", if it is...
        if (other.gameObject.CompareTag("pig"))
        {
            Debug.Log(body);
            Destroy(other.gameObject);
            body += 1;
            big();
        }
    }

    void big()
    {
        if (canbig)
        {
            transform.localScale += new Vector3(0.06f, 0.06f, 0.06f);
        }
        if (body == 25)
        {
            canbig = false;
        }
    }
}
