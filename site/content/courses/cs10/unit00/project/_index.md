---
Title: Hardware Project
# draft: true
---

# Unit 00 Hardware Project
In this project you will act as a data collector hired by ISF to assess the water quality of different areas around the school. Using sensors to collect the data and Python to analyze the data, you will produce a comprehensive data report. 

## [0] Starter Code

{{< code-action "Clone the project repository" >}} in your `cs10\unit_00` folder. 

```shell
cd cs10/unit_00
git clone https://github.com/the-isf-academy/project-hardware-YOUR-GITHUB-USERNAME.git
```


## [1] Deliverables

Each person is responsible for writing a program that utilizies the provided sensor to collect water quality information over the course of 24 hour. You will then produce a short report with graphs illustrating the findings in a jupyter notebook file. 

A successful `project-hardware` repository will have the following:
- `Hardware Project Planning Document` - a Google Doc with a project plan  
- `data.csv` - a file that stores the collected data formatted for your given sensor
- `data_collection.py` - a Python file that handles the collection of data over the course of 24 hours for your given sensor 
- `data_anaylsis.py` - a jupyter notebook file that analyzes the data with at least 3 graphs 
- `README.md` - instructions for how to use your `data_collection.py` file. Another user should be able to easily use your program to run their own data analysis.
- `assessment.md` - a self assessment of your final project 

`AtlastI2C.py` is also included in your repostitory. This is the interface for the sensors. 

## [2] Planning Document 
This is a large scale project that demands ample planning before tinkering. Before you start working on your project, you are required to complete your project planning document and review with with a teacher. You can find your planning doc in your Google Drive folder called `Hardware Project Planning Document`.

Once you have completed your project plan, meet with a teacher to talk through your plan. Don't start programming until you get your plan approved.

## [3] Assessment 

You are responsible for assessing your own project, though your teachers will let you know if they disagree. In `assessment.md`, you are required to explain how your project should be scored, and to give evidence to support your assessment.

### [Planning and Documentation]

*Students create personally meaningful projects through an iterative design cycle. Students’ work is grounded in a development plan which students create before beginning the project. Students document the development of their projects in order to create a record of decisions, assumptions, and lingering flaws. Students define the intended functionality and develop towards evaluation.*

> Write a short paragraph reflecting and evaluating your ability to plan a large scale computer science project and document your work for others to understand.

Key practices:
- detailed action plan for each class session
- test cases and edge cases for my program 
- consistent Github commits 
- `README.md` file  

### [Computational Thinking]
*Students appropriately apply computer science concepts and tools in context. On top of computer science concepts and tools, students apply computational thinking practices including habits such as writing pseudocode, developing iteratively, using abstractions, decomposing problems, and debugging.*

> Identify and describe 3 moments from the project that demonstrate your growth as a computer scientist. Tag each moment with at least one key practice and at most 3 key practices. 
>
> Write a short paragraph for each moment explaining how each of the key practices you tagged is demonstrated in the moment you described and how the moment helped you develop this practice.

Key practices:
- Abstraction
- Decomposition
- Pseudocode
- Iterative development
- Debugging
- Testing
- Reading documentation

### [Overall Assessment] 

Determine the level between 1-7 that represents your overall development of the key practices based on the evidence and reasoning you provided.

> Determine your score and write a short paragraph with your justification as to the score you self-assigned. 

## [4] Resources 


### [Documentation]
This project heavily focuses on reading and understanding documentation. Luckily Atlast Scientific, the manufacturer of the sensors, provides fantastic documentation.

#### Data Sheets

A data sheet is an informational document provided by the manufactorer with details of the performance and properties of a product. 

- [ORP Sensor](https://files.atlas-scientific.com/ORP_EZO_Datasheet.pdf)
- [Dissolved Oxygen Sensor](https://files.atlas-scientific.com/DO_EZO_Datasheet.pdf)
- [PH Sensor](https://files.atlas-scientific.com/pH_EZO_Datasheet.pdf)
- [Conductivity Sensor](https://files.atlas-scientific.com/EC_EZO_Datasheet.pdf)

#### Raspbery Pi Sample Code
Atlas Scientific provides it's own interface system to interact with the sensors using Python. The sample file, `AtlastI2C.py` is already provided for you in your `project-hardware` repository. 

[Raspberry Pi Sample Code Documentation](https://files.atlas-scientific.com/pi_sample_code.pdf)

#### Carrier Board 
Each sensor must be connected to a carrier board and the carrier board is connected to the Pi. 

[Carrier Board](https://files.atlas-scientific.com/electrically-isolated-ezo-carrier-board.pdf)

<hr>

### [File I/O]

File I/O, or File Input/Output, is the ability to read and write to a file in Python. 
In order to store the data the sensor collects, you will need to learn how to write to a file. 

Take a look at [this](https://www.pythontutorial.net/python-basics/python-write-csv-file/) tutorial for a great example. 

<hr>


### [Jupyter Notebook Refresh]

To open a Jupyter notebook, you will need to start a Jupyer server from your 
Terminal in your `project-hardware` repository directory:

```shell
jupyter notebook
```

Take a look at your `lab-pandas-matplotlib` and your `project-data-science` for a refresh as to how to create graphs using the `Pandas` and `MatPlotLib` Python libraries. 

- [Pandas Documentation](https://pandas.pydata.org/docs/user_guide/index.html)
- [MatPlotLib Documentation](https://matplotlib.org/)