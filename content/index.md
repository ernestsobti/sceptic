---
title: index
---
## Chow Chow Fuckers 

> [!info]- This is Python Code for snake Game
> ```python
> import turtle
> import time
> import random
> 
> delay = 0.1
> score = 0
> high_score = 0
> 
> # Set up the screen
> wn = turtle.Screen()
> wn.title("Snake Game")
> wn.bgcolor("#1e1e1e")
> wn.setup(width=600, height=600)
> wn.tracer(0)  # Turns off automatic screen updates
> 
> # Snake head
> head = turtle.Turtle()
> head.speed(0)
> head.shape("square")
> head.color("#4caf50")
> head.penup()
> head.goto(0, 0)
> head.direction = "stop"
> 
> # Snake food
> food = turtle.Turtle()
> food.speed(0)
> food.shape("circle")
> food.color("#ff5252")
> food.penup()
> food.goto(0, 100)
> 
> segments = []
> 
> # Scoreboard
> pen = turtle.Turtle()
> pen.speed(0)
> pen.shape("square")
> pen.color("white")
> pen.penup()
> pen.hideturtle()
> pen.goto(0, 260)
> pen.write("Score: 0  High Score: 0", align="center", font=("Courier", 20, "normal"))
> 
> # Movement functions
> def go_up():
>     if head.direction != "down":
>         head.direction = "up"
> 
> def go_down():
>     if head.direction != "up":
>         head.direction = "down"
> 
> def go_left():
>     if head.direction != "right":
>         head.direction = "left"
> 
> def go_right():
>     if head.direction != "left":
>         head.direction = "right"
> 
> def move():
>     if head.direction == "up":
>         head.sety(head.ycor() + 20)
>     if head.direction == "down":
>         head.sety(head.ycor() - 20)
>     if head.direction == "left":
>         head.setx(head.xcor() - 20)
>     if head.direction == "right":
>         head.setx(head.xcor() + 20)
> 
> def reset_game():
>     global score, delay
>     time.sleep(1)
>     head.goto(0, 0)
>     head.direction = "stop"
> 
>     # Hide the segments off-screen and clear the list
>     for segment in segments:
>         segment.goto(1000, 1000)
>     segments.clear()
> 
>     score = 0
>     delay = 0.1
>     pen.clear()
>     pen.write(f"Score: {score}  High Score: {high_score}", align="center", font=("Courier", 20, "normal"))
> 
> # Keyboard bindings (Supports both Arrow Keys and WASD)
> wn.listen()
> wn.onkeypress(go_up, "Up")
> wn.onkeypress(go_down, "Down")
> wn.onkeypress(go_left, "Left")
> wn.onkeypress(go_right, "Right")
> wn.onkeypress(go_up, "w")
> wn.onkeypress(go_down, "s")
> wn.onkeypress(go_left, "a")
> wn.onkeypress(go_right, "d")
> 
> # Main game loop
> try:
>     while True:
>         wn.update()
> 
>         # Check for collision with the border
>         if head.xcor() > 290 or head.xcor() < -290 or head.ycor() > 290 or head.ycor() < -290:
>             reset_game()
> 
>         # Check for collision with food
>         if head.distance(food) < 20:
>             # Move food to a random grid-aligned spot
>             x = random.randint(-14, 14) * 20
>             y = random.randint(-14, 14) * 20
>             food.goto(x, y)
> 
>             # Add a new body segment
>             new_segment = turtle.Turtle()
>             new_segment.speed(0)
>             new_segment.shape("square")
>             new_segment.color("#81c784")
>             new_segment.penup()
>             segments.append(new_segment)
> 
>             # Slightly increase speed and update score
>             delay = max(0.04, delay - 0.002)
>             score += 10
>             if score > high_score:
>                 high_score = score
> 
>             pen.clear()
>             pen.write(f"Score: {score}  High Score: {high_score}", align="center", font=("Courier", 20, "normal"))
> 
>         # Move the end segments first in reverse order
>         for index in range(len(segments) - 1, 0, -1):
>             x = segments[index - 1].xcor()
>             y = segments[index - 1].ycor()
>             segments[index].goto(x, y)
> 
>         # Move segment 0 to where the head is
>         if len(segments) > 0:
>             segments[0].goto(head.xcor(), head.ycor())
> 
>         move()
> 
>         # Check for head collision with body segments
>         for segment in segments:
>             if segment.distance(head) < 20:
>                 reset_game()
> 
>         time.sleep(delay)
> except turtle.Terminator:
>     pass
> 
> 
> ```




```base
filters:
  and:
    - file.name == "File Name"
views:
  - type: table
    name: View

```


![[FT US (6)_ocred.pdf]]