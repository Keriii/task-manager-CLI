# Task Tracker CLI

A simple command-line application to track and manage your tasks.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
  - [Adding a Task](#adding-a-task)
  - [Updating a Task](#updating-a-task)
  - [Deleting Tasks](#deleting-tasks)
  - [Marking Tasks as In Progress or Done](#marking-tasks-as-in-progress-or-done)
  - [Listing Tasks](#listing-tasks)
- [Task Properties](#task-properties)
- [Examples](#examples)
- [Error Handling](#error-handling)
- [Contributing](#contributing)
- [License](#license)

## Introduction

**Task Tracker CLI** is a command-line application that allows you to manage your to-do list efficiently. You can add, update, delete, and list tasks, as well as mark them as in progress or done. All tasks are stored in a JSON file in the current directory, making it easy to track and manage your tasks.

## Features

- **Add Tasks**: Create new tasks with descriptions.
- **Update Tasks**: Modify the description of existing tasks.
- **Delete Tasks**: Remove one or multiple tasks by their IDs.
- **Mark Tasks**: Change the status of tasks to `in-progress` or `done`.
- **List Tasks**: Display all tasks or filter them by status or IDs.
- **Persistent Storage**: Tasks are saved in a `tasks.json` file.

## Prerequisites

- **Python 3.x** installed on your machine.
- A terminal or command prompt to run the application.

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/task-tracker-cli.git
   cd task-tracker-cli
    ```
   
## Usage

The application is run from the command line using the `task_cli.py` script. Below are the available commands and their usage.

### Adding a Task

Add a new task with a description.
```bash
python3 task_cli.py add "Your task description"
```

**Example:**
```bash
python task_cli.py add "Buy groceries"
```

**Output:**
```bash
Task added successfully (ID: 1)
```

### Updating a Task

Update the description of an existing task.
```bash
python3 task_cli.py update <task_id> "New task description"

```
**Example**:
```bash
python task_cli.py update 1 "Buy groceries and cook dinner"
```

**Output:**
```bash
Task 1 updated successfully
```

### Deleting Tasks

Delete one or multiple tasks by their IDs.
```bash
python task_cli.py delete --ids [<task_id2> ...]
```
**Example**:
```bash
python task_cli.py delete --ids 1 2 3
```
**Output:**
```bash
3 task(s) deleted successfully
```

### Marking Tasks as In Progress or Done
Mark as In Progress
```bash
python task_cli.py mark-in-progress <task_id>
```

**Example:**
```bash
python task_cli.py mark-in-progress 4
```

**Output:**
```bash
Task 4 marked as in-progress
```

### Mark as Done
```bash
python task_cli.py mark-done <task_id>
```

**Example:**
```bash
python task_cli.py mark-done 4
```

**Output:**
```bash
Task 4 marked as done
```

### Listing Tasks

List all tasks or filter them by status or IDs.
1. List All Tasks
```bash
python task_cli.py list
```

2. List Tasks by Status
```bash
python task_cli.py list --status <status>
```
Available Statuses: to-do, in-progress, done

**Example**:
```bash
python task_cli.py list --status in-progress
```

3. List Specific Tasks by IDs
```bash
python task_cli.py list --ids [<task_id2> ...]
```

**Example:**
```bash
python task_cli.py list --ids 4 5
```

4. Combine IDs and Status
```bash
python task_cli.py list --ids 4 5 --status done
```

Note: This will list tasks with IDs 4 and 5 that are marked as done.
Task Properties

Each task in the tasks.json file has the following properties:

    id: A unique integer identifier for the task.
    description: A short description of the task.
    status: The status of the task (todo, in-progress, done).
    createdAt: The date and time when the task was created (ISO 8601 format).
    updatedAt: The date and time when the task was last updated (ISO 8601 format).