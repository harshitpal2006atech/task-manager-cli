# Task Manager CLI

A simple command-line task manager built with Python. It allows users to add, list, complete, and delete tasks using command-line commands. Tasks are stored in a JSON file, so they remain saved even after the program is closed.

## Features

- Add new tasks with an optional due date.
- List all tasks.
- Filter tasks by status (`pending` or `completed`).
- Filter tasks by due date.
- Mark tasks as completed.
- Delete tasks by ID.
- Save tasks in a JSON file for persistent storage.
- Validate due dates in `YYYY-MM-DD` format.
- Use `argparse` subcommands for a clean command-line interface.
- Includes automated tests using `pytest`.

## Technologies Used

- Python
- argparse
- JSON
- pytest

## Requirements

- Python 3.9 or newer
- pytest for running tests

## Installation

**1. Clone the repository**

```bash
git clone https://github.com/YOUR-USERNAME/task-manager-cli.git
cd task-manager-cli
```

Replace `YOUR-USERNAME` with your GitHub username.

**2. Install the dependencies**

```bash
python -m pip install -r requirements.txt
```

## Usage

### Add a task

```bash
python task_manager.py add "Complete Python assignment" --due 2026-10-20
```

You can also add a task without a due date:

```bash
python task_manager.py add "Learn Python"
```

### List all tasks

```bash
python task_manager.py list
```

### Filter tasks by status

Show pending tasks:

```bash
python task_manager.py list --status pending
```

Show completed tasks:

```bash
python task_manager.py list --status completed
```

### Filter tasks by due date

```bash
python task_manager.py list --due 2026-10-20
```

### Complete a task

Use the task ID displayed in the task list:

```bash
python task_manager.py complete 1
```

### Delete a task

```bash
python task_manager.py delete 1
```

### View help

```bash
python task_manager.py --help
```

## Running Tests

Run the automated test suite using:

```bash
python -m pytest -v
```

The tests cover task creation, status filtering, due-date filtering, task completion, deletion, and invalid date handling.

## Data Storage

Tasks are saved by default in a JSON file located at:

```text
~/.task-manager/tasks.json
```

The application creates the required directory and file automatically when a task is saved for the first time.

You can set the `TASK_MANAGER_DATA` environment variable to use a different storage location.

## Project Structure

```text
task-manager-cli/
├── task_manager.py
├── requirements.txt
├── README.md
├── .gitignore
└── tests/
    └── test_task_manager.py
```

## Design Decisions

This project uses a JSON file instead of a database to keep the application simple and easy to run. Each task has a unique ID, a title, an optional due date, and a status. The command-line interface uses `argparse` subcommands rather than an interactive menu.

## Learning Outcomes

- Working with Python command-line arguments.
- Creating and organizing Python functions.
- Reading and writing JSON files.
- Handling errors and validating dates.
- Writing automated tests with pytest.
- Documenting and preparing a Python project for GitHub.

## Author

Created as a Python programming project to practice command-line application development, file handling, and automated testing.
