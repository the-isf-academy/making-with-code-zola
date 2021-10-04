---
title: 4. Elevator
type: checkup
---

# Elevator

{{< code-action "Create a new file in your" >}} `do_now` **folder.**
```shell
cd Desktop/cs9/unit_00/
cd do_now
atom donow4.py
```


{{< code-action "The code block below has a number of errors. Your goal is fix them all." >}} Start by copying and pasting the code into your `donow4.py` file. 
> Consider both **programmatic** erros and **syntax** errors. 
>
> {{< columns >}}
**Programmatic error:** when the program does something different than what you wanted. 

<--->

**Syntax error:** when the program crashes because the program cannot be understood by the computer.

{{< /columns >}}


```python 
#############
# donow4.py
#############

def elevator_movement(start_floor,end_floor):
    floor_difference = abs(start-end)

    if start > end:
        print('\nGOING DOWN')

        for i in range(1,floor_difference+1):
            print('  [Floor {}]'.format(start-i))

    else:
        print('\nGOING UP')

        for i in range(1,floor_difference+1):
            print('  [Floor {}]'.format(start+i))

    print('YOU HAVE ARRIVED!')

def elevator_menu():
    print('-- WELCOME TO THE ELEVATOR --')

    print('Enter starting floor.')
    start = input('  > ')

    print('Enter destination floor')
    end = input('  > ')

    elevator_movement(start,end)

elevator_menu()
```

{{< write-action "In your notebook, write down the following:"  >}}
- What was 1 programmatic error and how did you fix it?
- What was 1 syntax error and how did you fix it?





{{< expand "Here is an example of the program running correctly." >}}
```shell
-- WELCOME TO THE ELEVATOR --
Enter starting floor.
  > 9
Enter destination floor
  > 15

GOING UP
  [Floor 10]
  [Floor 11]
  [Floor 12]
  [Floor 13]
  [Floor 14]
  [Floor 15]
YOU HAVE ARRIVED!
```
{{< /expand >}}