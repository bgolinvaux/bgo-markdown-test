# Comprehensive Markdown Compatibility Test

---

## 1. Metadata (YAML Front Matter)
```yaml
---
title: "Comprehensive Markdown Test"
author: "Your Name"
tags: [markdown, compatibility, test]
created: 2024-12-12
---
```

## 2. Headers
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

## 3. Emphasis
*Italic*  
**Bold**  
***Bold Italic***  
~~Strikethrough~~

## 4. Lists
### Unordered List
- Item 1
  - Subitem 1
  - Subitem 2
- Item 2

### Ordered List
1. First item
2. Second item
   1. Subitem 1
   2. Subitem 2

## 5. Links
[Inline Link](https://www.example.com)  
[Reference Link][example]

[example]: https://www.example.com

## 6. Images
![Alt text](https://picsum.photos/536/354)  
![Alt text][image]

[image]: https://picsum.photos/536/352

## 7. Blockquotes
> This is a blockquote.
> 
> This is the second paragraph in the blockquote.

## 8. Code
### Inline Code
Here is some `inline code`.

### Code Block
```python
def hello_world():
    print("Hello, world!")
```

## 9. Tables
| Feature      | Supported? | Notes                  |
|--------------|------------|------------------------|
| Tables       | ✅          | Advanced syntax for Sphinx. |
| Admonitions  | ✅          | Sphinx/MyST-specific.  |

## 10. Admonitions
!!! note
    This is a note.

!!! warning
    This is a warning.

## 11. Horizontal Rule
---

## 12. Footnotes
Here is a footnote reference[^1].

[^1]: Here is the footnote.

## 13. Task Lists
- [x] Task 1
- [ ] Task 2
- [ ] Task 3

## 14. HTML
<div style="color: red;">This is a red text.</div>

## 15. Emoji
:smile: :+1: :heart:

## 16. Math
Inline math: $E = mc^2$

Block math:
$$
E = mc^2
$$

## 17. Definition Lists
Term 1
: Definition 1

Term 2
: Definition 2

## 18. Abbreviations
Markdown converts `HTML` to HyperText Markup Language.

*[HTML]: HyperText Markup Language

