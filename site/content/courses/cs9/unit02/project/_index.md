---
Title: Project
# draft: true
---

# Unit 02 Games Project

In this project you will make a game using the Quest library. It's up to you to make a game with your group.

{{< figure src="images/courses/cs9/unit02/project0.png" width="50%" >}}

---

## [0] Planning Document

This is a big project with a lot of room for customization. It is important for each group to plan out their game prior to coding.

{{< write-action "Plan your game with your group." >}} Once you have completed your planning document, meet with a teacher to talk through your project.

---

## [1] Deliverables

- A `Unit 02 Games Project: Planning Document` 
- A `project-games` repository will include some if not all the following files:
    - `game.py` when this program runs, it should launch your game
    - map assets
    - sprite assets
    - `.ink` story file
    - `README.md`

### [Timeline]

Click below to see a detailed timeline for your class section.

🕹️ Our final class of the year will be a party where each group shares their games!

#### cs9.1
{{< expand "cs9.1 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 30 May 2022  | Introduction to Project/Planning Doc |
| 02 June 2022 | Work Day        |
| 07 June 2022 | Work Day                |
| 09 June 2022 | Work Day                |
| 13 June 2022 | Due: Final Edits to Game  |
| 16 June 2022 | 🎉 Final Day of Class - Party 🎉           |

{{< /expand >}}

#### cs9.2

{{< expand "cs9.2 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 31 May 2022  | Introduction to Project/Planning Doc |
| 01 June 2022 | Work Day        |
| 02 June 2022 | Work Day                |
| 07 June 2022 | Work Day                |
| 10 June 2022 | Work Day                |
| 14 June 2022 | Work Day                |
| 15 June 2022 | Due: Final Edits to Game                |
| 16 June 2022 | 🎉 Final Day of Class - Party 🎉  |

{{< /expand >}}



##  [2] Set Up

For this project, each group will share one git repository. It is your responsibility to regularly commit to your repository.

{{< code-action "Download your repository with starter code for your project." >}}
> replace the `YOUR-GITHUB-USERNAME` with your Github username.
>
> *example:*
>
> *`git clone https://github.com/the-isf-academy/project-animation-emmaqbrown.git`*


```shell
cd Desktop
cd cs9/unit_02
git clone https://github.com/the-isf-academy/project-games-groupX.git
```
> replace `X` with your group number 

{{< expand "cs9.1 Groups" >}}

| Group #        | Members                  |
|-------------|-------------------------|
| 0  | Introduction to Project/Planning Doc |
| 1 | Work Day        |
| 2 | Work Day                |
| 3 | Work Day                |

{{< /expand >}}

---

### [Advanced Git]

When using Git as an individual, the primary action is to `push` your work to the server. However, **when multiple people are working on a single project you must remember to `pull` before beginning to code**. 

Communication is key when collaborating on a repository. **We highly recommend communicating with your teammates about who is going to work on which file.** If multiple people edit the same lines of code in the same file, you will have to work together to resolve the merge conflicts. 


Let's practice pushing and pulling by updating the `README.md` file. 

{{< code-action >}} **Choose one person to open the `README.md` file.** 

{{< write-action >}} **Add their name to the file.**

{{< code-action "Save and close the file. Then push the updates to Github" >}}

{{< code-action >}} **Once the changes have been made, the teammate should `git pull` the changes.**

> ```shell
> git pull 
> ```

{{< code-action >}} **The teammate should now open the `README.md` file.** They should see the changes to the file. 

{{< write-action >}} **Add their name to the file.**

---

## [3] Self-Assessment
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score.

In `Unit 00 Animation Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit.

The self-assessment is broken down into three areas:
- Practices
    - planning, iterative development, test cases, and readability
- Concepts
    - abstraction and decomposition
- Reflection

**To do well in this project, you should be able to concretely justify that you can do each practice and understand each concept by providing evidence from your code.**

---


## [5] General Tips and Tricks

### [Map]

Make sure all of the assets for the map are in the folder of the repository. This includes:

- `.png` tilesets you download from the internet 
- `.tsx` files you create from tilesets in Tiled
- `.tmx` map files you create 

---

### [TLDR Advanced Github ]

0. `git pull`
0. resolve merge conflicts
0. update files 
0. `git status`
0. `git add`
0. `git commit`
0. `git push`