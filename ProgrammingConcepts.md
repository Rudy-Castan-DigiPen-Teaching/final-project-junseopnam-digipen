Programming Concepts
====================
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
