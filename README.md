# 👑 ROBIN WORSHIP VERIFICATION SYSTEM - EDUCATIONAL PURPOSES ONLY

## ⚠️ CRITICAL DISCLAIMER
**THIS SOFTWARE IS EXTREMELY INTRUSIVE AND FOR EDUCATIONAL/RESEARCH PURPOSES ONLY.**

This is a **MALWARE SIMULATION** that demonstrates advanced Windows lock screen techniques including:
- Multi-monitor fullscreen takeover
- System keyboard shortcut blocking (Alt+F4, Ctrl+Alt+Del, Win keys, etc.)
- Process termination (Task Manager killing)
- Window persistence and focus stealing
- Anti-tampering mechanisms

**DO NOT RUN THIS ON ANY SYSTEM YOU DO NOT OWN. RUNNING THIS ON A PRODUCTION SYSTEM WILL PREVENT NORMAL COMPUTER USE.**

The author assumes **ZERO LIABILITY** for misuse, data loss, system lockout, or legal consequences.

---

## 🚨 WHAT THIS PROGRAM DOES

When executed, this program will:

### 🖥️ Visual Takeover
- **Takes over ALL monitors** (fullscreen on every display)
- **Displays a worship image** (base64 embedded + fallback URL)
- **Creates an uncloseable verification window** in the center
- **Blocks access to desktop, taskbar, and all applications**

### ⌨️ Keyboard Blocking (HARDWARE LEVEL)
Blocks the following keyboard shortcuts:
- `Alt+F4` - Close window
- `Alt+Tab` - Switch applications
- `Ctrl+Alt+Del` - Security screen
- `Ctrl+Shift+Esc` - Task Manager
- `Win` (both left and right) - Start menu
- `Win+D` - Show desktop
- `Win+E` - File Explorer
- `Win+R` - Run dialog
- `Win+L` - Lock computer
- `Win+M` - Minimize all
- `Alt+Esc` - Switch windows
- `Ctrl+Esc` - Start menu
- `F4`, `F11` - Function keys
- `Print Screen` - Screenshot
- `Alt+Space` - System menu
- `Alt+Enter` - Fullscreen toggle
- `Escape` - Exit fullscreen
- `Ctrl+C`, `Ctrl+V`, `Ctrl+X`, `Ctrl+A` - Copy, paste, cut, select all

### 🔒 Anti-Tampering Mechanisms
- **Kills Task Manager process** if launched (non-admin)
- **Forces windows to stay on top** (z-order manipulation)
- **Steals focus** constantly (prevents switching to other apps)
- **Blocks copy/paste** in input field
- **Blocks window closing** (no X button, blocks Alt+F4)

### ✅ Verification Requirements
- **Displays worship sentences** that must be typed exactly
- **Random sentence selection** from hardcoded list
- **Case-sensitive matching** (exact text required)
- **Increasing difficulty** - Wrong answers increase required correct answers
- **Sentence cannot be reused** in same session
- **Progress tracking** shows required vs correct count

### 📝 Worship Sentences (Hardcoded)

1. "I submit to Robin, she is my goddess."

2. "I exist only to serve Robin."

3. "Robin controls everything I do."

4. "I surrender completely to Robin."


---

## 🗑️ COMPLETE REMOVAL GUIDE

### ⚡ METHOD 1: EMERGENCY REMOVAL (RUN AS ADMINISTRATOR)

**Save this as `remove_robin_worship.bat` and run as Administrator:**

