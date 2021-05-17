---
title: Render Mermaid Diagrams with Story
date: "2018-08-19 08:00:00"
url: "/mermaid"
author: "Lionel VICTOR"
description: "A chart or a diagram is worth a thousand words. Story has your back with MermaidJS."
image: "img/unsplash-photos-tZc3vjPCk-Q.jpg"
credit: "https://unsplash.com/photos/5mZ_M06Fc9g/download"
thumbnail: "img/unsplash-photos-tZc3vjPCk-Q.tn-500x500.jpg"
classes:
- feature-figcaption
- feature-figcaption-hidden
- feature-fignum
categories:
- Demo
---

[mermaidjs_home]: https://mermaid-js.github.io/mermaid/#/ "go to mermaid home page..."

### A Work In Progress...

This page is a first attempt at integrating [mermaid-js][mermaidjs_home] diagrams.

<!--more-->

It is a **Work in Progress**. Here follows a non exhaustive list of things to improve or fix:
- Integration with "`feature-figcaption`" may need reviewing

However, some features are already working:
- "`feature-fignum`" does increment the figures' caption number,
- "`feature-figcaption-hidden`" sort of work but requires further testing, and
- most important diagrams are showing properly _(even though styling needs to be worked on)_
- diagrams are not properly aligned / centered
- git diagrams are looking better _(font size was adjusted in mermaid's global configuration)_
- feature's blog article now stands out with its own picture+thumbnail. It also contains code
  samples for most important diagrams.

### The guided Tour

Please join me as I walk you through the classical mermaid scripts:


- SequenceDiagram _([read documentation](https://mermaid-js.github.io/mermaid/#/sequenceDiagram?id=sequence-diagrams))_:
  ```go
  {{</* mermaid */>}}
  sequenceDiagram
      participant Alice
      participant Bob
      Alice->>John: Hello John, how are you?
      loop Healthcheck
          John->John: Fight against hypochondria
      end
      Note right of John: Rational thoughts <br/>prevail...
      John-->Alice: Great!
      John->Bob: How about you?
      Bob-->John: Jolly good!
  {{</* /mermaid */>}}
  ```
  {{< mermaid >}}
  sequenceDiagram
      participant Alice
      participant Bob
      Alice->>John: Hello John, how are you?
      loop Healthcheck
          John->John: Fight against hypochondria
      end
      Note right of John: Rational thoughts <br/>prevail...
      John-->Alice: Great!
      John->Bob: How about you?
      Bob-->John: Jolly good!
  {{< /mermaid >}}

- Flowcharts _([read documentation](https://mermaid-js.github.io/mermaid/#/flowchart?id=flowcharts-basic-syntax))_:
  ```go
  {{</* mermaid */>}}
  graph LR;
      A[Hard edge] -->|Link text| B(Round edge)
      B --> C{Decision}
      C -->|One| D[Result one]
      C -->|Two| E[Result two]
  {{</* /mermaid */>}}
  ```
  {{< mermaid >}}
  graph LR;
      A[Hard edge] -->|Link text| B(Round edge)
      B --> C{Decision}
      C -->|One| D[Result one]
      C -->|Two| E[Result two]
  {{< /mermaid >}}

- GANTT diagram _([read documentation](https://mermaid-js.github.io/mermaid/#/gantt?id=gantt-diagrams))_:
  ```go
  {{</* mermaid */>}}
  gantt
      dateFormat  YYYY-MM-DD
      title Adding GANTT diagram functionality to Story
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
      Add to mermaid                      :1d
  {{</* /mermaid */>}}
  ```
  {{< mermaid >}}
  gantt
      dateFormat  YYYY-MM-DD
      title Adding GANTT diagram functionality to Story
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
      Add to mermaid                      :1d
  {{< /mermaid >}}

- Class diagram _([read documentation](https://mermaid-js.github.io/mermaid/#/classDiagram?id=class-diagrams))_:
  ```go
  {{</* mermaid */>}}
  %%{
    init: {
      "theme": "base",
      "themeVariables": {
        "lineColor": "#ff0000"
      }
    }
  }%%
  classDiagram
      Class01 <|-- AveryLongClass : Cool
      Class03 *-- Class04
      Class05 o-- Class06
      Class07 .. Class08
      Class09 --> C2 : Where am i?
      Class09 --* C3
      Class09 --|> Class07
      Class07 : equals()
      Class07 : Object[] elementData
      Class01 : size()
      Class01 : int chimp
      Class01 : int gorilla
      Class08 <--> C2: Cool label
  {{</* /mermaid */>}}
  ```
  {{< mermaid >}}
  %%{
    init: {
      "theme": "base",
      "themeVariables": {
        "lineColor": "#ff0000"
      }
    }
  }%%
  classDiagram
      Class01 <|-- AveryLongClass : Cool
      Class03 *-- Class04
      Class05 o-- Class06
      Class07 .. Class08
      Class09 --> C2 : Where am i?
      Class09 --* C3
      Class09 --|> Class07
      Class07 : equals()
      Class07 : Object[] elementData
      Class01 : size()
      Class01 : int chimp
      Class01 : int gorilla
      Class08 <--> C2: Cool label
  {{< /mermaid >}}

- Git graph _(experimental)_:
  ```go
  {{</* mermaid */>}}
  gitGraph:
  options
  {
      "nodeSpacing": 64,
      "nodeRadius": 8
  }
  end
      commit
      branch newbranch
      checkout newbranch
      commit
      commit
      checkout master
      commit
      commit
      merge newbranch
  {{</* /mermaid */>}}
  ```
  {{< mermaid >}}
gitGraph:
options
{
  "nodeSpacing": 64,
  "nodeRadius": 6
}
end
  commit
  branch newbranch
  checkout newbranch
  commit
  commit
  checkout master
  commit
  commit
  merge newbranch
  {{< /mermaid >}}

Read next: [Maps with Leaflet.js](/leaflet/).