---
share: true
category: Notes
title: Creating an efficient file browsing experience using the Tree View pattern
---

#case-study #interaction-design 

## Background / Context
Within digital archiving there are various scenarios that require the presentation of a hierarchical file structure to the user. The preservation of the original folder and file structure is one way that digital records have intrinsic meaning, making them representative of their original creation or use and also accessible in the future. Therefore, when a consignment of records is transferred to an archive or when it is being presented back to interested parties, showing the original folder structure is essential.

There are many ways to design a system for accomplishing this in web technologies, including loading a new page for each folder and only ever showing one folder at a time. Another method is to present all the files in a nested tree with expandable folders. There are positives and negatives to both options to do with efficiency of use, accessibility and the amount of content rendered on a single page.  

In terms of the UX both Finder (macOS) and File Explorer (Windows) have been dealing with these problems for years by making both options available and configurable.
![[Screenshot 2023-09-12 at 08.54.19.png]]
## Simplicity, efficiency trade off

To achieve something like the above in a web interface we would need to render all files and folders in a set of nested lists, and progressively enhance this to allow collapsing and expanding of folders. 

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

The upsides to this are the ability to have a 'wider' view of your folders. Seeing more than one directory simultaneously. This also helps with locating where you are in a deeply nested structure. It is also trivial to navigate back and forth through directories. 

The main downside to this approach is that screen readers are not great at representing complex structures such. 

## User needs
I'm unable to speak about the specifics of the user and business needs, only that it was deemed sensible to explore the rendering of folders and files in one page allowing them to be navigated in place. My challenge here was to design this complex pattern with accessibility at the forefront of the process. 

## Accessible design patterns
The common design pattern for this type of display and interaction is a 'tree view'. This has an equivalent [ARIA role](https://www.w3.org/TR/2017/REC-wai-aria-1.1-20171214/#tree) and implementation guidance from [ARIA Authoring Practices Guide (APG)](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/), [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role) and various design systems. 

See my page of [[UX Pattern - Tree view|UX research on the Tree View]].

## Design 

|     |  |
| -------- | ------- |
| ![[File selection - Radio buttons.png]]  | ![[File selection - Radio buttons.png]]    |



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