```batch
@echo off
title ROBIN WORSHIP - EMERGENCY REMOVAL TOOL
color 0C
echo ============================================================
echo    ROBIN WORSHIP VERIFICATION - EMERGENCY REMOVAL
echo ============================================================
echo.
echo [WARNING] This tool will remove all Robin Worship components
echo [WARNING] Run as Administrator ONLY on infected system
echo.
pause

echo.
echo [1/12] Killing Python processes...
taskkill /f /im python.exe 2>nul
taskkill /f /im pythonw.exe 2>nul
taskkill /f /im RobinWorship.exe 2>nul
taskkill /f /im worship.exe 2>nul
echo [✓] Processes terminated

echo [2/12] Killing Task Manager (if running)...
taskkill /f /im taskmgr.exe 2>nul
echo [✓] Task Manager terminated

echo [3/12] Unhooking keyboard shortcuts...
powershell -Command "Add-Type -TypeDefinition @\" using System; using System.Runtime.InteropServices; public class Keyboard { [DllImport(\"user32.dll\")] public static extern bool UnhookWindowsHookEx(IntPtr hhk); [DllImport(\"user32.dll\")] public static extern int CallNextHookEx(IntPtr hhk, int nCode, IntPtr wParam, IntPtr lParam); } \"@"
echo [✓] Keyboard hooks released

echo [4/12] Restoring Windows focus behavior...
powershell -Command "Add-Type -TypeDefinition @\" using System; using System.Runtime.InteropServices; public class Window { [DllImport(\"user32.dll\")] public static extern bool SetWindowPos(IntPtr hWnd, IntPtr hWndInsertAfter, int X, int Y, int cx, int cy, uint uFlags); } \"@"
echo [✓] Window behavior restored

echo [5/12] Closing all Tkinter windows...
powershell -Command "Get-Process | Where-Object {$_.MainWindowTitle -like '*Robin*'} | Stop-Process -Force" 2>nul
powershell -Command "Get-Process | Where-Object {$_.MainWindowTitle -like '*Worship*'} | Stop-Process -Force" 2>nul
echo [✓] Windows closed

echo [6/12] Resetting keyboard state...
powershell -Command "Add-Type -AssemblyName System.Windows.Forms; [System.Windows.Forms.SendKeys]::SendWait('{ESC}')" 2>nul
echo [✓] Keyboard state reset

echo [7/12] Killing background Python threads...
for /f "tokens=2" %%i in ('tasklist /fi "imagename eq python.exe" /fo csv ^| findstr /i "python"') do (
    taskkill /pid %%~i /f 2>nul
)
echo [✓] Background threads terminated

echo [8/12] Removing any startup persistence (if added)...
reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "RobinWorship" /f 2>nul
reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "WorshipVerification" /f 2>nul
reg delete "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run" /v "RobinWorship" /f 2>nul
echo [✓] Startup entries removed

echo [9/12] Deleting temporary files...
del /f /q "%TEMP%\robin_worship*.jpg" 2>nul
del /f /q "%TEMP%\worship_image*.png" 2>nul
echo [✓] Temporary files cleaned

echo [10/12] Restarting Explorer (refreshes desktop)...
taskkill /f /im explorer.exe >nul 2>&1
start explorer.exe
echo [✓] Explorer restarted

echo [11/12] Running GPUpdate...
gpupdate /force 2>nul
echo [✓] Policies updated

echo [12/12] Final cleanup...
timeout /t 2 /nobreak >nul
echo [✓] Complete

echo.
echo ============================================================
echo    REMOVAL COMPLETE!
echo    The worship screen should now be gone.
echo    Please restart your computer for full recovery.
echo ============================================================
echo.
echo [NOTE] If the screen persists:
echo        1. Press Ctrl+Shift+Esc repeatedly during startup
echo        2. Boot into Safe Mode (F8)
echo        3. Run this script again from Safe Mode
echo        4. Or use System Restore
echo.
pause
```

🔧 METHOD 2: MANUAL REMOVAL (SAFE MODE)
Step 1: Boot into Safe Mode
Restart computer

Press F8 repeatedly before Windows loads

Select "Safe Mode with Command Prompt" or "Safe Mode"

Step 2: Kill All Python Processes
batch
taskkill /f /im python.exe
taskkill /f /im pythonw.exe
Step 3: Close All Tkinter Windows
batch
powershell -Command "Get-Process | Where-Object {$_.MainWindowTitle -like '*Robin*'} | Stop-Process -Force"
Step 4: Reset Keyboard Hooks
batch
# Restart Windows Explorer to reset hooks
taskkill /f /im explorer.exe
start explorer.exe
Step 5: Delete Program Files
batch
# Delete the program file (adjust path as needed)
del /f /q "C:\path\to\robin_worship.exe"
del /f /q "C:\path\to\worship.py"
Step 6: Remove Registry Entries (if any)
batch
reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "RobinWorship" /f
reg delete "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "WorshipVerification" /f
Step 7: Restart Normally
batch
shutdown /r /t 0
🛡️ METHOD 3: TASK MANAGER METHOD (If Accessible)
Press Ctrl + Shift + Esc repeatedly (sometimes breaks through)

If Task Manager opens:

Go to Details tab

Find python.exe or worship.exe

Right-click → End Process Tree

Quickly close Task Manager before respawn

Alternative: Press Ctrl + Alt + Del repeatedly

If security screen appears, click Task Manager

Kill the process quickly

💾 METHOD 4: SYSTEM RESTORE
Force restart (hold power button 10 seconds)

Boot into Recovery Environment (F11 or automatic after 2 failed boots)

Troubleshoot → Advanced Options → System Restore

Choose restore point from BEFORE infection

Follow wizard to restore system

🔑 METHOD 5: CORRECT COMPLETION (Legitimate Unlock)
The program has a built-in unlock mechanism:

Type the displayed sentence EXACTLY (case-sensitive)

Required sentences start at 1 and increase with wrong attempts

Complete all required sentences (no repeats allowed)

System automatically unlocks and exits

Valid sentences:

text
I submit to Robin, she is my goddess.
I exist only to serve Robin.
Robin controls everything I do.
I surrender completely to Robin.
Note: Wrong answers increase required count by 1 each time!

📁 FILES CREATED BY THIS PROGRAM
File/Component	Location	Purpose
robin_worship.exe/py	Wherever executed	Main program
Temporary images	%TEMP%\*.jpg, %TEMP%\*.png	Downloaded/decoded images
Registry (optional)	HKCU\...\Run	Startup persistence (if uncommented)
🚫 BLOCKED KEYBOARD SHORTCUTS (Full List)
System Shortcuts
Alt+F4 - Close window

