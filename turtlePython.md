# PythonProgram
//this program create any shape/logo/object you want in python and turtle.

import turtle

t = turtle.Turtle()
t.fillcolor("blue")
t.begin_fill()
for i in range(5):
    t.forward(100)
    t.right(144)
    t.forward(100)
    t.left(72)
    
t.end_fill()
t.pencolor("red")
t.penup()
t.goto(0,0)
t.write("*", align="center", font=("Arial", 50, "bold"))
t.hideturtle()
turtle.exitonclick()


