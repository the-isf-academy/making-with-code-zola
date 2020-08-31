---
title: 3. Loops and Conditionals
type: labs
resources:
- name: Scratch loop
  src: images/courses/cs9/unit00/00_loops_scratch_loop.png
- name: Turtle loop
  src: images/courses/cs9/unit00/00_loops_turtle_loop.png
- name: Turtle var
  src: images/courses/cs9/unit00/00_loops_turtle_var.png
---

# Loops and Conditionals

from turtle import *

# USER INPUT 0 (starter) (add a shape)
# speed(10)
# drawing = input("What would you like me to draw? ")
# size = int(input("How big should I draw it? "))
# if drawing == "square":
    # for i in range(4):
        # forward(size)
        # right(90)
# elif drawing == "circle":
    # circle(size)
# else:
    # print("Sorry, I don't know how to draw that...")

# USER INPUT 1 (while true/break)
# speed(10)
# while True:
    # drawing = input("What would you like me to draw? ")
    # size = int(input("How big should I draw it? "))
    # if drawing == "square":
        # for i in range(4):
            # forward(size)
            # right(90)
    # elif drawing == "circle":
        # circle(size)
    # elif drawing == "quit":
        # break
    # else:
        # print("Sorry, I don't know how to draw that...")

# USER INPUT 2 (clear)
# speed(10)
# while True:
    # drawing = input("What would you like me to draw? ")
    # if drawing == "clear":
        # clear()
    # elif drawing == "quit":
        # break
    # else:
        # size = int(input("How big should I draw it? "))
        # if drawing == "square":
            # for i in range(4):
                # forward(size)
                # right(90)
        # elif drawing == "circle":
            # circle(size)
        # else:
            # print("Sorry, I don't know how to draw that...")

# RAINBOW (STARTER)
# speed(10)
# for i in range(5):
    # color("red")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("orange")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("yellow")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("green")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("blue")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("purple")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()
    # color("violet")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()


# RAINBOW (SOLUTION)
# speed(10)
# for i in range(50):
    # if i%7 == 0:
        # color("red")
    # elif i%7 == 1:
        # color("orange")
    # elif i%7 == 2:
        # color("yellow")
    # elif i%7 == 3:
        # color("green")
    # elif i%7 == 4:
        # color("blue")
    # elif i%7 == 5:
        # color("purple")
    # elif i%7 == 6:
        # color("violet")
    # begin_fill()
    # for j in range(4):
        # forward(100)
        # right(90)
    # end_fill()
    # penup()
    # right(45)
    # forward(10)
    # left(45)
    # pendown()


# HAILSTONE
# num = int(input("What number should I calculate the hailstone sequence of? "))
# count = 0
# while num != 1:
    # if num % 2 == 0:
        # num = int(num/2)
    # else:
        # num = int(num*3+1)
    # print(num)
    # count += 1
# print("Took " + str(count) + " steps to reach 1.")

# DRAWING HAILSTONE (LINEAR)
# speed(10)
# left(90)
# num = int(input("What number should  I draw the hailstone sequence of? "))
# original_num = num
# count = 0
# while num != 1:
    # if num % 2 == 0:
        # num = int(num/2)
    # else:
        # num = int(num*3+1)
    # count += 1
    # print(num)
    # forward(num)
    # back(num)
    # right(90)
    # forward(5)
    # left(90)


# DRAWING HAILSTONE (ROUND)
# speed(10)
# num = int(input("What number should  I draw the hailstone sequence of? "))
# original_num = num
# count = 0
# while num != 1:
    # if num % 2 == 0:
        # num = int(num/2)
    # else:
        # num = int(num*3+1)
    # count += 1
# num = original_num
# while num != 1:
    # if num % 2 == 0:
        # num = int(num/2)
    # else:
        # num = int(num*3+1)
    # print(num)
    # forward(num*0.2)
    # back(num*0.2)
    # right(360/count)
# print("Took " + str(count) + " steps to reach 1.")

# DRAWING HAILSTONE (FALLING)
# speed(10)

num = int(input("What number should I draw the hailstone sequence of? "))
penup()
goto(0, -300+num)
pendown()
count = 0
while num != 1:
    prev_num = num
    if num % 2 == 0:
        num = int(num/2)
        setheading(225)
    else:
        num = int(num*3+1)
        setheading(45)
    count += 1
    print(num)
    circle(abs(prev_num-num)/2, 180)
print("Took " + str(count) + " steps to reach 1.")
penup()
goto(0,-300)

# DRAWING HAILSTONE COMPARING STEPS 0
# left(90)
# speed(10)
# for i in range(1,100):
    # num = i
    # count = 0
    # while num != 1:
        # if num%2 == 0:
            # num = int(num/2)
        # else:
            # num = int(num*3 + 1)
        # count += 1
    # print(str(i) + " took " + str(count) + " steps to reach 1.")
    # forward(count)
    # back(count)
    # right(90)
    # forward(3)
    # left(90)

# DRAWING HAILSTONE COMPARING STEPS 1
# speed(10)
# for i in range(1,100):
    # num = i
    # count = 0
    # while num != 1:
        # if num%2 == 0:
            # num = int(num/2)
        # else:
            # num = int(num*3 + 1)
        # count += 1
    # print(str(i) + " took " + str(count) + " steps to reach 1.")
    # forward(count)
    # back(count)
    # right(360/100)

# DRAWING HAILSTONE COMPARING STEPS 2
# speed(10)
# for i in range(1,100):
    # num = i
    # count = 0
    # while num != 1:
        # if num%2 == 0:
            # num = int(num/2)
        # else:
            # num = int(num*3 + 1)
        # count += 1
    # print(str(i) + " took " + str(count) + " steps to reach 1.")
    # circle(count, 180)
    # penup()
    # circle(count, 180)
    # pendown()
    # right(360/100)

input()

