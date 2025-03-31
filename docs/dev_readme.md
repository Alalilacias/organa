# Development guide

The following document shall serve a backup document of the information needed for the development. Given that this is a small project, for now, this should fill the spot of a CONTRIBUTING.md or GUIDE.md file.

## Table of Contents

- [Declaration of Intentions](#declaration-of-intentions)
- [Currently Intended Project Folder Layout](#currently-intended-project-folder-layout)
- [Currently Intended User Config Structure](#currently-intended-user-config-structure)

## Declaration of Intentions

The current project intends to create a cli-based organizer that can handle tasks, money, and reminders. The project is intended to be a learning experience for the author, and as such, it will be developed in C++.
The project will be developed in a modular fashion, with the intention of making it easy to add new features in the future.
For now, a TUI is not intended, but it may be added in the future. If one were to be added, it'd be done in one of the following ways:

- [ftxtui](https://github.com/ArthurSonzogni/FTXUI?tab=readme-ov-file): C++ based TUI library.
- [rata-tui](https://github.com/ratatui/ratatui?tab=readme-ov-file) a rust based TUI crate.

Obviously, C++/Rust integration would bring massive problems, primarily given I know nothing about the Rust language. However, it's a possibility. Ftxtui is the most likely solution to be implementation, given it's a C++ library.

## Planning

Feel free to check [PLAN.md](https://github.com/Alalilacias/organa/docs/PLAN.md) for the current planning of the project.

## Currently Intended Project Folder Layout

```markdown
organa/
├── CMakeLists.txt # Top-level build file
├── README.md # Project overview
├── .gitignore
│
├── core/ # Shared logic (file I/O, date utils, config, etc.)
│ ├── include/organa/core/
│ │ └── Config.hpp
│ └── src/
│ └── Config.cpp
│
├── tasks/ # Task-specific CLI tool
│ ├── include/organa/tasks/
│ │ └── Task.hpp
│ ├── src/
│ │ ├── Task.cpp
│ │ └── main.cpp # Builds `organa-tasks`
│ └── CMakeLists.txt
│
├── budget/ # Budget tool
│ ├── include/organa/budget/
│ ├── src/
│ │ └── main.cpp # Builds `organa-budget`
│ └── CMakeLists.txt
│
├── tui/ # Optional TUI frontend (FTXUI)
│ ├── include/organa/tui/
│ ├── src/
│ │ └── main.cpp # Builds `organa-tui`
│ └── CMakeLists.txt
│
├── launcher/ # Combined summary tool (e.g., for login)
│ ├── src/launcher.cpp
│ └── CMakeLists.txt # Builds `organa`
│
└── scripts/ # Dev scripts (e.g., install, test, run)
└── install.sh
```

## Currently Intended User Config Structure

```markdown
~/.config/organa/
├── config.json # Global config (theme, currency, etc.)
├── tasks.json # Task database (or .csv, .organa format)
├── budget.json # Budget data (or SQLite later)
├── logs/
│ └── 2025-03-31.log # Optional: daily/weekly logs
├── cache/
│ └── summary.txt # Last summarized output
```
