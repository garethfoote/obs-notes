---
share: true
category: TNA/Sprints
---

# Tree view research
- [[UX Research - Tree view design pattern]]

# Accessibility Features
- [x] **Keyboard navigation**
- [x] Add `aria-multiselectable` to tree
- [x] Add `aria-selected` to all nodes
	In multi-select trees, all selected tree items have `aria-selected="true"` set and all tree item nodes that are selectable but not currently selected have `aria-selected="false"` set. Do not includes the `aria-selected` attribute on tree items that are not selectable.
- [x] Visual design should differentiate between selected and focussed. Selected = checkbox. Focus = border on checkbox
	In multi-select trees, the selected state is always independent of the focus. For example, in a typical file system navigator, the user can move focus to select any number of files for an action, such as copy or move. The visual design should make it clear which items are selected and which item has focus.
- [x]  Add `aria-expanded` to all items with children
- [ ] ??? Add count vs selected count to each parent node?
- [ ] Auto focus on first open item
- [ ] Auto focus on the last open item
- [ ] When page reloads and re-selects it doesn't set indeterminate parent checkboxes
- [x] Declare level, size and position based on [this example](https://www.w3.org/WAI/ARIA/apg/example-index/treeview/treeview-1/treeview-1b.html) 


# Accessibility Testing
## Which assistive technologies to test with 
![[Screenshot 2022-10-19 at 15.40.07.png]]
Image above from [Testing with assistive technologies](https://www.gov.uk/service-manual/technology/testing-with-assistive-technologies) in Gov Service Manual

## Recordings 19th October

### JAWS on Windows (desktop screen reader)
JAWS-Windows.mp4
### NVDA on Windows (desktop screen reader)
NVDA-Windows.mp4
### VoiceOver on MacOS (desktop screen reader)
VoiceOver-DesktopMacOS-Chrome.mov

# Coding Resources
## functional recursive tree walking
Possible use for counting checked or total children
https://jrsinclair.com/articles/2019/functional-js-traversing-trees-with-recursive-reduce/
## Convert directory to JSON
https://www.npmjs.com/package/directory-tree

## Generate random dirs
https://stackoverflow.com/a/13401143

## Recursive Nunjucks macros
https://embed.plnkr.co/AOmdyI/
