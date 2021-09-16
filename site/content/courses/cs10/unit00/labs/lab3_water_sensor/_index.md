---
Title: 2. Water Quality
# draft: true
---

# Water Quality Sensors

In this lab you will act as an aquarium monitoring system using water quality sensors and Raspberry Pis.

In pairs, you are responsible for writing a program that utilizies the provided sensor to collect water quality information over the course of 24 hours.

Each group will monitor `Dissolved Oxygen`, `PH`, or `Conductivity` for both the fish tank on A4 and a control tank in A403.

We will then compile and share the data with the ISF science faculty.


## [0] Setup

Let's start by taking a look at the sensors. There are three available sensors, each with its own data sheet. A data sheet is an informational document provided by the manufacturer with details of the performance and properties of a product.

- [Dissolved Oxygen Sensor](https://files.atlas-scientific.com/DO_EZO_Datasheet.pdf)
- [PH Sensor](https://files.atlas-scientific.com/pH_EZO_Datasheet.pdf)
- [Conductivity Sensor](https://files.atlas-scientific.com/EC_EZO_Datasheet.pdf)


**Each kit should have:**
- 1  sensor
- 1 EZO carrier board
- 1 EZO conductivity circut
- 1-2 calibration solutions


### [Connecting the Sensor]

{{< columns >}}
{{< figure src="images/courses/cs10/unit00/lab-water-quality-02.jpeg" width="100%" title="Sensor" >}}
{{< figure src="images/courses/cs10/unit00/lab-water-quality-04.jpeg" width="100%" title="Circut" >}}
<--->
{{< figure src="images/courses/cs10/unit00/lab-water-quality-01.jpeg" width="100%" title="Carrier Board" >}}
{{< figure src="images/courses/cs10/unit00/lab-water-quality-03.jpeg" width="100%" title="Calibration Solutions" >}}
{{< /columns >}}


{{< code-action "Step 1: Connect the Carrier board to the Circut" >}}

{{< figure src="images/courses/cs10/unit00/lab-water-quality-05.png" width="100%" alt-text="Circut to Carrier Board" >}}

{{< code-action "Step 2: Connect the Sensor to the Carrier Board" >}}


{{< figure src="images/courses/cs10/unit00/lab-water-quality-06.jpg" width="75%" alt-text="Sensor to Carrier Board" >}}

{{< code-action "Step 3: Connect the Carrier Board to the Raspberry Pi" >}}

Refer to the 2 diagrams below and follow the steps:

0. Carrier Board `RX` connected to Raspberry Pi `GPIO 3 (SCL)`
0. Carrier Board `TX` connected to Raspberry Pi `GPIO 2 (SCA)`
0. Carrier Board `GND` connected to any Raspberry Pi `Ground` Pin
0. Carrier Board `VCC` connected to any Raspberry Pi `3v3 power` Pin


{{< figure src="images/courses/cs10/unit00/lab-water-quality-07.png" width="100%" alt-text="Carrier Board Diagram" >}}
{{< figure src="images/courses/cs10/unit00/00_fresh_gpiodiagram.png" width="100%" alt-text="GPIO Pin Diagram" >}}

### [Starter Code]

{{< code-action "SSH into your Raspberry Pi" >}} with `ssh YOUR_USERNAME@rasperrypi-N`

> Replace `YOUR_USERNAME` with the user your created.
>   
> Replace `N` with your Raspberry Pi number.

{{< code-action "Clone the lab repository" >}} in your `cs10\unit_00` folder and install the requirements.

```shell
cd cs10/unit_00
git clone https://github.com/the-isf-academy/lab-water-quality-YOUR-GITHUB-USERNAME.git
pip3 install pytz
```

The `lab-water-quality` repository contains the following:
- Software provided by Atlas Scientific, the manufacturer of the sensors
    - `AtlastI2C.py` - a Python file with a Class to control with the sensors
- `data_tank.csv` - a file that will stores the data collected from the fish tank
- `data_control.csv` - a file that will store the data collected from the control tank
- `sensor_interface.py` - a Python file that handles the collection of data over the course of 24 hours for your given sensor
- `README.md` - instructions for how to use your `data_collection.py` file. Another user should be able to easily use your program to run their own data analysis

## [1] Sensor Interface

Your goal is to expand the functionality of `sensor_interface.py` to the specifications of the project.

{{< code-action "Start by running" >}} `sensor_interface.py`

```shell
python3 sensor_interface.py
```

Currently, the program only polls the data once. It is your job to ensure it polls over 24 hours.
```shell
Success 100: 0
```

{{< code-action "Let's take a look at" >}} `data_tank.csv`
```shell
cat data_tank.csv
```

Currently, it only stores the date of the data polled. It is your job to ensure it stores all of the necessary information.
```shell
data
14-09-2021
```

**Your `sensor_interface.py` must include the following functionalities:**
- Poll every 15 minutes for 24 hours
- Write to a `.csv` file that stores the following each time the sensor is polled:
    - the date
    - the time
    - the type of data the sensor collects
    - the *parsed* data



{{< checkpoint >}}
**In your notebook with your partner, write the pseudocodoe to achieve this functionality.**

Take a look at the exisiting code and consider the following:
- How will you determine how frequently the data is polled?
- How will you stop the data from polling after 24 hours?
- How and when will you save the *parsed* data to the csv?

Review your pseudocode with a teacher before moving on.
{{< /checkpoint >}}


### [Extend the Polling]

{{< code-action "Implement the functionality to poll data every 15 minutes for 24 hours" >}}

{{< aside "Tip" >}}
Make sure your implementation is well abstracted. That way you can run small tests to see if it works. This will also aid you as you test the `.csv` functionalites.

*e.g. Try polling every 15 seconds for a full minute. What should you see as an output?*
{{< /aside >}}

### [Adding the time]

Now that you're able to poll data over a peroid of time, let's extend the `.csv` functionalities.

{{< checkpoint >}}
**In your notebook with your partner, imagine how your `.csv` file will be formatted by creating a sample table.**
{{< /checkpoint >}}

{{< code-action "With your sample table in mind, start by implementing the functionality to store the time" >}}


{{< aside "Resources" >}}

- Take a look at [this](https://www.programiz.com/python-programming/datetime/strftime) resource for details about the `strftime()` function of the `datetime` library.
- Take a look at [this](https://www.programiz.com/python-programming/csv) resource for details about the `csv` library.
{{< /aside >}}

{{< code-action "Test your implementation of storing the time." >}}

When you run  `cat data_tank.csv` in Terminal, you should see something like:
```shell
data,time
14-09-2021,08:50:27
```


### [Adding the data]

Finally, let's add the functionality of storing the data type and the parsed data points to the `.csv` file.

{{< code-action "Start by implementing the functionality to store the data type in the first row" >}}

{{< code-action "Then, implement the functionality to store each parsed data point." >}} Currently the program prints if the sensor was able to successfully read the data point. However, for the csv, we simply want the number measured.


{{< aside "Tip" >}}
Take a look at the functionalites of the `AtlasI2C` class.

*There may be some helpful methods.*
{{< /aside >}}

{{< code-action "Test your implementation of storing the data" >}}

When you run  `cat data_tank.csv` in Terminal, you should see something like:
```shell
data,time,EC
14-09-2021,08:50:27,100
```
*`EC` and `100` will differ depending on your data type and measured data*

{{< checkpoint >}}
Before moving on, demonstrate your fully functioning `sensor_interface.py` file.
{{< /checkpoint >}}

<!-- ## Preparing to Launch

Testing with solution -->
