---
title: 0. Planet Gravity
type: checkup
---
# Do Now

Welcome back from break! To get started with Unit 01, let's do a little review.

{{< code-action "First, navigate to your cs9 folder, and create a" >}} `unit_01` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
mkdir unit_01
cd unit_01
```

{{< code-action "Create a new document" >}}
```shell
atom donow0.py
```


## Calculate your space weight

Did you know your weight varies based on which planet you're on? This due the different gravitional pulls on each planet. 

{{< code-action "Create a program that will calculate your weight on different planets." >}}Your program must include:
> - a function with 2 paramters
> - user input

Use the table below to reference different planets' relative weight. 

| Planet  | Multiple of Earth's Gravity |
|---------|-----------------------------|
| Moon    | 0.166                       |
| Sun     | 27.01                       |
| Mars    | 0.38                        |
| Jupiter | 2.34                        |
| Mercury | 0.38                        |



#### Your program should run like so:
```shell
How much do you weight (kgs)? 100
Enter a planet (moon, mars): mars
----------
On mars you would weight 38.0 kg
```

