# Murder Board Changelog


## 1.2.1 - 2025-12-14

### Fixed

- Custom fonts now render in the font select dropboxes

### Changed

- Removed delete confirmaiton dialoge when deletign items from the board.

## 1.2.0 - 2025-12-14

### Added Features

**Custom Board Background Images**
- You can now add any image you want to act as the board background. It will sit below everything on the canvas at the canvas' center and remain in place when pannning or zooming.
- You can scale the image up or down via the slider in Board Settings. This can be used to fine tune how things look or how big of a board you want.

**New Text Items**
- Text items can now be created directely and moved arounf the board
- Text items do not accept connecitons by default so that they can easily positioned near and over other items.
- Text itmes have drag handles to control word wrap if desired.
- Scale in Edit or by using the right-click context menu slider.
- Any font you have installed in Foundy can be used. (see below)

**Foundry Font Integration**
- All items and modal panels now use font selectors that pull directly from Foundry and your custom fonts.

**File Picker Support**
- Multi-platform file picker integration for Forge, Sqyre, and standard Foundry
- Handlebars helper `{{#file-picker type="image"}}` for reusable file picker buttons
- Added better file picker support to item dialogs and board settings dialog
- Unified file picker implementation across all dialogs ahead of Defiler integration.

**Color Picker Improvements**
- Module-wide implementaiton of 5 last used color swatches in addition to picker

**Foundry Native Element Dragging**
- Added ability to drag many Foundry elements directly to the canvas. This will be expanded greatly in upcoming releases.
- Added ability to drag Actors, Items, Journals, Journal Pages, and Scenes directly to Murder Board. These all behave is specific ways according to type.
  - Actors use actor portrait
  - Items use item image
  - Journals create Document and use Journal titel as initial text.
  - Journal Text Pages create Document and use the text of the page.
  - Journal Image Pages create Image and use the image of the page.
  - Journal Page PDFs and Videos not implemented yet.
 



### Bugs Squashed

**Canvas & Layout**
- Fixed canvas display issues - now properly fills entire window
- Fixed gray background artifacts on load and resize
- Fixed window layout cascade via `setPosition()` trigger
- Removed window position/size memory system

**Context Menu**
- Fixed critical stale closure bug affecting multiple context menu handlers:
  - Fastener buttons no longer reset when changing other options
  - Font color buttons maintain state across multiple changes
  - Shadow buttons preserve settings when switching between options
  - Size buttons no longer reset when changing other properties
  - Paper type buttons maintain selection
  - Document size buttons properly apply changes
  - Document effect buttons apply effects without reverting previous changes
  - Effect intensity slider and seed slider work independently without interfering
  - Border color buttons apply colors without resetting image size
- Fixed issue where changing one context menu option would reset others to stale values

**Image Handling**
- Fixed transparent image rendering (removed blocking white background)
- Transparent images now display correctly with proper alpha channels
- Fixed item-image dialog layout (button and input now stack vertically)

**Document Sizing**
- Added missing `xlarge` document size configuration
- X-large documents now properly larger than large documents
- Fixed sizing mismatch between UI options and canvas rendering

**UI & Styling**
- Removed toolbar hover effect that turned white in dark mode
- Dark mode styling now stable and consistent
- Fixed input field naming mismatches

**Error Handling**
- Fixed `addRecentColor()` error in Document Item Dialog (changed to `addColorToPalette()`)
- Fixed "Please provide an image URL" error when dragging scenes without images


## 1.0.0 - 2025-12-3

### Initial Release
