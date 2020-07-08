Programming Concepts
====================
Too many, so I'll shorten it down to a few examples of important use!

Shapes
------
what?

I used circle() to draw the character and Boss's eyes.
This is the most important.

How

character
<pre>
<code>
    push()
    fill(character_color);
    circle(this.x, this.y, this.size);
    fill('white')
    circle(this.x - 6, this.y- 5, this.size/3)
    fill('black')
    circle(this.x - 6, this.y- 7, 5)
    fill('white')
    circle(this.x + 6, this.y- 5, this.size/3)
    fill('black')
    circle(this.x + 6, this.y- 7, 5)
    pop();
</code>
</pre>

Boss
<pre>
<code>
    let p = float(count % frame) / frame
    count++
    this.move_x1.Set(p * TWO_PI);
    this.move_x2.Set(p * TWO_PI);
    this.move_y.Set(p * TWO_PI);
    push()
    fill('white')
    line(100, 100, 100, 50)
    line(width - 100, 100, width - 100, 50)
    circle(width - 100, 100, 50)
    circle(100, 100, 50)
    fill('black')
    circle(this.move_x1.value(), this.move_y.value(),30)
    circle(this.move_x2.value(), this.move_y.value(),30)
    pop()
</code>
</pre>

Why?

Because the noiseloop can make that eyes pretty enough

color
-----
What?

Used to make the color change when the mouse hovers over the rect of the option.

How?
<pre>
<code>
if (mouseX > this.x + 25 && mouseX < this.x + 75 && mouseY > this.y - this.plus * 3 - 15 && mouseY < this.y - this.plus * 3 + 15) {
      this.color = 'red'
      push()
      fill(this.color);
      rect(this.x + this.plus, this.y - this.plus * 3, this.width - this.plus, this.height)
      image(Left1, this.x + this.plus, this.y - this.plus * 3, this.width, this.height)
      pop()
      if (mouseIsPressed) {
        image(Left2, this.x + this.plus, this.y - this.plus * 3, this.width, this.height)
        character_color = 'skyblue'
      }
    } else {
      push()
      this.color = 'yellow'
      fill(this.color);
      rect(this.x + this.plus, this.y - this.plus * 3, this.width - this.plus, this.height)
      image(Left1, this.x + this.plus, this.y - this.plus * 3, this.width, this.height)
      pop()
    }
</code>
</pre>    

Why?

Used to indicate where the player can click the mouse in the options.

Variables
---------
> what?

x,y coordinates of most objects

how? (ex)
<pre>
<code>
class Obstacle1 {
  constructor() {
    this.x = random(30, 770);
    this.y = 0;
    this.r = 100;
  }
</code>
</pre>  

why?
The object was moved using coordinate variables.


> what?

Character color

how?
<pre>
<code>
let character_color = 'skyblue'
</code>
</pre>  

why?

To change the color in options


> what?

Character and boss health

how?
<pre>
<code>
this.B_life = 200;
this.character_life = 100;
</code>
</pre>  

why?

To judge whether the game is clear or failed

Conditional Statements
----------------------
what?

Player and obstacle hit decisions, Bullet and boss hit decisions.

how?

Player and obstacle hit decisions.
<pre>
<code>
if (dist(this.Hero.x, this.Hero.y, this.ball1.Ball_x, this.ball1.Ball_y) <= 40) {
        this.character_life = this.character_life - 1
        hit_sound.play();
      }
</code>
</pre> 

Bullet and boss hit decisions.

<pre>
<code>
if (round(this.Bullet[i].ypos) == 50 || round(this.Bullet[i].ypos) == 49 || round(this.Bullet[i].ypos) == 48 || round(this.Bullet[i].ypos) == 47 || round(this.Bullet[i].ypos) == 46) {
        this.Bullet[i].hit = true;
      }
      if (this.Bullet[i].hit == true) {
        this.B_life = this.B_life - 1
        this.Bullet[i].hit = false
      }
</code>
</pre> 

why?

Due to the hit judgment, the blood of characters and bosses is reduced.

Loops
-----
what?

It increase the length of the bullet array

how?
<pre>
<code>
for (var i = 0; i < this.Bullet.length; i++) {}
</code>
</pre> 

why?

Increases the size of the bullet array, allowing the bullet to continue firing.

Functions
---------
what?

Makes the stone fall.

how?
<pre>
<code>
function Draw_obstacle1() {
  let obstacle1 = [];

  let i = 0;
  for (let i = 0; i < 150; i++) {
    obstacle1[i] = new Obstacle1(this.x, this.y, this.r)
  }
  obstacle.show()
  obstacle.fly()
}
</code>
</pre> 

why?

To make it easier to draw a stone fall into another class
