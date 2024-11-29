# AutoHotkey: Automation At Its Finest ❤️

<p align="center">
<a target="_blank" href="https://www.autohotkey.com/"><img align="center" alt="AutoHotKey" width="90px" style="padding-right:10px;" src="docs/AHK-Icon.svg"/><a/>
<p/>

## Why AutoHotkey Will Change Your Digital Life Forever

Imagine if you could bend your computer to your will, automate mind-numbing tasks, and become a productivity ninja with just a few lines of code. That's exactly what AutoHotkey (AHK) lets you do! 🥷

### What is AutoHotkey?

AutoHotkey is a scripting language that allows you to:
- Easily automate repetitive tasks
- Create custom hotkeys and shortcuts
- Manipulate windows, text, and more
- Save HOURS of your precious time

## Let's Dive into an Epic AHK Script! 🏊‍♂️

### 1. Basic Setup and Includes

```autohotkey
#Requires AutoHotkey v2.0

```

**Why This Matters:**
- `#Requires AutoHotkey v2.0`: Ensures you're using the right version

#### 1.1. What I usually use

```autohotkey
#Warn All, Off
SendMode("Input")  
SetWorkingDir(A_ScriptDir)  
#SingleInstance Force
```
- `#Warn All, Off`: Enables all warning dialogs, but then immediately turns them off. In development, you might want to set this to #Warn to catch potential script issues.
- `SendMode("Input")`: Provides faster, more reliable keyboard input
- `#SingleInstance Force`: Automatically replaces the previous script version when you reload

### 2. Productivity Hotkeys 🚀

```autohotkey
; Minimize current window
#^Down:: WinMinimize "A"


; Navigation Shortcuts
!^Down:: SendInput("^{END}")
!^UP:: SendInput("^{HOME}")
```

**Power Move Breakdown:**
- `!^Down` (Alt + Ctrl + Down): Jumps to the end of the document
Uses *Ctrl + End* key combination
- `!^UP` (Alt + Ctrl + Up): Jumps to the beginning of the document
Uses *Ctrl + Home* key combination

### 3. Text Manipulation Magic ✨

```autohotkey
; Delete entire line left or right
^+Backspace:: {
    SendInput("+{Home}")
    SendInput("{Delete}")
}

^+!Backspace:: {
    SendInput("+{End}")
    SendInput("{Delete}")
}
```

**Coding Superpowers Explained:**
These keyboard shortcuts let you quickly delete text from the cursor to either the start or the end of the line without needing your mouse:

*Ctrl + Shift + Backspace*
Deletes all text to the left of the cursor (from the cursor to the beginning of the line).
    Example:
        Cursor here → `Hello |world`
        Press *Ctrl + Shift + Backspace*
        Result: `|world`

*Ctrl + Shift + Alt + Backspace*
Deletes all text to the right of the cursor (from the cursor to the end of the line).
    Example:
        Cursor here → `Hello| world`
        Press *Ctrl + Shift + Alt + Backspace*
        Result: `Hello|`

#### 3.1. Why this is magical:

- **Speed & Efficiency**: Forget about dragging your mouse or repeatedly pressing backspace or delete. These shortcuts handle entire chunks of text in one go.
- **Perfect for Coding**: If you often need to clear parts of a line in code editors, these shortcuts save time when refactoring or editing.
- **Universal Use**: Works in any text field, editor, or IDE where you write and edit text.

### 4. Personal Data Shortcuts 🤖

```autohotkey
; Quick Personal Info Expansion
:o::id::12345678910
:o::email1::my_email@domain.com
:o::email2::my_email2@domain.com
```

**Efficiency Unlocked:**
- Type `:id` and BAM! Your id number appears
- Quickly fill forms or send repetitive info with shortcuts for emails, phone numbers, and more.
- To expand a snippet, simply type the keyword (e.g., :email1) and watch it auto-complete.

### 5. Date Wizardry 📅

```autohotkey
:*::hoy:: {
    CurrentDateTime := FormatTime(, "yyyy-MM-dd")
    SendInput(CurrentDateTime)
}

:*::nhoy::
{
    CurrentDateTime := FormatTime(, "dd-MM-yyy")
    SendInput(CurrentDateTime)
    return
}


:*::ayer:: {
    today := a_now
    today := DateAdd(today, -1, 'days')
    today := FormatTime(today, "yyyy-MM-dd")
    SendInput(today)
}
```

**Time Travel (Sort Of):**
- `:hoy` instantly types today's date. (Hoy means Today in spanish)
- `:ayer` magically inserts yesterday's date(Ayer means Yesterday in spanish)
- Never manually type dates again!


#### Time Travel Expanded
Here are examples of what each shortcut produces:

- **ISO Dates (yyyy-MM-dd)**:
    :hoy → 2024-11-29 (Today's date)
- **Localized Dates (dd-MM-yyyy)**:
    :nhoy → 29-11-2024 (Today's date)
- **Time (HH:mm)**:
    :hora → 14:45 (Current system time)

##### Why use these formats?
- `yyyy-MM-dd`: Perfect for databases, APIs, or when consistency across systems is required.
- `dd-MM-yyyy`: User-friendly for regions like Europe or Latin America where this format is common.
- `HH:mm`: Quick time insertion for logs or messages.

### 6. Application-Specific Hotkeys 🎯

```autohotkey
#HotIf WinActive("Notepad++ ahk_exe notepad++.exe")
~^s:: {
    Reload()
    return
}
#HotIf
```

**Context is King:**
- These hotkeys only work in specific applications
- In Notepad++, *Ctrl + S* now reloads your script
- Tailored automation for each app!

### 7. Best for Last ⭐

The `~+^r:: Reload()` hotkey is a developer's best friend when working with AutoHotkey scripts. Here's why it's incredibly useful:
Why You Want the Reload Hotkey
Imagine you're in the middle of working on your computer, and you've just made a small tweak to your AutoHotkey script. Without this hotkey, you'd have to:

1. Stop the current script manually
2. Find the script file
3. Double-click to restart it

With `~+^r:: Reload()`, you can:

- Instantly update your script mid-workflow
- Test changes without interrupting your current work
- Save time during script development
- Maintain a seamless productivity experience

**Real-world scenario**: You're coding and realize you want to add a new hotkey or fix a small bug. Instead of breaking your concentration, you simply press *Shift + Ctrl + R*, and your script updates instantly - with zero downtime.
It's like having a instant "refresh" button for your custom computer automation. The ~ ensures the original key combination still works (so *Shift + Ctrl + R* can still do its original function in most apps), while also triggering the script reload.
This single line of code represents the core of AHK's power: **rapid, flexible customization** of your computing environment.

## Getting Started: Your AHK Adventure Begins! 🌟

1. Download AutoHotkey v2.0
2. Create a `.ahk` file
3. Copy these scripts
4. Run and marvel at your new superpowers!

### Pro Tips 💡
- Start small, automate gradually
- Check the official AHK documentation
- Join AHK community forums
- Experiment and have fun!

## Warning: Side Effects May Include 😂
- Extreme productivity
- Jealous co-workers
- Uncontrollable smiling
- Feeling like a computer wizard

**Remember:** With great power comes great... efficiency! 🚀

---

**Disclaimer:** This script is a personal productivity tool. Customize it to fit YOUR workflow! 💪
