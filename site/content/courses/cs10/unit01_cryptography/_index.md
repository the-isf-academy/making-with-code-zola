---
title: "Unit Cryptography: Puzzle Project"
type: unit
slug: unit00_networking
# draft: true
---

**In this project, you will create a Cryptography puzzle. It is completely up to you to create its theme and the final message/prize. You can be as creative as you’d like!**

It must have at least 3 parts to the puzzle. You will be responsible for ensuring the puzzle is solvable, includes sections that require coding, and is readable to the guesser.


You may choose to do this project individually, or as a pair. Partners will receive the same grade as eachother. If do you choose to work as a pair, just pick 1 Puzzle Outline to complete.

---

## [0] Project Resources

**This project is primarily accessing your ability to apply and reuse code.** We highly recommend taking time to look at these resources that were utilized to the encrypt materials in the previous puzzles. Let a teacher know if you have any questions.

- [Previous Puzzle Google Docs](https://drive.google.com/drive/folders/1RNOGAvU_5xZbTdH0gIrqJkxtKM-Y5r7q?usp=sharing)
    - To export a doc as a PDF: `File > Download > PDF Document (.pdf)`
- [helper functions Python file](https://github.com/the-isf-academy/project_cryptography_resources/blob/main/helpers.py)
    - `make_encrypted_df()`
    - `decrypt_pdf()`
    - `caesar_cipher()`
    - `number_to_letter()`
- quickly caesar encrypt text using [this site](https://cryptii.com/pipes/caesar-cipher)
- [pypdf library documentation](https://pypdf2.readthedocs.io/en/latest/index.html)
- [open source `json` files with words of various categories](https://github.com/dariusk/corpora/tree/master/data)
    - simply copy and paste the parts you want into a Python file
    - just be sure to cite this in your README.md
- shorten links using [bit.ly](http://bit.ly/)
- [replit.com](https://replit.com/) to host a small Python file online






---

## [1] Puzzle Outline Document

This is a small project. The primary purpose of the document is that is holds a solution breakdown to each part of your puzzle.


{{< code-action >}} **Find your puzzle outline document in your Google Drive folder.** Share the document with your group member if you are working as a pair.

---

## [2] Starter Code

Each student has their own repository. If you are working as a pair, tell a teacher which repository you would like to work in and they will make it collaborative.

{{< code-action "Download your repository with starter code for your project." >}}

```shell
cd ~/desktop/making_with_code/cs10/unit_cryptography/
git clone https://github.com/the-isf-academy/project_cryptography.git
cd project_cryptography
```

{{< code-action "Enter the poetry shell." >}}
```shell
poetry shell
```

{{< code-action "Install requirements" >}}
```shell
poetry install
```

It contains the following :
- A `Cryptography Project | Puzzle Outline` - a Google Doc
- A `project_cryptography` repository containing the following:
  - `helpers.py` - you may include any useful functions *(e.g. `caesar_decrypt()`)*
  - `README.md` - this is the documentation. It should include a brief description of the puzzle and the first clue.
  - any additional Python files *(e.g. `adjectives.py`)*

{{< code-action "Start developing the first step of the puzzle!" >}}

---

## [3] Criteria


**This project will be assessed on the following criteria:**
- puzzle outline [3]
- encryption methods[3]
- puzzle execution[3]
- readability [3]


**For each criteria you will be assessed on a score from 0-3. With 8 criteria, there is a total of 12 potential points.** If you choose to work as a pair, you will be awarded the same grade as your group member.
- 0 - no evidence of the practice
- 1 - limited evidence of the practice
- 2 - adequate evidence of the practice
- 3 - substantial evidence of the practice


---

### [Success Claims]

Successful computer scientists should be able to make the following claims:
- I can thoughtfully plan and outline the puzzle
    - I can plan each step of the puzzle that logically
- I can successfully use 2 methods of encryption
    - I can use the caesar cipher or one of the additional methods you may have explored
    - I can create a password protected clue that requires brute force to break
- I can write a fully executable puzzle
    - I can ensure each step of the puzzle is solvable
    - I can test my puzzle
- I can write a readable puzzle
    - I can provide the necessary helper functions and files in the repository
    - I can write a README.md file with the puzzle description and first clue
    - I can prepare any additional materials such as printed documents or encrypted PDF files


*Keep these success claims in mind when completing your project.*

---

### [Scoring]

The project is scored out of 7. It will be calculated by adding the score from each criteria, then referencing the bands:
- 1 = 0
- 2 = 1
- 3 = 2-3
- 4 = 4-6
- 5 = 7-8
- 6 = 9-10
- 7 = 11-12

---

## [4] Deliverables

{{< deliverables  "Projects are due on Wednesday, 11 January." >}}

- A `Cryptography Project | Puzzle Outline` - a Google Doc
- A `project_cryptography` repository containing the following:
  - `helpers.py` - you may include any useful functions *(e.g. `caesar_decrypt()`)*
  - `README.md` - this is the documentation. It should include a brief description of the puzzle and the first clue.
  - any additional Python files *(e.g. `adjectives.py`)*

---

**🗓️ Timeline**

- begins on Thursday, 05 January
- due on Wednesday, 11 January

You should not have to work on this outside of class. The key is to rely on the example puzzles and resources provided.

---

{{< code-action "Push your work to Github:" >}}
- `git status`
- `git add helpers.py`
    - you can add multiple files by putting a space in-between each file
    - *e.g. `git add helpers.py adjectives.py`*
- `git status`
- `git commit -m "your message goes here"`
  > be sure to customize this message, do not copy and paste this line
- `git push`
{{< /deliverables >}}
