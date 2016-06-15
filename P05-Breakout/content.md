Now we understand how the board is built, let’s look at how the block
and deathZone work:

The Deathzone is the spot below the paddle, so if you miss the ball you
die.

In DeathZone.cs you will find this method:

```
public void OnCollisionEnter(Collision collisionWith)
	{
		//if anything collides with this object that has this script let’s check if it has the ball tag?
		if(collisionWith.gameObject.tag == "Ball")
		{
			//oh it does, so we are going to reset the ball back to kinematic, this snaps it back to the paddle.
			Rigidbody ballBody = collisionWith.gameObject.GetComponent<Rigidbody>();
			ballBody.isKinematic = true;
		}
	}
```

Every block has Block.cs attached to it.

Block.cs has some similar code:
```
//Destroy a block when the ball hits it, and make a nice shiny explosion
effect.

//Destroy a block when the ball hits it, and make a nice shiny explosion effect.
	public void OnCollisionEnter(Collision collisionWith)
	{
		//if anything collides with this block lets see if it has the ball tag?
		if(collisionWith.gameObject.tag == "Ball")
		{
			//This Destroy method destroys an explosion 0.5 seconds after it is created with Instantiate
			Destroy((GameObject)Instantiate(explosionEffect, collisionWith.gameObject.transform.position, collisionWith.gameObject.transform.rotation), 0.5f);

			//This destroy destroys the block.
			Destroy(this.gameObject);
		}
	}
```
