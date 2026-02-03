Checkout my other widgets:

https://github.com/moshirfakhoury/edgetx-preflighttest-widget

https://github.com/moshirfakhoury/edgetx-flightdash-widget

https://github.com/moshirfakhoury/edgetx-postflight-widget

https://github.com/moshirfakhoury/edgetx-images-widget

Overview

The Service Checklist Widget is designed for RC planes, helicopters, and drones to track maintenance schedules and ensure mechanical checks are completed. Using a user-entered Last Service field and Interval, the widget calculates the next service due date / flight and provides an “in-your-face” alert when maintenance is overdue.
When overdue, it sets a global variable (GV7 FM0 = 1), allowing integration with logical switches to trigger special functions like automatic page selection. This ensures critical maintenance reminders are never missed while keeping the widget unobtrusive when everything is up-to-date.
The widget also supports two service tracking modes, allowing maintenance to be scheduled either by calendar date or by flight count, depending on user preference.

Functions
- Service Tracking (Dual Mode):
  - Date Mode (Mode = 0)
    Enter last service date (DD/MM/YYYY) and service interval (days) to calculate the next service due date.
  - Flight Count Mode (Mode = 1)
    Enter last service flight number and service interval (flights).
    The widget reads a selected flight counter source (e.g. a Global Variable) to determine when the next service is due.
    
- Checklist Display:
  - Predefined safety and mechanical service items are displayed in two columns.
  - There are over 80 checklist items the user can select from.
  - The full list is stored in the Widget Checklist Items.txt file and can be viewed directly on the Radiomaster transmitter
  - The screen can display up to 16 checks at a time.
- Overdue Alerts:
  - Title flashes red and changes to “SERVICE DUE” when maintenance is overdue.
  - Last service and service due values are highlighted in red if overdue, otherwise green.

- Remaining Counter (Days / Flights):
  - A circle on the screen shows the remaining days or flights until the next service, depending on the selected mode.
  - The circle color indicates urgency:
    - Green if > 10 remaining
    - Yellow if <= 10 remaining
    - Red if <= 3 remaining
  - If overdue, the value becomes negative and the label changes to:
    - “Days overdue” (Date Mode)
    - “Flights overdue” (Flight Mode)
      
- Global Variable Output:
  - Optional GV7 output – can be enabled or disabled via widget options.
  - Writes 0 to GV7 FM0 when service is up-to-date.
  - Writes 2 to GV7 FM0 when service is due soon (≤ 10 days / flights).
  - Writes 1 to GV7 FM0 when service is overdue.
  - This allows logical switches and special functions to react to service state (e.g. automatic page load, sound alerts, haptic warnings, etc.).
    
- Flexible Options:
  - Up to 4 parameters can be used to select which checklist items are displayed.
  - A single Interval option is used for both modes:
    - Days in Date Mode
    - Flights in Flight Count Mode
  - A shared Last Service field is used:
    - Date (DD/MM/YYYY) in Date Mode
    - Flight count in Flight Count Mode
      
- Error Handling Messages:
  - Congratulations Message:
    - When a valid new service date or flight count is entered that is greater than the previous value and not in the future, a green “Congratulations! Service Complete” message is displayed.
  - Future Entry Warnings:
    - If a date entered is later than today, a red “Date Entered Is In The Future” message is displayed.
    - If a flight count entered is greater than the current flight counter, a red “Flight Count Is In The Future” message is displayed.
  - Incorrect Entry Errors:
    - If a date entered is earlier than the previous last service date, a red “Date Entered Is Less Than Previous” message is displayed.
    - If a flight count entered is less than the previous last service flight count, a red “Flight Count Is Less Than Previous” message is displayed.
  - Messages appear for a short duration, ensuring visibility without interfering with the main display.

- Date Handling:
  - Handles leap years, month lengths, and accurate date math when calculating service due dates.

Notes
- Designed for EdgeTX 2.11+.
- Only tracks mechanical service items; batteries and electronics are excluded.
- Flight counting itself is external to the widget and is typically handled via logical switches and special functions; the widget only reads the selected counter source.
- Does not modify screen layout; all text positions remain fixed for readability.
- Flashing title and overdue highlighting can be customized in the code (flash rate, colors).
- GV7 FM0 integration allows seamless automation with logical switches and special functions.

Installation
- Dowload the ZIP file
- Extract content from ZIP file
- Copy only the last folder called '' with the main.lua and Readme.txt
- Paste the folder into your SDCard/WIDGETS folder
- If you want to use the sound files provided, copy and pasted them into SDCard/SOUNDS/en folder - you can then assign them to Special Functions

Date Mode:

<img width="495" height="287" alt="image" src="https://github.com/user-attachments/assets/1e0c1487-7c71-428a-8389-7dc740366e7a" />

<img width="502" height="293" alt="image" src="https://github.com/user-attachments/assets/dfc954b5-0979-4730-9c84-d9e13ac9da1c" />

<img width="497" height="290" alt="image" src="https://github.com/user-attachments/assets/e66b69da-de82-499a-9533-0ab21e05354f" />

Fight Counter Mode:

<img width="492" height="287" alt="image" src="https://github.com/user-attachments/assets/ee9c5f67-2aed-4a42-b525-bf0e7d4c2229" />

<img width="496" height="287" alt="image" src="https://github.com/user-attachments/assets/b3c071c3-d2d1-4f3f-800b-a4dcc4adbe24" />

<img width="498" height="292" alt="image" src="https://github.com/user-attachments/assets/c6425d13-4110-4b0e-b771-511f8390a11b" />

Widget Options:

<img width="492" height="287" alt="image" src="https://github.com/user-attachments/assets/bfb3027b-b0c8-4016-a6f8-c6489c26d832" />

<img width="495" height="287" alt="image" src="https://github.com/user-attachments/assets/73c16b4e-d96b-4bd0-870b-5ec4370fdfea" />






















