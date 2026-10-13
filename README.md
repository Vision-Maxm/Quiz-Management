# 🧠 Quiz Management System

> **A Python-based command-line quiz application built with Object-Oriented Programming (OOP).**  
> Create and manage questions, conduct quizzes, evaluate answers, and save candidate results automatically.

---

## 📌 Project Overview

The **Quiz Management System** is a menu-driven Python application that lets users take quizzes and manage a reusable question bank. It supports **Multiple Choice Questions (MCQs)** and **True/False questions**, checks answers, calculates scores, and stores quiz results in CSV files for later review.

This project demonstrates practical Python programming concepts, especially **Object-Oriented Programming, file handling, exception handling, and data management using CSV files**.

## ✨ Features

- 📝 **Take a Quiz** — Answer questions from the saved question bank.
- 🔘 **Multiple Choice Questions** — Supports four options labelled A, B, C, and D.
- ✅ **True/False Questions** — Answer using `T` / `F` or `True` / `False`.
- ➕ **Add Questions** — Add MCQ and True/False questions through the menu.
- 🎯 **Automatic Evaluation** — Checks answers and calculates the final score and percentage.
- 💾 **Save Results** — Records the candidate name, score, total questions, percentage, and timestamp.
- 📊 **View Quiz Results** — Display previously saved candidate performance records.
- 🛡️ **Input Validation** — Handles invalid answer formats and menu selections.
- 🧩 **OOP Design** — Uses abstraction, inheritance, encapsulation, and polymorphism-friendly method overriding.
- 📂 **CSV Storage** — Stores questions and results in simple CSV files.

## 🛠️ Built With

- **Python 3.9+** (uses built-in generic type hints such as `list[str]`)
- `csv` — Read and write question and result data
- `datetime` — Add timestamps to quiz results
- `os` — Check whether data files exist
- `abc` — Define an abstract base class for questions

All libraries used by this project are part of Python's standard library, so no third-party packages are required.

## 📁 Project Structure

```text
quiz-management-system/
├── main.py             # Python source code (use your actual script filename)
├── questions.csv       # Question bank; created/updated when questions are added
├── quiz_results.csv    # Candidate results; created when results are saved
└── README.md           # Project documentation
```

> **Note:** `main.py` is a suggested filename. If your Python file has a different name, use that filename in the project folder and in the run command below.

## ⚙️ Getting Started

### 1. Install Python

Install Python **3.9 or newer** from [python.org](https://www.python.org/downloads/). During installation on Windows, enable **“Add Python to PATH”** if that option is shown.

Check your installation:

```bash
python --version
```

On some systems, use:

```bash
python3 --version
```

### 2. Get the Project

Download or clone the project repository, then open a terminal in the project folder.

### 3. Run the Application

If your script is named `main.py`, run:

```bash
python main.py
```

If your script has another name, replace `main.py` with the actual filename.

## 🚀 How to Use

When the application starts, it displays this menu:

```text
=== QUIZ MANAGEMENT SYSTEM ===
1. Take Quiz
2. Add Multiple Choice Question (MCQ)
3. Add True / False Question
4. View All Quiz Results
5. Exit
```

Choose an option by entering its corresponding number.

| Menu option | What it does |
|---|---|
| `1` | Enter a candidate name and take the quiz |
| `2` | Add a multiple-choice question with four options and the correct option |
| `3` | Add a True/False statement and its correct answer |
| `4` | View saved candidate results |
| `5` | Exit the application |

### ✍️ Answering Questions

- For MCQs, enter `A`, `B`, `C`, or `D`.
- For True/False questions, enter `T` or `F`. The answer checker also accepts `TRUE` and `FALSE`.
- If an answer format is invalid, the program asks you to try again.
- At the end of the quiz, the application displays the score and percentage.

## 📄 CSV Data Files

### `questions.csv`

The question bank uses these column headings:

```csv
type,prompt,opt_a,opt_b,opt_c,opt_d,correct
MCQ,"Which language is this project written in?","Java","Python","C++","Ruby",B
TF,"Python is a programming language.",,,, ,True
```

- `type`: `MCQ` for multiple-choice questions or `TF` for True/False.
- `prompt`: The question or statement shown to the candidate.
- `opt_a`–`opt_d`: The four MCQ options. These are blank for True/False questions.
- `correct`: The correct option letter for MCQs, or a truth value for True/False questions.

You can also populate the question bank from within the application using menu options `2` and `3`. The application creates the CSV header when it first writes to an empty question file.

### `quiz_results.csv`

Quiz results are appended to this file with the following columns:

```csv
timestamp,candidate_name,score,total,percentage
```

Each saved record includes the date and time, candidate name, number of correct answers, total questions, and final percentage.

> 💡 Keep both CSV files in the same working directory as the application unless you configure different file paths in the code.

## 🧠 Python Concepts Demonstrated

| Concept | How it is used |
|---|---|
| **Classes and Objects** | Models questions and quiz management |
| **Abstraction** | `Question` defines the common interface for question types |
| **Inheritance** | `MCQQuestion` and `TrueFalseQuestion` inherit from `Question` |
| **Encapsulation** | Uses protected/private-style attributes for internal data |
| **Polymorphism** | Each question type implements its own `display()` and `check_answer()` methods |
| **Exception Handling** | Custom exceptions report question-loading and invalid-answer errors |
| **File Handling** | Opens and processes CSV files safely with context managers |
| **Data Processing** | Calculates scores and percentages |
| **Date and Time** | Records when each quiz result is saved |
| **Input Validation** | Checks menu choices and answer formats |

## 🖥️ Example Result

The exact output depends on the questions in your CSV file. A quiz completion may look like this:

```text
============================================================
                 STARTING QUIZ FOR: ALEX
============================================================

Q1: Which language is this project written in?
  [A] Java
  [B] Python
  [C] C++
  [D] Ruby
Your answer: B
✓ Correct!

------------------------------------------------------------
Quiz Completed! Final Score: 1/1 (100.0%)
------------------------------------------------------------
✓ Result successfully saved to 'quiz_results.csv'.
```

*This is an illustrative example; your actual questions and output may differ.*

## ⚠️ Notes & Limitations

- If the question bank is empty, add questions before starting a quiz.
- The application currently uses a command-line interface; it does not include a graphical or web interface.
- Question and result data are stored locally in CSV files.
- True/False values in a manually edited CSV should use `true`, `t`, or `1` for True; other values are interpreted as False by the current loader.
- The application is intended as a learning project and does not include user accounts, encryption, or online data storage.

## 🔮 Future Enhancements

Possible improvements for a future version include:

- ⏱️ Add a quiz timer and configurable question limits.
- 🎲 Randomize question order.
- 📈 Generate detailed performance summaries.
- 🗂️ Organize questions by subject or difficulty.
- 🖥️ Build a graphical interface using Tkinter or a web interface.
- 🧪 Add automated unit tests.
- 🏆 Add leaderboards and high-score tracking.

## 🎓 Learning Outcomes

By building this project, you can demonstrate how to:

- Design a menu-driven application in Python.
- Apply core Object-Oriented Programming principles.
- Read and write structured data with CSV files.
- Validate user input and handle errors.
- Calculate and persist quiz performance records.
- Organize code into reusable classes and methods.

## 👨‍💻 Author

**Your Name**  
*Python / Machine Learning Intern*

> Replace **Your Name** with your preferred name before publishing.

---

⭐ **If you find this project useful, consider giving the repository a star!**

Made with 🐍 Python and a passion for learning.
