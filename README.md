# Organa

**Organa** is a personal, terminal-based productivity dashboard written in C++. It runs automatically at system startup and presents a summarized overview of upcoming responsibilities and financial planning. Designed for clarity, autonomy, and configurability, Organa helps you stay in control of your time and money.

---

## Features

### 🗂 Responsibilities System
- Track tasks with:
  - Name
  - Description
  - Urgency level (measured in days before due date)
  - Due date
- Accept both single and batch inputs (CSV format)
- Configurable urgency threshold and daily task display limit
- Summarized and full views of responsibilities
- Automatically highlights urgent or nearly due tasks

### 💰 Money System
- Configure financial goals and obligations
- Track:
  - Real debt
  - Future debt
  - Savings targets
  - Available funds
- Define:
  - Whether items are monthly or distributed
  - Payment mode (monthly vs. accumulated)
  - Total value
- Summarized and full breakdowns available
- Enforces savings discipline and payment planning

---

## Configuration

Organa stores its configuration and data in:

```
~/.config/organa/
```

### Files:
- `config.yml`: Global settings (urgency threshold, daily limits, savings policy, etc.)
- `responsibilities.csv`: List of tasks with required metadata
- `money.yml`: Financial responsibilities and goals
- `logs/`: Optional logs for activity/debugging
- `cache/`: Optional cached summaries

### Example `config.yml`
```yaml
urgency_days: 3
daily_task_limit: 5

money:
  minimum_savings: 100
  responsibilities:
    - name: Rent
      type: real_debt
      value: 450
      mode: monthly
    - name: Emergency Fund
      type: savings
      value: 600
      mode: accumulate
      months: 6
```

---

## Autostart Setup

Organa is designed to run automatically via a Kitty terminal at login.

Example `.desktop` entry in `~/.config/autostart/organizer.desktop`:

```ini
[Desktop Entry]
Type=Application
Exec=kitty --title Organa -e /home/youruser/bin/organa
Hidden=false
NoDisplay=false
X-GNOME-Autostart-enabled=true
Name=Organa Dashboard
```

---

## Build & Install

```bash
git clone https://github.com/yourusername/organa.git
cd organa
cmake -B build
cmake --build build
ln -s $(pwd)/build/organa ~/bin/organa
```

Ensure `~/bin/` is in your `PATH`.