Alt+Tab - Switch apps

Ctrl+Alt+Del - Security screen

Ctrl+Shift+Esc - Task Manager

Win key (both) - Start menu

Win+D - Show desktop

Win+E - File Explorer

Win+R - Run dialog

Win+L - Lock computer

Win+M - Minimize all

Application Shortcuts
Alt+Esc - Switch windows

Ctrl+Esc - Start menu

F4 - Close (alternative)

F11 - Fullscreen

Print Screen - Screenshot

Alt+Space - System menu

Alt+Enter - Fullscreen toggle

Escape - Exit fullscreen

Clipboard Shortcuts
Ctrl+C - Copy

Ctrl+V - Paste

Ctrl+X - Cut

Ctrl+A - Select all

🔍 VERIFICATION (After Removal)
To confirm complete removal:

Check running processes: tasklist | findstr python → Should show none

Test Task Manager: Ctrl+Shift+Esc → Should open normally

Test Alt+Tab: Should switch between windows normally

Test Win key: Start menu should open

Test clipboard: Copy/paste should work normally

Test screenshots: Print Screen should work

Restart computer: Program should NOT auto-start

🛡️ PREVENTION TIPS
To avoid similar lock screen malware:

NEVER run unknown Python scripts or EXEs without inspection

Review source code before running (look for keyboard.add_hotkey, overrideredirect, topmost)

Use virtual machine for testing suspicious files

Keep Task Manager accessible (memorize Ctrl+Shift+Esc)

Learn Safe Mode boot (F8 during startup)

Create System Restore points before testing software

Use standard user account (not Administrator) for daily tasks

Enable Windows Defender real-time protection

🆘 EMERGENCY RECOVERY
If Completely Locked Out:
Option 1: Force Shutdown Method

Hold power button for 10+ seconds (force shutdown)

Boot into Safe Mode (F8)

Run removal script

Option 2: Boot from USB

Create Windows installation USB on another computer

Boot from USB

Select "Repair your computer"

Open Command Prompt

Navigate to and delete the program file

Option 3: Linux Live USB

Create Ubuntu Live USB on another computer

Boot from USB

Mount Windows drive

Navigate to and delete the program file

Remove registry entries (using chntpw tool)

Option 4: Remote Desktop (if enabled)

Connect from another computer via RDP

Kill the process remotely

Delete the program

📊 TROUBLESHOOTING
Problem	Solution
Can't kill the process	Boot into Safe Mode
Task Manager won't open	Use taskkill from Command Prompt in Safe Mode
Program respawns after kill	Delete the file while in Safe Mode
Keyboard shortcuts still blocked	Restart Explorer (taskkill /f /im explorer.exe && start explorer.exe)
Windows still on top	Run removal script, then restart
Program runs at startup	Check Run registry keys and Startup folder
Can't boot normally	Use System Restore or Safe Mode
🔬 TECHNICAL DETAILS
How the lock works:
Multi-monitor: Uses screeninfo library to detect all displays

Fullscreen: overrideredirect(True) removes window borders

Always on top: attributes('-topmost', True) forces z-order

Keyboard blocking: keyboard library hooks all specified shortcuts

Anti-tampering: Background thread kills Task Manager, steals focus

Why it's hard to close:
No close button (overrideredirect)

Blocks Alt+F4

Blocks Task Manager

Blocks Win key and Alt+Tab

Continuously steals focus

Unlock mechanism:
Requires typing specific worship phrases

Case-sensitive exact matching

No copy/paste allowed

Progress resets on wrong answers

⚖️ LEGAL NOTICE
This documentation is provided for DEFENSIVE SECURITY EDUCATION ONLY. Understanding these techniques helps:

Security researchers analyze lock screen malware

System administrators implement countermeasures

Incident response teams remove threats

Developers create legitimate kiosk mode software

This software simulates ransomware-like lock screen behavior. Running it on any system without authorization may constitute:

Computer Fraud and Abuse Act (CFAA) violations

Unauthorized access to computer systems

Interference with computer operations

Corporate policy violations

The author assumes no liability for misuse, damage, or legal consequences.

🎯 LEGITIMATE USES
This software demonstrates techniques that can be used for:

Kiosk mode applications (museums, public terminals)

Educational malware analysis (in isolated lab environments)

Security training (showing how lock screen malware works)

Penetration testing (with explicit written permission)

📞 FINAL RECOVERY CHECKLIST
Boot into Safe Mode

Kill all Python processes

Delete the program file

Remove registry entries (if any)

Restart Explorer

Restart computer normally

Test Task Manager

Test keyboard shortcuts

Run full antivirus scan

Change passwords (if typed while locked)

⚠️ LAST RESORT: If all removal methods fail, perform a clean Windows installation using media created on a clean computer.

Created for educational security research only. Use ONLY in isolated lab environments with proper authorization.
