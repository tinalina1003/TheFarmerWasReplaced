<h1>The Farmer Was Replaced</h1>

<h3><u>Trees</u></h3>
Trees are a better way to get wood than bushes. They give 5 wood each. Like bushes, they can be planted on grass or soil.

Trees like to have some space and planting them right next to each other will slow down their growth. The growing time is doubled for each tree that is on a tile directly to the north, east, west or south of it. So if you plant trees on every tile, they will take 2*2*2*2 = 16 times longer to grow. The % operator can be useful here. Remember that the % operator returns the remainder of the division. Even numbers divided by 2 have a remainder of 0 and odd numbers divided by 2 have a remainder of 1.
So you can check if a number is even like this:

def is_even(n):
	return n % 2 == 0

This returns True if n is even and False if it isn't.



<h3>Carrots</h3>

Before you can plant carrots with plant(Entities.Carrot), you have to till the soil. This will change the ground to Grounds.Soil. To till the soil, simply call till(). Calling till() again will change it back to Grounds.Grassland.

Planting carrots costs wood and hay. These items will be automatically removed when calling plant(Entities.Carrot).

You can see the cost of any plant on its own page.


<h3>Pumpkins</h3>

Pumpkin grow like carrots on tilled soil. Planting them costs carrots.

When all the pumpkins in a square are fully grown, they will grow together to form a giant pumpkin. Unfortunately, pumpkins have a 20% chance of dying once they are fully grown, so you will need to replant the dead ones if you want them to merge. 

When a pumpkin dies, it leaves behind a dead pumpkin that won't drop anything when harvested. Planting a new plant in its place automatically removes the dead pumpkin, so there is no need to harvest it. can_harvest() always returns False on dead pumpkins.

The yield of a giant pumpkin depends on the size of the pumpkin.

A 1x1 pumpkin yields 1*1*1 = 1 pumpkins.
A 2x2 pumpkin yields 2*2*2 = 8 pumpkins instead of 4.
A 3x3 pumpkin yields 3*3*3 = 27 pumpkins instead of 9.
A 4x4 pumpkin yields 4*4*4 = 64 pumpkins instead of 16.
A 5x5 pumpkin yields 5*5*5 = 125 pumpkins instead of 25.
A nxn pumpkin yields n*n*6 pumpkins for n >= 6.

It's a good idea to get at least 6x6 size pumpkins to get the full multiplier. 

This means that even if you plant a pumpkin on every tile in a square, one of the pumpkins may die and prevent the mega pumpkin from growing.
