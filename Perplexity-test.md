# Main Title

## Section 1: Text Formatting
Plain text
**Bold text**
*Italic text*
***Bold and italic text***
~~Strikethrough text~~
==Highlighted text== 
^Superscript^ text
~Subscript~ text

## Section 2: Lists
### Unordered List
* Item 1
* Item 2
  * Sub-item 2.1
  * Sub-item 2.2

### Ordered List
1. First item
2. Second item
   1. Sub-item 2.1
   2. Sub-item 2.2

## Section 3: Links and References
[Link text](https://example.com)

[Reference link][ref1]

[ref1]: https://example.com

## Section 4: Images
![Alt text](https://picsum.photos/536/354)

![Referenced image][img1]

[img1]: https://picsum.photos/536/352

## Section 5: Blockquotes
> Single line quote
>> Nested blockquote
> Multiple line quote
> continues here

## Section 6: Code
Inline `code` example

```python
def hello_world():
    print("Hello, World!")
```

## Section 7: Tables
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |

## Section 8: Horizontal Rules
---
***
___

## Section 9: Task Lists
- [x] Completed task
- [ ] Incomplete task
- [x] Another completed task

## Section 10: Footnotes
Here's a sentence with a footnote[^1].
[^1]: This is the footnote content.

## Section 11: Definition Lists
Term 1
: Definition 1

Term 2
: Definition 2

## Section 12: Mathematics
Inline math: $E = mc^2$

Block math:

$$
\sum_{i=1}^{n} x_i = \frac{n(n+1)}{2}
$$

$$
f(x) = \int_{a}^{b} \left( e^{-x^2} \cdot \cos(\pi x) \right) dx + \sum_{n=1}^{\infty} \frac{1}{n^2 + 1}
$$


## Section 13: Comments
[//]: # (This is a comment that won't be rendered)

## Section 14: Escaping Characters
\* Not italic \*
\` Not code \`
\[ Not a link \]

## Section 15: Abbreviations
*[HTML]: Hyper Text Markup Language
HTML is a markup language.

## Section 16: Custom HTML
<details>
<summary>Click to expand</summary>
This is hidden content.
</details>

<div align="center">
Centered text
</div>

## Section 17: Emojis
:smile: :heart: :thumbsup:

## Section 18: Mermaid Graph Diagrams
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## Section 19: Mermaid Sequence Diagrams

```mermaid 
%% A complex Mermaid sequence diagram showcasing multiple participants, synchronous and asynchronous messages,
%% as well as conditions, loops, and notes. This diagram should be compatible with GitHub flavored markdown.

sequenceDiagram
    autonumber
    
    participant U as User
    participant B as Browser
    participant WS as Web Server
    participant DB as Database
    participant PG as Payment Gateway
    participant ES as Email Service

    Note over U,B: User attempts to log in through the browser
    U->>B: Enter credentials (username & password)
    B->>WS: POST /login with credentials
    WS->>DB: Validate user against DB
    
    alt User found
        DB-->>WS: User record found
        WS->>WS: Verify password hash
        
        alt Password correct
            WS-->>B: Send session token & user dashboard data
            B-->>U: Render dashboard
        else Password incorrect
            WS-->>B: Return error "Invalid password"
            B-->>U: Display error
        end
        
    else User not found
        DB-->>WS: No user record
        WS-->>B: Return error "User not found"
        B-->>U: Display error
    end

    Note over WS,PG: After successful login, user initiates a purchase
    U->>B: Click "Buy Now"
    B->>WS: POST /purchase
    WS->>PG: Initiate payment (async)
    par Payment Processing
        PG-->>WS: Payment success confirmation
    and Email Notification
        WS->>ES: Send order confirmation email (async)
        ES-->>WS: Email queued for delivery
    end
    
    loop Retry until email delivered or timeout
        ES->>ES: Check email queue status
        alt Email sent
            ES-->>WS: Delivery confirmed
        else Still queued
            ES-->>ES: Wait & retry
        end
    end

    WS-->>B: Return "Purchase Complete"
    B-->>U: Display "Thank you for your purchase!"

```

## Section 20: Mermaid Graph Diagrams 2

```mermaid

%% This is a complex UML-style collaboration diagram using Mermaid syntax.
%% It shows multiple components (objects) collaborating through messages.
%% Messages are numbered to indicate the sequence of interactions.

graph LR

    %% Define nodes (objects/participants)
    U[User]
    B[Browser]
    WS[Web Server]
    DB[Database]
    PG[Payment Gateway]
    ES[Email Service]

    %% Define interactions (edges with message numbers and actions)
    U -->|1: Initiate login| B
    B -->|2: Send credentials| WS
    WS -->|3: Validate user data| DB
    DB -->|4: Return user record| WS
    WS -->|5: Check password hash| WS
    WS -->|6: Return session token| B
    B -->|7: Render user dashboard| U

    %% Additional collaboration steps
    WS -->|8: Initiate payment request| PG
    PG -->|9: Confirm payment status| WS
    WS -->|10: Send confirmation email| ES
    ES -->|11: Deliver email notification| U

```

## Section 21: Mermaid XY Chart 

```mermaid

xychart-beta
    title "Sales Revenue"
    x-axis [jan, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec]
    y-axis "Revenue (in $)" 4000 --> 11000
    bar [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
    line [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
```

## Mermaid Gantt

```mermaid

gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :until isadded
    Functionality added                 :milestone, isadded, 2014-01-25, 0d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```

## Mermaid Class Diagram

```mermaid

classDiagram

class Name {
&lt;&lt;Interface&gt;&gt;
String
}

class School {
Name: Name
Teachers: List Teacher
}

School --* Name
School --* Teacher

class Person {
Id: Number
Name: Name
}


Person --* Name

class Teacher {
Subject: Subject
Id: Number
Name: Name
}
Teacher --|> Person
Teacher --* Subject

Teacher --* Name

class Sudent {
Subjects: List Subject
FirstReport: ReportCardResult
SecondReport: ReportCardResult
ThirdReport: ReportCardResult
Id: Number
Name: Name
}
Sudent --|> Person
Sudent --* Subject
Sudent --* ReportCardResult
Sudent --* ReportCardResult
Sudent --* ReportCardResult

Sudent --* Name

class Subject {
Name: Name
Description: String
}

Subject --* Name


class ReportCard {
Results: List ReportCardResult
}

ReportCard --* ReportCardResult

class ReportCardResult {
Subject: Subject
Grade: Number
RepeatGrade: Number
}

ReportCardResult --* Subject



class Other {
Something: String
}
```



## STL

```stl
solid cube_corner
  facet normal 0.0 -1.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 1.0 0.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
  facet normal 0.0 0.0 -1.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 1.0 0.0 0.0
    endloop
  endfacet
  facet normal -1.0 0.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 0.0 1.0
      vertex 0.0 1.0 0.0
    endloop
  endfacet
  facet normal 0.577 0.577 0.577
    outer loop
      vertex 1.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
endsolid
```

