Checkout my other widgets:

https://github.com/moshirfakhoury/edgetx-preflighttest-widget

https://github.com/moshirfakhoury/edgetx-flightdash-widget

https://github.com/moshirfakhoury/edgetx-postflight-widget

https://github.com/moshirfakhoury/edgetx-images-widget

Overview

The Service Checklist Widget is designed for RC planes, helicopters, and drones to track maintenance schedules and ensure mechanical checks are completed. Using a user-entered last service date and interval, the widget calculates the next service due date and provides an “in-your-face” alert when maintenance is overdue.
When overdue, it sets a global variable (GV7 FM0 = 1), allowing integration with logical switches to trigger special functions like automatic page selection. This ensures critical maintenance reminders are never missed while keeping the widget unobtrusive when everything is up-to-date.

Functions
- Service Tracking: Enter last service date (DD/MM/YYYY) and service interval (days) to calculate due date.
- Checklist Display: Predefined safety and mechanical service items are displayed in two columns.
  - There are over 80 checklist items the user can select from.
  - The screen can display up to 16 checks at a time.
- Overdue Alerts:
  - Title flashes red/white and changes to “SERVICE DUE” when maintenance is overdue.
  - Last service and due dates are highlighted in red if overdue, otherwise green.
- Days Counter:
  - A circle on the screen shows the number of days until the next service.
  - The circle color indicates urgency: green if ≥15 days remaining, yellow if <15 days, red if <7 days.
  - If overdue, the number is negative and the label changes to “Days overdue”. 
- Global Variable Output:
  - Optional GV7 output – can be enabled or disabled via widget options.
  - Writes 1 to GV7 FM0 when service is overdue.
  - Writes 0 to GV7 FM0 when service is up-to-date.
  - Writes 2 to GV7 FM0 when service is due soon (≤ 10 days)
  - Can be linked to logical switches for triggering special functions (e.g., automatic page load / sound alert).
- Flexible Options: Up to 3 parameters can be used to select which checklist items are displayed.
- Date Handling: Handles leap years, month lengths, and adds days to last service date to calculate the next due date.

Notes
- Designed for EdgeTX 2.11+.
- Only tracks mechanical service items; batteries and electronics are excluded.
- Does not modify screen layout; all text positions remain fixed for readability.
- Flashing title and overdue highlighting can be customized in the code (flash rate, colors).
- GV7 FM0 integration allows seamless automation with logical switches and special functions.
