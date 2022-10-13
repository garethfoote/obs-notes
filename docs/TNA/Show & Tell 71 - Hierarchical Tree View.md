---
share: true
category: TNA
---

Hierarchical tree view for deeply nested file selection

- Credit to Sam Palmer

- [Currently](https://tdr-prototype.herokuapp.com/metadata/descriptive-metadata/file-level#page-1) we have a page for each folder and pagination within each page. 
	- For a deep nested folder you need to navigate through many pages. 
	- Or within one folder with many files you need to navigate through many pages using pagination.

- For a nested/hierarchical structure (such as a file system) a tree representation is ideal.
	- HTML includes [list elements that can be nested](https://i.stack.imgur.com/rqAiC.jpg) whilst passing validation and being technically accessible for screen readers and keyboard navigation. 
	- [Non-JS example]

- Not a great experience if the consignment of files is big
	- baseline non-Javascript experience is challenging and time consuming
	- for everyone, including those using assistive technology.  	
	- https://www.a11yproject.com/posts/people-who-use-screen-readers-dont-use-javascript/

- **Research** - It is a rare use case but is documented in ARIA web standards 
- WAI-ARIA (Web Accessibilty Initiative - Accessible Rich Internet Applications)
	- > **It especially helps with dynamic content and advanced user interface controls developed with HTML, JavaScript, and related technologies.**
- https://www.w3.org/WAI/ARIA/apg/example-index/treeview/treeview-1/treeview-1b.html

- Features
	- Nested nodes
	- Multi-select
	- Indeterminate checkbox states
	- Collapsible / expandable nodes
	- Current folder state maintained
	- (TDR specific) Current checkbox selection maintained 

- Accessibility features 
	- current position focus state
	- keyboard controls
		- up, down 
		- open, close
		- Go to start & end
	- Search
	- On tree focus default to first selected item

- Remaining work
	- Select All & Deselect all
	- Search
	- More robust accessibility testing on different devices

- Publishing the component 

https://github.com/ctdesign/gov-design-systems-list
https://digital-land.github.io/design-system/components/filter-group/
https://design-patterns.service.justice.gov.uk/components/pagination/