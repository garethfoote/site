---
share: true
category: Notes
title: Tree view pattern
---

#case-study #interaction-design 

## Background / Context
Within digital archiving there are various scenarios that require the presentation of a hierarchical file structure to the user. The preservation of the original folder and file structure is one way that digital records have intrinsic meaning, making them representative of their original creation or use and also accessible in the future. Therefore, when a consignment of records is transferred to an archive or when it is being presented back to interested parties, showing the original folder structure is essential.

There are many ways to design a system for accomplishing this in web technologies, including loading a new page for each folder and only ever showing one folder at a time. Another method is to present all the files in a nested tree with expandable folders. There are positives and negatives to both options to do with efficiency of use, accessibility and the amount of content rendered on a single page.  

In terms of the UX both Finder (macOS) and File Explorer (Windows) have been dealing with these problems for years by making both options available and configurable.
![[Screenshot 2023-09-12 at 08.54.19.png]]
## Simplicity, efficiency trade off
The approach that would create the most simple pages with (less content and complexity per page) would be to render a folder per page load. This gives the advantage of only ever needing to present a simple (non-nested) HTML list:

```html
<ul>
	<li class="dir">Cakes</li>
	<li class="file">Shopping list.txt</li>
	<li class="dir">Winter Recipes</li>
</ul>
```
![[Screenshot 2023-09-12 at 09.41.03.png]]
The upsides to this are:
- Simplicity of rendered HTML
- Unlikely to be complex to design/build for accessibility

The downsides to this are:
- Your view is narrow, i.e. you can only every see one folder at a time
- The overhead of navigating back and forth between folders could become significant if you have a deeply nested folder structure

The alternative is to render all files and folders in a set of nested lists.

```html
<ul>
	<li class="dir">Cakes
		<ul>
			<li class="file">Baking powder 1999.txt</li>
			<li class="file">Baking powder 2022.txt</li>
			<li class="dir">Basics techniques</li>
		</ul>
	</li>
	<li class="file">Shopping list.txt</li>
	<li class="dir">Winter Recipes
		<ul>
			...
		</ul>
	</li>
</ul>
```

The upsides to this are:
- Offers a wider view of the files
- Easier to navigate back and forth through directories 

The downsides to this are:
- More complex build
- Accessibility will be more challenging

## User needs
I'm unable to speak about the specifics of the user and business needs, only that it was deemed sensible to explore the rendering of folders and files in one page allowing them to be navigated in place. 

## Accessible design patterns
The common design pattern for this type of display and interaction is a 'tree view'. This has an equivalent [ARIA role](https://www.w3.org/TR/2017/REC-wai-aria-1.1-20171214/#tree) and implementation guidance from [ARIA Authoring Practices Guide (APG)](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/), [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role) and various design systems. See my page of [[UX Pattern - Tree view|UX research on the Tree View]].

## Implementation 

<iframe
  id="inlineFrameExample"
  title="Inline Frame Example"
  width="100%"
  height="400"
  src="https://nationalarchives.github.io/tdr-components/iframe.html?args=&id=tdr-tree-view--default-multiple&viewMode=story"
>
</iframe>


## Accessibility testing

There is a  provides a 


## Our own implementation 
[ANOTHER PAGE]

## Summary 
There are some concerns about 


