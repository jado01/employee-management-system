# Employee and Team Management System

A command-line application for managing employees, managers, leaders, departments, and teams.

The project demonstrates object-oriented programming, inheritance, composition, validation, JSON data persistence, audit logging, and automated model tests. It was created as the second main project of the Skillmea Python Academy.

## Features

- Create employees, managers, and leaders with unique IDs.
- Validate salaries and increase an employee's salary.
- Create departments and assign managers.
- Add employees to departments and teams.
- Create multiple teams within a department.
- Assign departments to leaders.
- Record leader decisions in the audit log.
- Display employees and departments in formatted tables.
- Display the complete organization structure in a single overview.
- Save and restore application data using JSON files.
- Generate ready-to-use demo data.
- Verify core domain rules with automated tests.

## Business rules

- A manager can manage only one department.
- An employee can belong to only one department.
- A department can have only one leader.
- A leader can manage multiple departments.
- An employee can join multiple teams within their department.
- An employee cannot be added to the same team more than once.
- Department and team names cannot be empty or duplicated within the same scope.

## Requirements

- Python 3
- No third-party packages are required.

## Run the application

```bash
git clone https://github.com/jado01/employee-management-system.git
cd employee-management-system
python main.py
```

The application presents an interactive menu divided into employee, department, team, and organization management sections.

## Try it with demo data

```bash
python demo_data.py
python main.py
```

The demo script creates a small organization with employees, managers, leaders, departments, teams, and team memberships. It does not overwrite existing application data.

Choose **Show organization structure** in the application to display the complete overview.

## Run the tests

```bash
python -m unittest discover -s tests -v
```

The test suite verifies salary validation and core relationship rules between employees, managers, departments, and teams.

## Data persistence and logging

Application data is stored locally in the `data` directory:

- `employees.json` stores employees, managers, and leaders.
- `organization_structure.json` stores departments, relationships, teams, and team memberships.
- `employee_management.log` stores timestamped audit events.

Generated data and log files are excluded from Git.

## Project structure

```text
employee-management-system/
|-- main.py                    # Application entry point
|-- menu.py                    # Main interactive menu
|-- actions.py                 # Menu actions and workflows
|-- helpers.py                 # Input, selection, and terminal helpers
|-- organization_structure.py # Formatted organization overview
|-- demo_data.py               # Optional demo data generator
|-- models/
|   |-- employee.py            # Employee model and salary validation
|   `-- organization.py        # Manager, Leader, Department, and Team models
|-- services/
|   |-- data_storage.py        # JSON persistence
|   `-- audit_log.py           # Audit logging
`-- tests/
    `-- test_models.py         # Automated model tests
```

## Concepts practised

- Classes, objects, encapsulation, and properties
- Inheritance and method overriding
- Composition and relationships between objects
- Validation and exception handling
- File handling and JSON serialization
- Audit logging
- Separation of responsibilities
- Automated testing with `unittest`

## Background

This project was developed as the second main assignment of the Skillmea Python Academy. Its purpose was to practise building a larger application step by step, connecting multiple object-oriented models, persisting their relationships, and refactoring the code into a clearer project structure.


