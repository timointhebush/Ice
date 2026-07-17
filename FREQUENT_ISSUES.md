# Frequent Issues <!-- omit in toc -->

- [Items are moved to the always-hidden section](#items-are-moved-to-the-always-hidden-section)
- [Floe appears to remove an item](#floe-appears-to-remove-an-item)
- [Floe does not remember an item's order](#floe-does-not-remember-an-items-order)
- [How do I solve the automatically hidden menu bar error?](#how-do-i-solve-the-automatically-hidden-menu-bar-error)

## Items are moved to the always-hidden section

By default, macOS adds new items to the far left of the menu bar, which is also
the location of Floe's always-hidden section. Most apps remember the positions
of their items, but some do not. macOS treats those items as new every time they
appear, which can place them in the always-hidden section.

Floe cannot reliably restore the location of every item that macOS rearranges.

## Floe appears to remove an item

Floe cannot move or remove menu bar items. macOS likely placed the item in the
always-hidden section. Option-click the Floe icon to show that section, then
Command-drag the item into a different section.

## Floe does not remember an item's order

Some menu bar apps do not preserve their own item order. Floe cannot restore an
item's previous location when macOS treats it as newly added.

## How do I solve the automatically hidden menu bar error?

1. Open **System Settings** on your Mac.
2. Go to **Control Center**.
3. Set **Automatically hide and show the menu bar** to **Never**.
4. Update your menu bar items in Floe.
5. Restore your preferred menu bar hiding setting.

![Disable Menu Bar Hiding](https://github.com/user-attachments/assets/74c1fde6-d310-4fe3-9f2b-703d8ccb636a)
