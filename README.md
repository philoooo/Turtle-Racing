<h1 align="center"> Turtle Racing </h1>


<div align="center">
<img src="https://github.com/philoooo/Turtle-Racing/blob/main/Screenshot%202025-11-01%20at%209.38.37%20PM.png" width="400" >
</div>

<h1></h1>

I created a turtle racing game. The user is prompted to select a turtle color to bet on. The speeds of all 6 turtles are randomized. Whichever turtle passes by the finish line at the selected coordinate system is crowned the winner!

<h1></h1>

```
import random
from turtle import Turtle, Screen


is_race_on = False
screen = Screen()
screen.setup(width=500,height=400)
user_bet = screen.textinput(title="Make your bet", prompt="Which turtle will win the race? Enter a color: ")
colors = ['red', 'orange', 'purple', 'green', 'blue', 'pink']
y_positions = [-70, -40, -10, 20, 50, 80]
all_turtles = []

for turtle_index in range(0, 6):
    new_turtle = Turtle(shape="turtle")
    new_turtle.color(colors[turtle_index])
    new_turtle.penup()
    new_turtle.goto(x=-230, y=y_positions[turtle_index])
    all_turtles.append(new_turtle)

if user_bet:
    is_race_on = True

while is_race_on:

    for turtle in all_turtles:
        if turtle.xcor() > 230:
            is_race_on = False
            winning_color = turtle.pencolor()
            if winning_color == user_bet:
                print(f"You've won! The {winning_color} turtle is the winner!")
            else:
                print(f"You lost. The {winning_color} turtle is the winner")
        rand_distance = random.randint(0,10)
        turtle.forward(rand_distance)

```
