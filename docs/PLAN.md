# Planning for Organa development

The following documents the development plan for Organa. The plan is divided into short, medium, and long-term goals, each term four times larger than the previous one, starting with one week at short and finishing at four months at long. Each goal is broken down into specific tasks.

## **Short Term (This Week)**

**Goal:** Build the foundation and validate your workflow.

### 1. **Project Setup**

- [ ] Create project structure:
  - `organa-core/`, `organa-tasks/`, `organa-budget/`, `launcher/`
- [ ] Setup `CMakeLists.txt` for modular builds
- [ ] Add a CLI arg parser (like `CLI11` or custom)

### 2. **Implement Organa Tasks MVP**

- [ ] Add simple task structure (title, due date, priority, status)
- [ ] Store tasks in flat file (JSON or custom format)
- [ ] Implement commands:
  - `organa tasks add`
  - `organa tasks list`
  - `organa tasks done`

### 3. **Neovim Integration (Minimal)**

- [ ] Add Neovim command to open `organa --today` in terminal

### 4. **Login Script Prototype**

- [ ] Write a shell script that runs:
  - Organa tasks summary
  - Organa budget summary (placeholder)

---

## **Medium Term (1 Month)**

**Goal:** Solidify functionality, add TUI, and automate daily usage.

### 1. **Organa Budget MVP**

- [ ] Track expenses and categories
- [ ] Add budgeting logic
- [ ] Commands:
  - `organa money add`
  - `organa money summary`
  - `organa money report`

### 2. **TUI Layer**

- [ ] Integrate `FTXUI` into `organa-tui`
- [ ] Display tasks + budget in side-by-side panes
- [ ] Allow marking tasks done with key

### 3. **Refactor and Modularize**

- [ ] Move shared logic into `organa-core`
- [ ] Ensure all modules build cleanly with CMake

### 4. **Neovim Plugin Improvements**

- [ ] Add Lua command to show tasks in buffer
- [ ] Add simple task-adding popup (`vim.ui.input`)

### 5. **Installer or Dotfiles Integration**

- [ ] Add to dotfiles as optional component (`~/.dotfiles/.config/organa`)
- [ ] Ensure compatibility with login automation

---

## **Long Term (4 Months)**

**Goal:** Mature, clean, extensible tool that fits seamlessly into your life.

### 1. **Advanced Features**

- [ ] Recurring tasks and reminders
- [ ] Budget projections
- [ ] Daily/weekly logs
- [ ] Configurable priorities / urgency weights

### 2. **Persistence Layer Upgrade**

- [ ] Move from flat file to SQLite (optional)
- [ ] Add backup/sync logic (e.g., sync to Git repo or WebDAV)

### 3. **Polished TUI**

- [ ] Dynamic views (calendar, day view, filters)
- [ ] Improved input UI (FTXUI forms)

### 4. **Cross-System Support**

- [ ] Make login tool portable across systems
- [ ] Package Organa (deb or standalone binary)

### 5. **Stretch: Start Learning Rust**

- [ ] Prototype a Rust CLI version (optional)
- [ ] Explore rewriting one module in Rust for comparison

---
