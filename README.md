# AutoHotkey: Automation At Its Finest ❤️

<br/>
<p align="center">
<a target="_blank" href="https://www.autohotkey.com/"><img align="center" alt="AutoHotKey" width="90px" style="padding-right:10px;" src="docs/AHK-Icon.svg"/><a/>
<p/>
<br/>

- [AutoHotkey: Automation At Its Finest ❤️](#autohotkey-automation-at-its-finest-️)
  - [Why AutoHotkey Will Change Your Digital Life Forever](#why-autohotkey-will-change-your-digital-life-forever)
    - [What is AutoHotkey?](#what-is-autohotkey)
  - [Let's Dive into an Epic AHK Script! 🏊‍♂️](#lets-dive-into-an-epic-ahk-script-️)
    - [1. Basic Setup and Includes](#1-basic-setup-and-includes)
      - [1.1. What I usually use](#11-what-i-usually-use)
    - [2. Productivity Hotkeys 🚀](#2-productivity-hotkeys-)
    - [3. Text Manipulation Magic ✨](#3-text-manipulation-magic-)
      - [3.1. Why this is magical:](#31-why-this-is-magical)
    - [4. Personal Data Shortcuts 🤖](#4-personal-data-shortcuts-)
    - [5. Date Wizardry 📅](#5-date-wizardry-)
      - [5.1. Time Travel Expanded](#51-time-travel-expanded)
        - [5.1.1. Why use these formats?](#511-why-use-these-formats)
    - [6. Application-Specific Hotkeys 🎯](#6-application-specific-hotkeys-)
      - [6.1. Using AutoHotkey Window Spy 🕵️‍♂️](#61-using-autohotkey-window-spy-️️)
    - [7. Reloading is your lord and savior ⭐](#7-reloading-is-your-lord-and-savior-)
    - [8. Language and Math Shortcuts 🌐➕](#8-language-and-math-shortcuts-)
      - [8.1. Character Expansions to Other Languages 🌍](#81-character-expansions-to-other-languages-)
      - [8.2 Mathematical Symbol Shortcuts 🧮](#82-mathematical-symbol-shortcuts-)
        - [8.2.1. Basic Mathematical Symbols](#821-basic-mathematical-symbols)
        - [8.2.2. Set Theory and Logic Symbols](#822-set-theory-and-logic-symbols)
        - [8.2.3. Greek Letters](#823-greek-letters)
      - [8.4 Obsidian and LaTeX Integrations 📝](#84-obsidian-and-latex-integrations-)
      - [8.5 Contextual Typing Exclusions 🛡️](#85-contextual-typing-exclusions-️)
        - [8.5.1. Key Details](#851-key-details)
      - [8.6 Bonus: Quick Text Corrections 🔧](#86-bonus-quick-text-corrections-)
        - [8.6.1. Why These Shortcuts Matter](#861-why-these-shortcuts-matter)
    - [9. Smart App Launching & Window Management 🚀](#9-smart-app-launching--window-management-)
    - [10. Visual GUIs as Contextual Notifications 🎨](#10-visual-guis-as-contextual-notifications-)
  - [Getting Started: Your AHK Adventure Begins! 🌟](#getting-started-your-ahk-adventure-begins-)
    - [Pro Tips 💡](#pro-tips-)
  - [Warning: Side Effects May Include 😂](#warning-side-effects-may-include-)


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


#### 5.1. Time Travel Expanded
Here are examples of what each shortcut produces:

- **ISO Dates (yyyy-MM-dd)**:
    :hoy → 2024-11-29 (Today's date)
- **Localized Dates (dd-MM-yyyy)**:
    :nhoy → 29-11-2024 (Today's date)
- **Time (HH:mm)**:
    :hora → 14:45 (Current system time)

##### 5.1.1. Why use these formats?
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

#### 6.1. Using AutoHotkey Window Spy 🕵️‍♂️

To identify window titles, class names, or executables, follow these steps:

1. **Open Window Spy**:
   - Launch **Window Spy** from your AutoHotkey installation folder, or run it from an AHK script:
     ```autohotkey
     Run, WindowSpy.ahk
     ```

2. **Activate the Target Application**:
   - Switch to the application you want to analyze and ensure its window is active.

3. **Review Window Spy Output**:
   Key details are displayed:
   - **Window Title**: The full title of the current window.
   - **Class Name**: Shown as `ahk_class [Class Name]`, e.g., `ahk_class Chrome_WidgetWin_1`.
   - **Executable Name**: Shown as `ahk_exe [Executable Name]`, e.g., `ahk_exe Code.exe`.

4. **Choose the Identifier**:
   - Use `ahk_exe` for precision (e.g., `datagrip64.exe`).
   - Use `ahk_class` for broader matches across similar windows.
   - Use partial titles for specific windows if necessary (e.g., `"SQL"`).

5. **Apply in Your Script**:
   Example of disabling hotkeys for Visual Studio Code:
   ```autohotkey
   #HotIf NOT WinActive("ahk_exe Code.exe")
   ```

This method ensures accurate targeting of windows, preventing unwanted hotkey interference while maintaining efficiency across your workflows.

### 7. Reloading is your lord and savior ⭐

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

### 8. Language and Math Shortcuts 🌐➕

#### 8.1. Character Expansions to Other Languages 🌍

These shortcuts help you quickly type accented characters and special punctuation without switching keyboard layouts:

| Shortcut | Result | Description |
|----------|--------|-------------|
| `:ni`    | `ñ`    | Lowercase ñ |
| `:aa`    | `á`    | Lowercase á |
| `:ea`    | `é`    | Lowercase é |
| `:ia`    | `í`    | Lowercase í |
| `:oa`    | `ó`    | Lowercase ó |
| `:ua`    | `ú`    | Lowercase ú |
| `:?`     | `¿`    | Inverted question mark |
| `:!`     | `¡`    | Inverted exclamation mark |

**Pro Tip**: Uppercase versions are also supported (e.g., `:NI` for `Ñ`)

#### 8.2 Mathematical Symbol Shortcuts 🧮

Transform your typing into a mathematical notation powerhouse with these concise symbol expansions:

##### 8.2.1. Basic Mathematical Symbols
| Shortcut   | Symbol | Meaning |
|------------|--------|---------|
| `:cross`   | `×`    | Multiplication |
| `:perp`    | `⊥`    | Perpendicular |
| `:tick`    | `✓`    | Checkmark |
| `:to`      | `→`    | Implies/Goes to |
| `:geq`     | `≥`    | Greater than or equal to |
| `:leq`     | `≤`    | Less than or equal to |
| `:neq`     | `≠`    | Not equal to |
| `:aprox`   | `≅`    | Approximately equal |
| `:pm`      | `±`    | Plus-minus |
| `:inf`     | `∞`    | Infinity |

##### 8.2.2. Set Theory and Logic Symbols
| Shortcut   | Symbol | Meaning |
|------------|--------|---------|
| `:forall`  | `∀`    | For all |
| `:exists`  | `∃`    | There exists |
| `:in`      | `∈`    | Element of |
| `:or`      | `∨`    | Logical OR |
| `:and`     | `∧`    | Logical AND |
| `:subset`  | `⊂`    | Subset of |

##### 8.2.3. Greek Letters
| Shortcut   | Symbol | Description |
|------------|--------|-------------|
| `:pi`      | `π`    | Pi |
| `:omega`   | `ω`    | Lowercase omega |
| `:Omega`   | `Ω`    | Uppercase omega |
| `:alpha`   | `α`    | Alpha |
| `:beta`    | `β`    | Beta |
| `:delta`   | `δ`    | Lowercase delta |
| `:Delta`   | `Δ`    | Uppercase delta |
| `:sigma`   | `σ`    | Sigma |
| `:lambda`  | `λ`    | Lambda |

#### 8.4 Obsidian and LaTeX Integrations 📝

For those using Obsidian or writing LaTeX documents, these shortcuts provide quick text formatting and mathematical notation:

| Shortcut   | Expansion | Use Case |
|------------|-----------|----------|
| `:bold`    | `\textbf{}` | Bold text in LaTeX |
| `:vec`     | `\vec{}` | Vector notation |
| `:frac`    | `\frac{}{}` | Fraction |
| `:sum`     | `\displaystyle\sum` | Summation |
| `:lim`     | `\lim_{}` | Limit |
| `:integ1`  | `∫`        | Simple integral |
| `:integ2`  | `∫^{}_{}` | Definite integral |

#### 8.5 Contextual Typing Exclusions 🛡️

```autohotkey
#HotIf NOT (WinActive("ahk_class SunAwtFrame") or WinActive("SQL") or 
            WinActive("Visual Studio Code") or WinActive("Azure") or 
            WinActive("ahk_exe datagrip64.exe") or 
            WinActive("ahk_exe FSD-WinGDK-Shipping.exe"))
```

This configuration ensures hotkeys are disabled when certain applications are active. It prevents interference with your workflow in environments like coding, database management, or gaming.

##### 8.5.1. Key Details
- **`#HotIf`**: Creates conditional hotkeys based on window context.
- **`NOT`**: Disables hotkeys when the conditions inside the parentheses are met.
- **`WinActive()`**: Checks if a specific window is currently active.
  - **`ahk_class`**: Identifies windows by their internal class names.
  - **`ahk_exe`**: Targets applications by their executable names.
  - Text like "SQL" matches partial window titles.

For example:
- **`ahk_class SunAwtFrame`**: Often Java-based apps like IntelliJ.
- **`ahk_exe datagrip64.exe`**: Refers to DataGrip, a database IDE.
- **`FSD-WinGDK-Shipping.exe`**: Likely a game executable.

By excluding these applications, hotkeys stay relevant only where they’re needed.

#### 8.6 Bonus: Quick Text Corrections 🔧

Automatic corrections for common typos and accented words:

| Typo         | Correction   |
|--------------|--------------|
| `nomina`     | `nómina`     |
| `preambulo`  | `preámbulo`  |
| `semantica`  | `semántica`  |
| `implicita`  | `implícita`  |

##### 8.6.1. Why These Shortcuts Matter

These AutoHotkey shortcuts transform your typing experience by:
- Reducing repetitive keystrokes
- Making mathematical and Spanish typing faster
- Providing quick access to complex symbols
- Customizing your workflow across different applications

**Remember:** Automation is about making technology work for you, not the other way around! 💻✨

### 9. Smart App Launching & Window Toggling 🚀

With a single hotkey, you get **multiple intelligent behaviors**:

1. **App Not Running?** → Launch it
2. **App Running but Not Active?** → Focus it
3. **App Already Active?** → Minimize it (toggle off)

```autohotkey
#W:: ; Win + W → WhatsApp Launcher & Toggle
{
    if (!WinExist("WhatsApp")) {
        Run("C:\Path\To\Your\AppShortcut.lnk")
        WinWait("WhatsApp")
        WinActivate("WhatsApp")
        WinWaitActive("WhatsApp")
        Sleep(75)
        Send("+{TAB}") ; optional: moves focus to content pane
    }
    else if (!WinActive("WhatsApp")) {
        WinActivate("WhatsApp")
        WinWaitActive("WhatsApp")
    } else {
        WinMinimize("WhatsApp")
    }
    return
}
```

#### Why this is 🔥:

* **One Key, Three Functions**: Switch between launching, focusing, or minimizing with no extra keys.
* **No Dupes**: Avoids opening the same app twice.
* **Context-Aware**: Automatically knows what you want based on app state.
* **Extendable**: Works great with any app (Discord, Obsidian, VS Code, etc.)

#### Pro Tips:

* Add `WinWait()` after `Run()` to ensure the window is ready before interacting.
* Use `Sleep()` to give the app time to load UI elements, especially with web-based apps.

### 10. Visual GUIs as Contextual Notifications

```autohotkey
; Display a modern Windows 11-style notification
myGui := Gui()
myGui.Opt("-Caption +AlwaysOnTop +ToolWindow")
myGui.SetFont("s11 cWhite", "FiraCode Nerd Font")
myGui.Add("Text", "x20 y20 w400", "Remember to review your key points!")
myGui.Show("AutoSize")

; Apply acrylic blur effect (Windows 10/11)
EnableAcrylic(myGui.Hwnd, 0xCC090C13)
```

### What are GUIs?

GUIs (`Gui()`) let you create **simple visual interfaces** directly from your scripts — anything from floating notifications to interactive forms. No need for compiling or external tools.

In this example, we use a GUI as a **custom visual notification**, with professional fonts and a translucent background, that can appear automatically when you launch an app or trigger a specific action.

---

### 🧠 Why use this?

You can use GUIs as dynamic notifications or helpful overlays that appear exactly when you need them. For example:

* Show **reminders or tips** when launching an app
* Indicate the **status of an automation**
* Display **quick reference notes** without switching windows
* Provide **basic interaction** (like buttons or confirmations)

---

### 🎯 Benefits of using GUIs as notifications:

* **Fully customizable**: Colors, fonts, size, position, icons, buttons, etc.
* **Seamless integration**: Part of the same script that launches or manages your apps
* **Modern look**: Supports blur, transparency, rounded corners (just like Windows 11)
* **Minimal yet helpful**: Stays visible when needed, out of the way when not
* **Auto-dismiss or manual close**: Great for keeping focus

---

### 💡 Real-world use cases:

* You launch an app → a GUI appears with tips, shortcuts, or next steps
* You run a script → a GUI reminds you of your daily tasks
* You switch environments or profiles → the GUI shows relevant settings
* You detect an event (like plugging in headphones) → a personalized notification pops up

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

### Warning ⚠️
Side Effects May Include:
- Extreme productivity
- Jealous co-workers
- Uncontrollable smiling
- Feeling like a computer wizard

**Remember:** With great power comes great... efficiency! 🚀

---

**Disclaimer:** This script is a personal productivity tool. Customize it to fit YOUR workflow! 💪
