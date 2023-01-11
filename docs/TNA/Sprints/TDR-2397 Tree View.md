---
share: true
category: TNA/Sprints
---

Design a tree view implementation for a file hierachy display and selection. Use GDS styles and mirror components where possible. Must be multi-select. Must be as accesibile as possible.

# UX Research
- [[UX Pattern - Tree view]]


# To Dos

Mega bug
NVDA cannot claim focus when there is a event listener on a child element. i.e. the expander buttons. The event could be on the entire list item instead of the button, which seems to work in the codepen (aria patterns) example. This would cause problems for the checkbox/multi-select version because the same click cannot both open and select a folder. 

Bugs
- [ ] Remove console.logs
- [ ] Fix keyboard navigation
- [ ]  [TDR-2799](https://national-archives.atlassian.net/browse/TDR-2799) - tabindex
	- Slightly confused by the instantiation - Contructor collects the first and then all the trees on the page
- [ ]  [TDR-2802](https://national-archives.atlassian.net/browse/TDR-2802) `aria-labelledby`

Improvements
- [ ] Children cloning when swapping out inputs⏫ 
- [ ] hidden input rendered so form still submits⏫ 
- [ ] Remove `aria-checked` (doesn't exist on tree view)⏫ 
- [ ] Do not include the `aria-selected` attribute on tree items that are not selectable.⏫  

- [ ] querySelectors working on document level instead of scoped to the tree element
- [x] ~~`replaceCheckboxWithSpans` more generic name~~
- [ ] name of InputTypes - singular vs plural
- [ ] Parametize the input[name=???]

Library usability
- [ ] Cannot import TS into prototype currently
- [ ] Can we use nunjucks tpls in prototype?

GDS alignment
- [ ] Should we use HTML attributes for customisation as per GDS components instead of params being passed to `initFormListeners()` - the `aria-multiselectable` attribute could be used here

Design
- [ ] When a radio button is selected inside folder we need a visual cue to indicate when it's closed that it has active content
- [ ] focus on radio buttons isn't using GDS yellow surround






# Accessibility Features
- [ ] (Suggested) Add count vs selected count to each parent node?
- [ ] Auto focus on first open item
- [x] **Keyboard navigation**
- [x] Add `aria-multiselectable` to tree
- [x] Add `aria-selected` to all nodes
	In multi-select trees, all selected tree items have `aria-selected="true"` set and all tree item nodes that are selectable but not currently selected have `aria-selected="false"` set. Do not includes the `aria-selected` attribute on tree items that are not selectable.
- [x] Visual design should differentiate between selected and focussed. Selected = checkbox. Focus = border on checkbox
	In multi-select trees, the selected state is always independent of the focus. For example, in a typical file system navigator, the user can move focus to select any number of files for an action, such as copy or move. The visual design should make it clear which items are selected and which item has focus.
- [x]  Add `aria-expanded` to all items with children
- [x] Declare level, size and position based on [this example](https://www.w3.org/WAI/ARIA/apg/example-index/treeview/treeview-1/treeview-1b.html) 



# Accessibility Testing
## Which assistive technologies to test with 
![[Screenshot 2022-10-19 at 15.40.07.png]]
Image above from [Testing with assistive technologies](https://www.gov.uk/service-manual/technology/testing-with-assistive-technologies) in Gov Service Manual

## Recordings 19th October

### JAWS on Windows (desktop screen reader)
[[JAWS-Windows.mp4]]
### NVDA on Windows (desktop screen reader)
[[NVDA-Windows.mp4]]
### VoiceOver on MacOS (desktop screen reader)
[[VoiceOver-DesktopMacOS-Chrome.mov]]

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
