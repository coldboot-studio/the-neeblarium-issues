# [Feature] Auto-Open Tray on Handle Hover

## Problem
Current interaction requires explicit LMB click on handle to open tray, adding unnecessary friction to the core gameplay loop. Players frequently open/close tray when managing resources, making this repetitive action a pain point.

## Proposed Solution
Implement auto-open behavior when cursor hovers over tray handle:
- **Delay:** 0.3-0.5s hover time before opening (prevents accidental triggers)
- **Visual feedback:** Subtle handle animation on hover (scale/glow) to communicate interactivity
- **Cancellation:** Moving cursor off handle before delay completes cancels auto-open
- **Tunable:** Add `GlobalTuning.tray_auto_open_delay` for live adjustment

## Acceptance Criteria
- [ ] Tray automatically opens after hovering handle for configured duration
- [ ] Hover timer resets if cursor leaves handle area before delay completes
- [ ] Handle shows subtle hover animation (scale bounce or glow)
- [ ] Auto-open delay is tunable via `GlobalTuning.tray_auto_open_delay`
- [ ] Manual LMB click still works immediately (no delay)
- [ ] No accidental opens when cursor briefly passes over handle
- [ ] Works with existing right-click quick-grab system

## Affected Files
- `ui/InteractionTray.gd` - Add hover timer logic and auto-open trigger
- `GlobalTuning.gd` - Add `tray_auto_open_delay` export parameter
- `ui/InteractionTray.tscn` - Potentially add animation resources for handle

## Design Notes
This is Phase 1 of larger tray/dropper UX revamp:
1. ✅ **Auto-open on hover (THIS ISSUE)**
2. Future: drawing_picker cursor on bins
3. Future: Juicy pickup pop-up feedback
4. Future: Hide dropper until leaving tray

## Related Issues
Part of tray/dropper UX modernization initiative (November 2025)
